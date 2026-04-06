<script setup lang="ts">
import { Button } from "@/components/ui/button";
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";


enum PopularPlan {
  NO = 0,
  YES = 1,
}

interface PlanBenefit {
  title: string;
  description?: string;
}

interface PlanProps {
  title: string;
  popular: PopularPlan;
  price: string;
  description: string;
  buttonText: string;
  benefitList: PlanBenefit[];
}

const plans: PlanProps[] = [
  {
    title: "Our Payment Gateway",
    popular: PopularPlan.YES,
    price: "Payment Rate",
    description: "Free to contact us for more information.",
    buttonText: "Contact Us",
    benefitList: [
      { title: " Fpx", description: "-Up to 17 banks" },
      { title: " DuitNow" },
      {
        title: " E wallet",
        description: "-Up to 5 Channels",
      },
      { title: " Pay out FPX" },
      { title: " Payout Big" },
    ],
  },
];
</script>

<template>
  <section class="container py-24 sm:py-32">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      Premium Serve
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Connect With Us
    </h2>

    <h3
      class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground pb-14"
    >
      Explore how our bespoke financial solutions can optimize your global
      transaction landscape. Our dedicated team is ready to engineer your
      growth.
    </h3>

    <div class="flex justify-center items-center">
      <Card
        v-for="{
          title,
          popular,
          price,
          description,
          buttonText,
          benefitList,
        } in plans"
        :key="title"
        :class="{
          'drop-shadow-xl shadow-black/10 dark:shadow-white/10 border-[1.5px] border-primary lg:scale-[1.1]':
            popular === PopularPlan?.YES,
        }"
      >
        <CardHeader>
          <CardTitle class="pb-2">
            {{ title }}
          </CardTitle>

          <CardDescription class="pb-4">{{ description }}</CardDescription>

          <div>
            <span class="text-3xl font-bold">{{ price }}</span>
          </div>
        </CardHeader>

        <CardContent class="flex">
          <div class="space-y-4">
            <span
              v-for="(benefit, index) in benefitList"
              :key="`${benefit.title}-${index}`"
              class="flex"
            >
              <div class="flex flex-col">
                <h3 class="font-bold">
                  {{ index + 1 }}. {{ benefit.title }}
                </h3>
                <h3 v-if="benefit.description" class="font-medium">
                  {{ benefit.description }}
                </h3>
              </div>
            </span>
          </div>
        </CardContent>

        <CardFooter>
          <Button
            :variant="popular === PopularPlan?.NO ? 'secondary' : 'default'"
            class="w-full"
            onclick="window.location.href = 'https://wa.me/qr/YJSBMHJW7VVOK1'"
          >
            {{ buttonText }}
          </Button>
        </CardFooter>
      </Card>
    </div>
  </section>
</template>
