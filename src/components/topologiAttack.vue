<template>
    <div id="network-topology"
        class="flex flex-col items-center -mx-10 md:-mx-4 -mb-6 md:-mb-16 -mt-[4.4rem] md:-mt-20 w-full h-auto">
        <svg ref="topologySVG" viewBox="0 0 700 700" preserveAspectRatio="xMidYMid meet"
            class="w-full h-auto max-w-full"></svg>
    </div>
</template>

<script>
import * as d3 from "d3";

export default {
    data() {
        return {
            svgPaths: {
                laptop: require('@/assets/laptop.svg'),
                server: require('@/assets/server.svg'),
                firewall: require('@/assets/firewall.svg'),
                bug: require('@/assets/bug.svg')
            },
            bugTypes: {
                laptop1: { label: "SQL Injection", color: "#B20600" },
                laptop2: { label: "Phishing", color: "#B20600" },
                laptop3: { label: "XSS", color: "#B20600" },
                laptop4: { label: "Malware", color: "#B20600" }
            },
            isBlocked: false,
        };
    },
    mounted() {
        this.drawTopology();
        setTimeout(this.startAttack, 100);
        setInterval(this.startAttack, 5000);
    },
    methods: {
        drawTopology() {
            const svg = d3.select(this.$refs.topologySVG);

            const nodes = [
                { id: "laptop1", x: 175, y: 175, image: this.svgPaths.laptop },
                { id: "laptop2", x: 175, y: 620, image: this.svgPaths.laptop },
                { id: "laptop3", x: 620, y: 175, image: this.svgPaths.laptop },
                { id: "laptop4", x: 620, y: 620, image: this.svgPaths.laptop },
                { id: "firewall1", x: 295, y: 420, image: this.svgPaths.firewall },
                { id: "firewall2", x: 420, y: 420, image: this.svgPaths.firewall },
                { id: "firewall3", x: 545, y: 420, image: this.svgPaths.firewall },
                { id: "server", x: 420, y: 270, image: this.svgPaths.server }
            ];

            const links = [
                { source: "laptop1", target: "firewall1" },
                { source: "laptop2", target: "firewall1" },
                { source: "laptop3", target: "firewall3" },
                { source: "laptop4", target: "firewall3" },
                { source: "firewall1", target: "firewall2" },
                { source: "firewall3", target: "firewall2" },
                { source: "firewall2", target: "server" }
            ];

            nodes.forEach(node => {
                svg.append("image")
                    .attr("href", node.image)
                    .attr("x", node.x)
                    .attr("y", node.y)
                    .attr("width", 60)
                    .attr("height", 60)
                    .attr("id", node.id);
            });

            links.forEach(link => {
                const sourceNode = nodes.find(n => n.id === link.source);
                const targetNode = nodes.find(n => n.id === link.target);
                svg.append("line")
                    .attr("x1", sourceNode.x + 30)
                    .attr("y1", sourceNode.y + 30)
                    .attr("x2", targetNode.x + 30)
                    .attr("y2", targetNode.y + 30)
                    .attr("stroke", "#B20600")
                    .attr("stroke-width", 2);
            });
        },
        getRandomAttackingLaptops() {
            const allLaptops = ["laptop1", "laptop2", "laptop3", "laptop4"];
            const numAttacks = Math.floor(Math.random() * 2) + 1;
            return allLaptops.sort(() => 0.5 - Math.random()).slice(0, numAttacks);
        },
        startAttack() {
            this.isBlocked = false;
            const svg = d3.select(this.$refs.topologySVG);

            svg.selectAll(".bug, .bug-label").remove();

            const attackingLaptops = this.getRandomAttackingLaptops();

            attackingLaptops.forEach((laptopId) => {
                const laptop = svg.select(`#${laptopId}`);

                if (!laptop.empty()) {
                    const bugType = this.bugTypes[laptopId];
                    const initialX = parseFloat(laptop.attr("x")) + 30;
                    const initialY = parseFloat(laptop.attr("y")) + 30;

                    const firewallX = (laptopId === "laptop1" || laptopId === "laptop2") ? 295 : 545;
                    const firewallY = 450 + (laptopId === "laptop1" || laptopId === "laptop3" ? -25 : 0);

                    const firewall2X = 420;

                    const bug = svg.append("image")
                        .attr("href", this.svgPaths.bug)
                        .attr("class", "bug")
                        .attr("x", initialX)
                        .attr("y", initialY)
                        .attr("width", 50)
                        .attr("height", 50);

                    bug.transition()
                        .duration(2300)
                        .attr("x", firewallX)
                        .attr("y", firewallY)
                        .on("end", () => {
                            const label = svg.append("text")
                                .attr("class", `font-bold bug-label`)
                                .attr("x", firewallX)
                                .attr("y", firewallY + 30)
                                .text(bugType.label)
                                .attr("font-size", "18px")
                                .attr("fill", bugType.color)
                                .attr("letter-spacing", "1px")
                                .attr("font-family", "JetBrains Mono, monospace");

                            bug.transition()
                                .duration(2000)
                                .attr("x", firewall2X)
                                .attr("y", 450)
                                .on("end", () => {
                                    this.blockAttack(bug, bugType.color);
                                    label.remove();
                                });

                            label.transition()
                                .duration(2000)
                                .attr("x", firewall2X)
                                .attr("y", 440);
                        });
                } else {
                    console.error(`Element with ID ${laptopId} not found`);
                }
            });
        },
        blockAttack(bug) {
            const svg = d3.select(this.$refs.topologySVG);
            const color = "#B20600";

            const messages = [
                "try again next time",
                "u doesn't matter",
                "are u tired?"
            ];
            const targetLengths = [1, 3, 4];
            const randomTargetLength = targetLengths[Math.floor(Math.random() * targetLengths.length)];
            const filteredMessages = messages.filter(msg => msg.split(" ")[0].length === randomTargetLength);
            const randomMessage = filteredMessages.length > 0
                ? filteredMessages[Math.floor(Math.random() * filteredMessages.length)]
                : messages[Math.floor(Math.random() * messages.length)];

            svg.selectAll(".block-message").remove();
            svg.append("circle")
                .attr("cx", 420)
                .attr("cy", 450)
                .attr("r", 0)
                .attr("fill", color)
                .attr("opacity", 0.5)
                .transition()
                .duration(100)
                .attr("r", 60)
                .transition()
                .duration(100)
                .attr("opacity", 0)
                .on("end", () => {
                    bug.remove();
                });

            const message = svg.append("text")
                .attr("class", "block-message")
                .attr("x", 450)
                .attr("y", 490)
                .attr("text-anchor", "middle")
                .attr("font-size", "16px")
                .attr("fill", color)
                .attr("opacity", 0)
                .attr("letter-spacing", "1px")
                .attr("font-family", "JetBrains Mono, monospace")
                .text(randomMessage);

            message.transition()
                .duration(200)
                .attr("opacity", 1)
                .transition()
                .delay(1000)
                .duration(500)
                .attr("opacity", 0)
                .on("end", () => {
                    message.remove();
                });
        }
    }
};
</script>
