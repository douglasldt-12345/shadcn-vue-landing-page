<script setup lang="ts">
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";

interface FAQProps {
  question: string;
  answer: string;
  value: string;
}

const FAQList: FAQProps[] = [
  {
    question:
      "How does the gateway ensure institutional-grade security for high-volume transactions?",
    answer:
      "We employ multi-layer encryption protocols and PCI DSS Level 1 compliant infrastructure. Every transaction is monitored by our proprietary AI fraud detection engine, ensuring absolute fiscal reliability and risk mitigation in real-time.",
    value: "item-1",
  },
  {
    question:
      "Can the platform support multi-currency settlement for global commerce?",
    answer:
      "Yes. Our sophisticated gateway enables seamless cross-border transactions with localized settlement options in over 135+ currencies, reducing conversion friction and optimizing your global revenue streams.",
    value: "item-2",
  },
  {
    question:
      "What is the typical integration timeline for our existing ecosystem?",
    answer:
      "Designed for high-velocity growth, our developer-first API allows for rapid deployment. Most enterprises achieve full integration within days, benefiting from our comprehensive documentation and dedicated technical support.",
    value: "item-3",
  },
  {
    question:
      "How does the system maintain high-velocity liquidity during peak traffic?",
    answer:
      "Our architecture is built for strategic scalability. By utilizing a distributed ledger approach and redundant banking rails, we maintain 99.99% uptime and low-latency processing, even during extreme transactional surges.",
    value: "item-4",
  },
  {
    question:
      "What advanced analytics are provided for long-term financial health?",
    answer:
      "Beyond simple processing, we provide a unified intelligence dashboard. This includes deep-dive insights into transaction success rates, customer churn analysis, and automated reconciliation reports to help you prioritize strategic scalability.",
    value: "item-5",
  },
];
</script>

<template>
  <section id="faq" class="container md:w-[700px] py-24 sm:py-32">
    <div class="text-center mb-8">
      <h2 class="text-lg text-primary text-center mb-2 tracking-wider">FAQS</h2>

      <h2 class="text-3xl md:text-4xl text-center font-bold">
        Common Questions
      </h2>
    </div>

    <Accordion type="single" collapsible class="AccordionRoot">
      <AccordionItem
        v-for="{ question, answer, value } in FAQList"
        :key="value"
        :value="value"
      >
        <AccordionTrigger class="text-left"> {{ question }} </AccordionTrigger>

        <AccordionContent>{{ answer }}</AccordionContent>
      </AccordionItem>
    </Accordion>
  </section>
</template>
