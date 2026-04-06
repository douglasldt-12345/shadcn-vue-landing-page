<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Sparkle,
  Tag,
  Paintbrush,
  Blocks,
  LineChart,
  Wallet,
} from "lucide-vue-next";

interface BenefitsProps {
  icon: string;
  title: string;
  description: string;
}

const benefitList: BenefitsProps[] = [
  {
    icon: "guardian_icon.png",
    title: "Sentinel of your Revenue",
    description:
      "We treat your capital with the vigilance it deserves. Our proprietary risk intelligence anticipates threats before they manifest, ensuring your profit margins remain uncompromised in a volatile global market.",
  },
  {
    icon: "global_icon.png",
    title: "Catalyize Global Market Access",
    description:
      "Eliminate the friction of cross-border commerce. Our unified payment infrastructure empowers your brand to resonate in every local market, turning global complexity into seamless growth opportunities.",
  },
  {
    icon: "money.png",
    title: "  Amplifying Revenue Velocity",
    description:
      "Empower your business to capture every potential cent. Our high-performance gateway is engineered to reduce friction, ensuring a seamless path from intent to settlement for global customers.",
  },
  {
    icon: "compass.png",
    title: "Strategic & Growth-Oriented",
    description:
      "We specialize in deploying data-backed marketing frameworks designed to scale payment ecosystems. By leveraging rigorous A/B testing and consumer behavior analysis, we optimize every touchpoint of the merchant journey to drive sustainable acquisition and long-term retention.",
  },
];

const iconMap: Record<
  string,
  | typeof Sparkle
  | typeof Tag
  | typeof Paintbrush
  | typeof Blocks
  | typeof LineChart
  | typeof Wallet
> = {
  sparkle: Sparkle,
  tag: Tag,
  paintbrush: Paintbrush,
  blocks: Blocks,
  lineChart: LineChart,
  wallet: Wallet,
};
</script>

<template>
  <section id="Security and Trust" class="container py-24 sm:py-32">
    <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
      <div>
        <h2 class="text-lg text-primary mb-2 tracking-wider">
          Security and Trust
        </h2>

        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Engineered for Infinite Scale
        </h2>
        <p class="text-xl text-muted-foreground mb-8">
          From lightning-fast authoriztionto multi-layered fraud prevention, we
          redefine the architecture of global payments with uncompromising
          speed.
        </p>
      </div>

      <div class="grid lg:grid-cols-2 gap-4 w-full">
        <Card
          v-for="({ icon, title, description }, index) in benefitList"
          :key="title"
          class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number"
        >
          <CardHeader>
            <div class="flex justify-between">
              <img :src="`/${icon}`" class="w-20 h-20 mb-6" />

              <span
                class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30"
                >0{{ index + 1 }}</span
              >
            </div>

            <CardTitle>{{ title }}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>
