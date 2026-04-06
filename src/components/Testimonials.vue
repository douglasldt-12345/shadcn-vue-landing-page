<script setup lang="ts">
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar";
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Star } from "lucide-vue-next";

const benefitList: BenefitProps[] = [
  {
    title: "Unrivaled Performance",
    description:
      "Our intelligent routing technology ensures maximum transaction success rates with millisecond latency. We turn every payment attempt into a successful settlement.",
    image: "point.png",
  },
  {
    title: "Gold-Standard Security",
    description:
      "We believe in high-tech supported by high-touch. Our elite technical team is available golden security services, providing bespoke solutions tailored specifically to your business needs.",
    image: "point.png",
  },
  {
    title: "Dedicated Support",
    description:
      "TG Payment Gateway is trusted by global enterprise leaders to provide them with the best possible service and support.",
    image: "point.png",
  },
];
</script>

<template>
  <section id="testimonials" class="container py-24 sm:py-32">
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
        Benefits
      </h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        TG Payment Gateway
      </h2>
      <p>Unrivaled excellence, dedicated to you.</p>
    </div>

    <div class="lg:w-[80%] mx-auto relative">
      <div
        v-for="({ title, description, image }, index) in benefitList"
        :key="title"
        :class="[
          'flex mb-8 items-center',
          { ' flex-row-reverse': index % 2 !== 0 },
        ]"
      >
        <Card class="h-full bg-transparent border-0 shadow-none">
          <CardHeader>
            <CardTitle class="text-2xl font-bold">
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground w-[80%] text-xl">
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
