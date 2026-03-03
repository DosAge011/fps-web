<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Sponsors & Partners
        </h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">
          Partner with purpose. Our sponsors make our work possible.
        </p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
          <div>
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
              >Partnership</span
            >
            <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy mb-6">
              Partner With Purpose
            </h2>
            <p class="text-gray-600 mb-6">
              Our sponsors make our work possible. Through event partnerships,
              community support, and financial contributions, our partners help
              us invest directly in the wellbeing of paramedics and first
              responders.
            </p>
            <p class="text-gray-600 mb-8">
              When you partner with FPS, you're not just supporting events —
              you're strengthening morale, building connection, and making a
              real difference.
            </p>
            <NuxtLink to="/contact" class="btn-primary"
              >Become a Sponsor</NuxtLink
            >
          </div>
          <div>
            <img
              src="https://placehold.co/600x400"
              alt="Partnership"
              class="rounded-2xl shadow-lg w-full h-[400px] object-cover"
            />
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-gray-50">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="text-center mb-12">
          <span
            class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
            >Opportunities</span
          >
          <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy">
            Sponsorship Opportunities
          </h2>
          <p class="text-gray-600 mt-4 max-w-2xl mx-auto">
            We offer various ways for businesses and organizations to partner
            with us.
          </p>
        </div>
        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6">
          <div
            v-for="opportunity in sponsorshipOpportunities"
            :key="opportunity.title"
            class="bg-white rounded-2xl p-6 shadow-sm hover:shadow-lg transition-shadow"
          >
            <div
              class="w-12 h-12 bg-fps-navy rounded-lg flex items-center justify-center mb-4"
            >
              <component :is="opportunity.icon" class="w-6 h-6 text-white" />
            </div>
            <h3 class="text-lg font-bold text-fps-navy mb-2">
              {{ opportunity.title }}
            </h3>
            <p class="text-gray-600 text-sm">{{ opportunity.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="text-center mb-12">
          <span
            class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
            >Our Partners</span
          >
          <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy">
            Current & Past Sponsors
          </h2>
          <p class="text-gray-600 mt-4 max-w-2xl mx-auto">
            We're grateful for the support of these organizations.
          </p>
        </div>
        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
          <a
            v-for="sponsor in sponsors"
            :key="sponsor.name"
            :href="sponsor.website"
            target="_blank"
            rel="noopener"
            class="group bg-gray-50 rounded-xl p-6 flex flex-col items-center justify-center hover:bg-gray-100 transition-colors"
          >
            <div class="w-20 h-20 mb-4 flex items-center justify-center">
              <img
                :src="sponsor.logo"
                :alt="sponsor.name"
                class="max-w-full max-h-full object-contain grayscale group-hover:grayscale-0 transition-all"
              />
            </div>
            <span class="text-sm font-medium text-gray-700 text-center">{{
              sponsor.name
            }}</span>
          </a>
        </div>
      </div>
    </section>

    <section class="section-padding bg-fps-navy">
      <div class="max-w-4xl mx-auto container-padding text-center">
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-6">
          Ready to Partner With Us?
        </h2>
        <p class="text-lg text-blue-100 mb-8 max-w-2xl mx-auto">
          Contact us to learn more about sponsorship opportunities.
        </p>
        <div class="flex flex-wrap justify-center gap-4">
          <NuxtLink
            to="/contact"
            class="inline-flex items-center gap-2 px-8 py-4 bg-white text-fps-navy font-semibold rounded-lg hover:bg-blue-50 transition-colors"
          >
            <Mail class="w-5 h-5" />
            Contact Us
          </NuxtLink>
          <a
            href="/sponsorship-package.pdf"
            class="inline-flex items-center gap-2 px-8 py-4 border-2 border-white text-white font-semibold rounded-lg hover:bg-white/10 transition-colors"
          >
            <Download class="w-5 h-5" />
            Download Package
          </a>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { Calendar, Award, Gift, Users, Mail, Download } from "lucide-vue-next";

useHead({ title: "Sponsors & Partners" });

const sponsorshipOpportunities = [
  {
    title: "Event Sponsorship",
    description:
      "Sponsor specific events like our Winter Ball, Golf Tournament, or community gatherings.",
    icon: Calendar,
  },
  {
    title: "Annual Sponsorship",
    description:
      "Become a year-round partner with recognition across all FPS programs and events.",
    icon: Award,
  },
  {
    title: "In-Kind Contributions",
    description:
      "Support us with products, services, or venues that help our programs succeed.",
    icon: Gift,
  },
  {
    title: "Community Partnerships",
    description:
      "Collaborate on initiatives that benefit both our organizations and the community.",
    icon: Users,
  },
];

const sponsors = [
  {
    name: "MedCorp Solutions",
    logo: "https://placehold.co/600x400",
    website: "https://example.com",
  },
  {
    name: "SafeGuard Insurance",
    logo: "https://placehold.co/600x400",
    website: "https://example.com",
  },
  {
    name: "First Response Equipment",
    logo: "https://placehold.co/600x400",
    website: "https://example.com",
  },
  {
    name: "Valley Health Systems",
    logo: "https://placehold.co/600x400",
    website: "https://example.com",
  },
  {
    name: "Emergency Transport Co.",
    logo: "https://placehold.co/600x400",
    website: "https://example.com",
  },
  {
    name: "Community Bank",
    logo: "https://placehold.co/600x400",
    website: "https://example.com",
  },
  {
    name: "Paramedic Supplies Ltd.",
    logo: "https://placehold.co/600x400",
    website: "https://example.com",
  },
  {
    name: "Wellness Centre BC",
    logo: "https://placehold.co/600x400",
    website: "https://example.com",
  },
];
</script>
