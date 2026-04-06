<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Paintbrush,
  MessageCircle,
  TabletSmartphone,
  BadgeCheck,
  Goal,
  PictureInPicture,
  MousePointerClick,
  Newspaper,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "phone.png",
    title: "Mobile-First Experience",
    description:
      "Deliver a frictionless checkout experience optimized for the mobile economy. Our responsive interface ensures high conversion rates across all devices, supporting native in-app payments and mobile wallets.",
  },
  {
    icon: "ecosystem.png",
    title: "Trusted Merchant Ecosystem",
    description:
      "Join a global network of industry leaders who rely on our robust infrastructure. Our proven track record in handling high-volume transactions fosters institutional trust and consumer confidence.",
  },
  {
    icon: "personalized.png",
    title: "AI-Driven Personalization",
    description:
      "Leverage intelligent data insights to tailor the payment journey. By analyzing consumer behavior, we provide localized payment methods and dynamic content that resonate with your specific audience.",
  },
  {
    icon: "dashboard.png",
    title: "Immersive Dashboard Analytics",
    description:
      "Visualize your business growth through advanced real-time reporting. Our intuitive data visualization tools turn complex transactional data into actionable strategic insights at a glance.",
  },
  {
    icon: "checkout.png",
    title: "Conversion-Optimized Checkout",
    description:
      "Eliminate drop-offs with a streamlined call-to-action framework. We prioritize psychological triggers and intuitive navigation to guide users seamlessly from intent to successful authorization.",
  },
  {
    icon: "brand.png",
    title: "Strategic Brand Positioning",
    description:
      "Define your market presence with clarity and authority. Our platform empowers you to communicate your value proposition effectively, ensuring a professional and cohesive brand image across the globe.",
  },
];

const iconMap: Record<
  string,
  | typeof TabletSmartphone
  | typeof BadgeCheck
  | typeof Goal
  | typeof PictureInPicture
  | typeof Paintbrush
  | typeof MousePointerClick
  | typeof MessageCircle
  | typeof Newspaper
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
};
</script>

<template>
  <section id="features" class="container py-24 sm:py-32">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Features
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      What Makes Us Different
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      From lightning-fast authoriztionto multi-layered fraud prevention, we
      redefine the architecture of global payments with uncompromising speed.
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div v-for="{ icon, title, description } in featureList" :key="title">
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex justify-center items-center">
            <div
              class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4"
            >
              <img :src="`/${icon}`" class="w-20 h-20 mb-6" />
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
