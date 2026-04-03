<script setup lang="ts">
import { Marquee } from "@selemondev/vue3-marquee";
import "@selemondev/vue3-marquee/dist/style.css";

import {
  Crown,
  Vegan,
  Ghost,
  Puzzle,
  Squirrel,
  Cookie,
  Drama,
} from "lucide-vue-next";

interface sponsorsProps {
  icon: string;
  name: string;
}

const sponsors = [
  {
    icon: "tg_ewallet.png",
    name: "TNG",
  },
  {
    icon: "tg_duitnow.png",
    name: "DuitNow",
  },
  {
    icon: "tg_ffx.png",
    name: "ABBPAY",
  },
  {
    icon: "tg_ffx.png",
    name: "ABMB",
  },
  {
    icon: "tg_ffx.png",
    name: "ARGO",
  },
  {
    icon: "tg_ffx.png",
    name: "BIMB",
  },
  {
    icon: "tg_ffx.png",
    name: "BSN",
  },
  {
    icon: "tg_ffx.png",
    name: "CIMB",
  },
  {
    icon: "tg_ffx.png",
    name: "HLBB",
  },
  {
    icon: "tg_ffx.png",
    name: "HSBC",
  },
  {
    icon: "tg_ffx.png",
    name: "KFH",
  },
  {
    icon: "tg_ffx.png",
    name: "MB2U",
  },
  {
    icon: "tg_ffx.png",
    name: "BMMB",
  },
  {
    icon: "tg_ffx.png",
    name: "OCBC",
  },
  {
    icon: "tg_ffx.png",
    name: "PBB",
  },
  {
    icon: "tg_ffx.png",
    name: "RHB",
  },
  {
    icon: "tg_ffx.png",
    name: "SCB",
  },
  {
    icon: "tg_ffx.png",
    name: "UOB",
  },
];

const iconMap: Record<
  string,
  | typeof Crown
  | typeof Vegan
  | typeof Ghost
  | typeof Puzzle
  | typeof Squirrel
  | typeof Cookie
  | typeof Drama
> = {
  crown: Crown,
  vegan: Vegan,
  ghost: Ghost,
  puzzle: Puzzle,
  squirrel: Squirrel,
  cookie: Cookie,
  drama: Drama,
};
</script>

<template>
  <section id="sponsors" class="max-w-[75%] mx-auto pb-24 sm:pb-32">
    <h2 class="text-lg md:text-xl text-center mb-6">Our Grand Sponsors</h2>

    <div class="mx-auto">
      <Marquee
        class="gap-[3rem] [--duration:15s]"
        :pauseOnHover="true"
        :fade="true"
        innerClassName="gap-[3rem]"
      >
        <div
          v-for="{ icon, name } in sponsors"
          :key="name"
          class="flex items-center text-xl md:text-2xl font-medium"
        >
          <img
            :src="`/${icon}`"
            :alt="name"
            class="w-12 h-12 mr-1 object-contain"
          />
          <span>{{ name }}</span>
        </div>
      </Marquee>
    </div>
  </section>
</template>
