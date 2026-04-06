<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";

interface HowItWorksProps {
  badgeTitle: string;
  title: string;
  description: string;
  image: string;
}

const HowItWorksList: HowItWorksProps[] = [
  {
    badgeTitle: "Contribute",
    title: "Empower Global Commerce with Every Transaction",
    description:
      "We redefine the standard of financial liquidity. By integrating our sophisticated gateway, your business becomes part of a seamless economic network designed for high-velocity growth and absolute fiscal reliability.",
    image: "empower.png",
  },
  {
    badgeTitle: "Discover",
    title: "Precision Excellence in Every Decision",
    description:
      "Beyond simple processing, we provide the intelligence needed to optimize your revenue streams. Discover a partnership that prioritizes strategic scalability and long-term financial health over short-term gains.",
    image: "precision.png",
  },
  {
    badgeTitle: "Innovate",
    title: "Driving the Future of Digital Settlements",
    description:
      "Innovation is embedded in our architecture. From agile payment methods to instant cross-border clearing, we continuously evolve our infrastructure to ensure your business stays ahead of a rapidly shifting financial landscape.",
    image: "settlement.png",

  },
  {
    badgeTitle: "Collaborate",
    title: "Synergistic Growth Through Strategic Alliance",
    description:
      "Success in the global market is a collaborative venture. We align our advanced technology with your unique business objectives, creating a powerful synergy that transforms traditional barriers into competitive advantages.",
    image: "growth.png",
  },
];
</script>

<template>
  <section id="features" class="container py-24 sm:py-32">
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        How It Works
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Step-by-Step Process
      </h2>
    </div>

    <div class="lg:w-[80%] mx-auto relative">
      <div
        v-for="(
          { badgeTitle, title, description, image }, index
        ) in HowItWorksList"
        :key="title"
        :class="[
          'flex mb-8 items-center',
          { ' flex-row-reverse': index % 2 !== 0 },
        ]"
      >
        <Card class="h-full bg-transparent border-0 shadow-none">
          <CardHeader>
            <div class="pb-4">
              <Badge>{{ badgeTitle }}</Badge>
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground w-[80%]">
            {{ description }}
          </CardContent>
        </Card>

        <img
          :src="image"
          :alt="`Image describing ${title} `"
          className="w-[150px]  md:w-[250px] lg:w-[300px] mx-auto -scale-x-100 "
        />
        <div
          :class="[
            '-z-10 absolute right-0 w-44 h-72  lg:w-64 lg:h-80 rounded-full bg-primary/15 dark:bg-primary/10 blur-3xl',
            {
              'left-0': index % 2 !== 0,
            },
          ]"
        ></div>
      </div>
    </div>
  </section>
</template>
