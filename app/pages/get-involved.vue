<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Get Involved
        </h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">
          There are many ways to support Fraser Paramedic Society and make a
          difference.
        </p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
          <div>
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
              >Volunteer</span
            >
            <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy mb-6">
              Be the Backbone of FPS
            </h2>
            <div class="space-y-4 text-gray-600 mb-8">
              <p>
                Volunteers are the backbone of Fraser Paramedic Society. Whether
                you're helping run an event, supporting fundraising efforts,
                reaching out to sponsors, or lending your skills to new
                initiatives, your time and energy make a direct impact.
              </p>
              <p>
                From setup and logistics to promotion and community engagement,
                there are meaningful ways for everyone to contribute.
              </p>
            </div>
            <div class="flex flex-wrap gap-3 mb-8">
              <span
                v-for="role in volunteerRoles"
                :key="role"
                class="px-4 py-2 bg-gray-100 text-gray-700 rounded-full text-sm font-medium"
                >{{ role }}</span
              >
            </div>
            <NuxtLink to="/contact?subject=Volunteer" class="btn-primary"
              >Apply to Volunteer</NuxtLink
            >
          </div>
          <div>
            <img
              src="https://placehold.co/600x400"
              alt="Volunteers at FPS event"
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
              alt="FPS members"
              class="rounded-2xl shadow-lg w-full h-[400px] object-cover"
            />
          </div>
          <div class="order-1 lg:order-2">
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
              >Membership</span
            >
            <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy mb-6">
              Become a Member
            </h2>
            <p class="text-gray-600 mb-6">
              Fraser Paramedic Society is built on connection. Whether you serve
              on the front lines, support someone who does, or simply believe in
              our mission, there is a place for you here.
            </p>
            <div class="space-y-4 mb-8">
              <div class="flex items-start gap-3">
                <div
                  class="w-6 h-6 bg-fps-navy rounded-full flex items-center justify-center flex-shrink-0 mt-0.5"
                >
                  <Check class="w-4 h-4 text-white" />
                </div>
                <div>
                  <p class="font-medium text-gray-900">Regular Member</p>
                  <p class="text-sm text-gray-600">
                    For active or retired paramedics
                  </p>
                </div>
              </div>
              <div class="flex items-start gap-3">
                <div
                  class="w-6 h-6 bg-fps-navy rounded-full flex items-center justify-center flex-shrink-0 mt-0.5"
                >
                  <Check class="w-4 h-4 text-white" />
                </div>
                <div>
                  <p class="font-medium text-gray-900">Allied Member</p>
                  <p class="text-sm text-gray-600">
                    For family members and allied professionals
                  </p>
                </div>
              </div>
              <div class="flex items-start gap-3">
                <div
                  class="w-6 h-6 bg-fps-navy rounded-full flex items-center justify-center flex-shrink-0 mt-0.5"
                >
                  <Check class="w-4 h-4 text-white" />
                </div>
                <div>
                  <p class="font-medium text-gray-900">Community Supporter</p>
                  <p class="text-sm text-gray-600">
                    For community members and businesses
                  </p>
                </div>
              </div>
            </div>
            <NuxtLink to="/membership" class="btn-primary">Join FPS</NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-fps-navy">
      <div class="max-w-4xl mx-auto container-padding text-center">
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-6">
          Every Contribution Matters
        </h2>
        <p class="text-lg text-blue-100 mb-8 max-w-2xl mx-auto">
          Whether you volunteer your time, become a member, or support us
          financially, you're helping build a stronger, more connected paramedic
          community.
        </p>
        <div class="flex flex-wrap justify-center gap-4">
          <NuxtLink
            to="/donate"
            class="inline-flex items-center gap-2 px-8 py-4 bg-white text-fps-navy font-semibold rounded-lg hover:bg-blue-50 transition-colors"
          >
            <Heart class="w-5 h-5" />
            Donate
          </NuxtLink>
          <NuxtLink
            to="/contact"
            class="inline-flex items-center gap-2 px-8 py-4 border-2 border-white text-white font-semibold rounded-lg hover:bg-white/10 transition-colors"
          >
            <Mail class="w-5 h-5" />
            Contact Us
          </NuxtLink>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import { Check, Heart, Mail } from "lucide-vue-next";

useHead({ title: "Get Involved" });

const volunteerRoles = [
  "Event Support",
  "Fundraising",
  "Sponsor Outreach",
  "Communications",
  "Logistics",
  "Community Engagement",
];
</script>
