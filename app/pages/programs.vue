<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Our Programs
        </h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">
          Discover how Fraser Paramedic Society creates connection, supports
          families, and strengthens communities.
        </p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
          <div>
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
              >Programs</span
            >
            <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy mb-6">
              Morale & Connection Initiatives
            </h2>
            <p class="text-gray-600 mb-6">
              We create events and experiences that bring paramedics together —
              building connection, pride, and belonging.
            </p>
            <ul class="space-y-3">
              <li
                v-for="item in moralePrograms"
                :key="item"
                class="flex items-center gap-3"
              >
                <div
                  class="w-6 h-6 bg-fps-navy rounded-full flex items-center justify-center flex-shrink-0"
                >
                  <Check class="w-4 h-4 text-white" />
                </div>
                <span class="text-gray-700">{{ item }}</span>
              </li>
            </ul>
          </div>
          <div>
            <img
              src="https://placehold.co/600x400"
              alt="Morale and connection event"
              class="rounded-2xl shadow-lg w-full h-[400px] object-cover"
            />
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-gray-50">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
          <div class="order-2 lg:order-1">
            <img
              src="https://placehold.co/600x400"
              alt="Community project"
              class="rounded-2xl shadow-lg w-full h-[400px] object-cover"
            />
          </div>
          <div class="order-1 lg:order-2">
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
              >Programs</span
            >
            <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy mb-6">
              Community Projects
            </h2>
            <p class="text-gray-600 mb-6">
              From public engagement to educational projects, FPS strengthens
              the connection between paramedics and the communities they serve.
            </p>
            <ul class="space-y-3">
              <li
                v-for="item in communityPrograms"
                :key="item"
                class="flex items-center gap-3"
              >
                <div
                  class="w-6 h-6 bg-fps-navy rounded-full flex items-center justify-center flex-shrink-0"
                >
                  <Check class="w-4 h-4 text-white" />
                </div>
                <span class="text-gray-700">{{ item }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="text-center mb-12">
          <span
            class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
            >Looking Ahead</span
          >
          <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy">
            Future Initiatives
          </h2>
          <p class="text-gray-600 mt-4 max-w-2xl mx-auto">
            We're constantly evolving to better serve our community.
          </p>
        </div>
        <div class="grid md:grid-cols-3 gap-8">
          <div
            v-for="initiative in futureInitiatives"
            :key="initiative.title"
            class="bg-gray-50 rounded-2xl p-8"
          >
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-6"
            >
              <component :is="initiative.icon" class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-xl font-bold text-fps-navy mb-3">
              {{ initiative.title }}
            </h3>
            <p class="text-gray-600">{{ initiative.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-fps-navy">
      <div class="max-w-4xl mx-auto container-padding text-center">
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-6">
          Be Part of Our Programs
        </h2>
        <p class="text-lg text-blue-100 mb-8 max-w-2xl mx-auto">
          Whether you're looking to attend an event, volunteer, or support our
          initiatives, there's a place for you in the FPS community.
        </p>
        <div class="flex flex-wrap justify-center gap-4">
          <NuxtLink
            to="/events"
            class="inline-flex items-center gap-2 px-8 py-4 bg-white text-fps-navy font-semibold rounded-lg hover:bg-blue-50 transition-colors"
          >
            <Calendar class="w-5 h-5" />
            View Events
          </NuxtLink>
          <NuxtLink
            to="/get-involved"
            class="inline-flex items-center gap-2 px-8 py-4 border-2 border-white text-white font-semibold rounded-lg hover:bg-white/10 transition-colors"
          >
            <Users class="w-5 h-5" />
            Get Involved
          </NuxtLink>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import {
  Check,
  Calendar,
  Users,
  TrendingUp,
  DollarSign,
  MapPin,
} from "lucide-vue-next";

useHead({ title: "Programs" });

const moralePrograms = [
  "Winter Ball – Annual formal celebration",
  "Golf Tournament – Charity fundraising event",
  "Community Social Events – Casual gatherings",
  "Peer Connection Nights – Support and networking",
];
const communityPrograms = [
  "Educational initiatives for the public",
  "Public engagement events",
  "Collaborative partnerships with local organizations",
  "First responder appreciation activities",
];
const futureInitiatives = [
  {
    title: "Expanded Programming",
    description:
      "We're developing new events and initiatives to reach more paramedics across British Columbia.",
    icon: TrendingUp,
  },
  {
    title: "Increased Fundraising",
    description:
      "Building our capacity to fund more programs and provide greater support.",
    icon: DollarSign,
  },
  {
    title: "Broader Provincial Reach",
    description:
      "Expanding our impact beyond the Lower Mainland to serve paramedics province-wide.",
    icon: MapPin,
  },
];
</script>
