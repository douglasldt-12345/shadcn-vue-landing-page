<script setup lang="ts">
import {
  Card,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

import { Badge } from "@/components/ui/badge";

enum ProService {
  YES = 1,
  NO = 0,
}

interface ServiceProps {
  title: string;
  pro: ProService;
  description: string;
}

const serviceList: ServiceProps[] = [
  {
    title: "Global Settlement & Integration",
    description:
      "Integrate our robust API into your existing ecosystem to facilitate multi-currency settlements with localized payment methods worldwide.",
    pro: 0,
  },
  {
    title: "Unified Omni-Channel Connectivity",
    description:
      "Consolidate your sales streams from web, mobile, and social platforms into a single, high-performance gateway for a consistent merchant experience.",
    pro: 0,
  },
  {
    title: "Automated Fiscal Communications",
    description:
      "Deploy automated, intelligent reporting and instant transaction notifications to maintain high trust levels and streamline your financial operations.",
    pro: 0,
  },
  {
    title: "Risk Intelligence & Fraud Shield",
    description:
      "Deploy an autonomous defense layer that proactively identifies and neutralizes high-risk anomalies. Our sophisticated security architecture ensures bulletproof transaction integrity, safeguarding your capital and reputation in real-time.",
    pro: 1,
  },
];
</script>

<template>
  <section id="services" class="container py-24 sm:py-32">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Services
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Elevate Your Financial Infrastructure
    </h2>
    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
      From transaction processing to enterprise-grade security, we provide the
      strategic financial technology to power your global scaling.
    </h3>
    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4"></div>

    <div
      class="grid sm:grid-cols-2 lg:grid-cols-2 gap-4 w-full lg:w-[60%] mx-auto"
    >
      <div v-for="{ title, description, pro } in serviceList" :key="title">
        <Card class="bg-muted/60 dark:bg-card h-full relative">
          <CardHeader>
            <CardTitle>{{ title }}</CardTitle>
            <CardDescription>{{ description }}</CardDescription>
          </CardHeader>
          <Badge
            v-if="pro === ProService.YES"
            variant="secondary"
            class="absolute -top-2 -right-3"
            >PRO</Badge
          >
        </Card>
      </div>
    </div>
  </section>
</template>
