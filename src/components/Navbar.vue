<script lang="ts" setup>
import { ref } from "vue";

import { useColorMode } from "@vueuse/core";
const mode = useColorMode();
mode.value = "dark";

import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
} from "@/components/ui/navigation-menu";
import {
  Sheet,
  SheetContent,
  SheetFooter,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from "@/components/ui/sheet";

import { Button } from "@/components/ui/button";
import { Separator } from "@/components/ui/separator";
import ToggleTheme from "./ToggleTheme.vue";

interface RouteProps {
  href: string;
  label: string;
}

interface FeatureProps {
  title: string;
  description: string;
}

const routeList: RouteProps[] = [
  {
    href: "#testimonials",
    label: "Testimonials",
  },
  {
    href: "#features",
    label: "Features",
  },
];

const featureList: FeatureProps[] = [
  {
    title: "Showcase Your Value ",
    description: "Highlight how your product solves user problems.",
  },
  {
    title: "Build Trust",
    description:
      "Leverages social proof elements to establish trust and credibility.",
  },
  {
    title: "Capture Leads",
    description:
      "Make your lead capture form visually appealing and strategically.",
  },
];

const isOpen = ref<boolean>(false);
</script>

<template>
  <header
    :class="{
      'shadow-light': mode === 'light',
      'shadow-dark': mode === 'dark',
      'relative w-[90%] md:w-[70%] lg:w-[75%] lg:max-w-screen-xl top-5 mx-auto stickyborder z-40 rounded-2xl flex justify-between items-center p-2 bg-card shadow-md': true,
    }"
  >
    <a href="/" class="font-bold text-lg flex items-center">
      <img src="/logo.png" class="w-10 h-10 mr-2" />
      TGPay</a
    >
    <!-- Mobile -->
    <div class="flex items-center lg:hidden">
      <Sheet v-model:open="isOpen">
        <SheetTrigger as-child>
          <Menu @click="isOpen = true" class="cursor-pointer" />
        </SheetTrigger>

        <SheetContent
          side="left"
          class="flex flex-col justify-between rounded-tr-2xl rounded-br-2xl bg-card"
        >
          <div>
            <SheetHeader class="mb-4 ml-4">
              <SheetTitle class="flex items-center">
                <a href="/" class="flex items-center">
                  <img src="/logo.png" class="w-10 h-10 mr-2" />
                  TGPay
                </a>
              </SheetTitle>
            </SheetHeader>

            <div class="flex flex-col justify-center items-center gap-2">
              <Button
                v-for="{ href, label } in routeList"
                :key="label"
                as-child
                variant="ghost"
                class="justify-start text-base"
              >
                <a @click="isOpen = false" :href="href">
                  {{ label }}
                </a>
              </Button>
            </div>
          </div>

          <SheetFooter class="flex-col sm:flex-col justify-start items-start">
            <Separator class="mb-2" />

            <ToggleTheme />
          </SheetFooter>
        </SheetContent>
      </Sheet>
    </div>

    <NavigationMenu
      class="hidden lg:flex absolute left-1/2 top-1/2 z-20 -translate-x-1/2 -translate-y-1/2"
    >
      <NavigationMenuList>
        <NavigationMenuItem>
          <NavigationMenuLink asChild>
            <Button
              v-for="{ href, label } in routeList"
              :key="label"
              as-child
              variant="ghost"
              class="justify-start text-base"
            >
              <a :href="href">
                {{ label }}
              </a>
            </Button>
          </NavigationMenuLink>
        </NavigationMenuItem>
      </NavigationMenuList>
    </NavigationMenu>

    <a
      href="#pricing"
      class="hidden lg:flex items-center justify-center gap-2 cursor-pointer"
    >
      <img src="/phone2.png" class="w-10 h-10" alt="" />
      <span class="contact-now-gradient-border rounded-full">
        <span class="contact-now-gradient-spin" aria-hidden="true" />
        <span class="contact-now-gradient-inner text-sm font-bold rounded-full">
          Contact Now
        </span>
      </span>
    </a>
  </header>
</template>

<style scoped>
.shadow-light {
  box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.085);
}

.shadow-dark {
  box-shadow: inset 0 0 5px rgba(255, 255, 255, 0.141);
}

.contact-now-gradient-border {
  position: relative;
  display: inline-flex;
  overflow: hidden;
}

.contact-now-gradient-spin {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 250%;
  height: 250%;
  background: conic-gradient(
    from 0deg,
    #000000 0deg,
    #000000 90deg,
    #ffbd5a 180deg,
    #000000 360deg
  );
  animation: contact-now-border-spin 3s linear infinite;
}

.contact-now-gradient-inner {
  position: relative;
  z-index: 1;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin: 2px;
  padding: 0.5rem 0.75rem;
  border-radius: 9999px;
  background: hsl(var(--card));
}

@keyframes contact-now-border-spin {
  from {
    transform: translate(-50%, -50%) rotate(0deg);
  }
  to {
    transform: translate(-50%, -50%) rotate(360deg);
  }
}
</style>
