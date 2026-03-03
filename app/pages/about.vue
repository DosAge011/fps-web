<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          About FPS
        </h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">
          Learn about our mission, vision, and the people behind Fraser
          Paramedic Society.
        </p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
          <div>
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
              >Our Story</span
            >
            <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy mb-6">
              Built by Paramedics, for Paramedics
            </h2>
            <div class="space-y-4 text-gray-600">
              <p>
                Fraser Paramedic Society was founded by paramedics who saw a
                need for stronger connection, higher morale, and better support
                within the profession.
              </p>
              <p>
                Emergency services work is demanding. Behind every uniform is a
                human being navigating pressure, trauma, and responsibility. FPS
                was built to support that human side of the job.
              </p>
            </div>
          </div>
          <div>
            <img
              src="https://placehold.co/600x400"
              alt="FPS founding story"
              class="rounded-2xl shadow-lg w-full h-[400px] object-cover"
            />
          </div>
        </div>
      </div>
    </section>

    <section id="mission" class="section-padding bg-gray-50">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid md:grid-cols-2 gap-8 lg:gap-12">
          <div class="bg-white rounded-2xl p-8 lg:p-10 shadow-sm">
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-6"
            >
              <Target class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-2xl font-bold text-fps-navy mb-4">Our Mission</h3>
            <p class="text-gray-600">
              To support paramedics and first responders, strengthen morale and
              community, and lead initiatives that benefit both emergency
              workers and the public.
            </p>
          </div>
          <div class="bg-white rounded-2xl p-8 lg:p-10 shadow-sm">
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-6"
            >
              <Eye class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-2xl font-bold text-fps-navy mb-4">Our Vision</h3>
            <p class="text-gray-600">
              A connected, resilient paramedic community where no one stands
              alone.
            </p>
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="text-center mb-12">
          <span
            class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
            >What We Stand For</span
          >
          <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy">
            Our Values
          </h2>
        </div>
        <div class="grid sm:grid-cols-2 lg:grid-cols-5 gap-6">
          <div
            v-for="value in values"
            :key="value.name"
            class="text-center p-6 bg-gray-50 rounded-2xl"
          >
            <div
              class="w-12 h-12 bg-fps-navy rounded-lg flex items-center justify-center mx-auto mb-4"
            >
              <component :is="value.icon" class="w-6 h-6 text-white" />
            </div>
            <h3 class="font-bold text-fps-navy">{{ value.name }}</h3>
          </div>
        </div>
      </div>
    </section>

    <section id="leadership" class="section-padding bg-gray-50">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="text-center mb-12">
          <span
            class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
            >Our Team</span
          >
          <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy">
            Leadership
          </h2>
          <p class="text-gray-600 mt-4 max-w-2xl mx-auto">
            Meet the dedicated individuals guiding Fraser Paramedic Society.
          </p>
        </div>
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="member in boardMembers"
            :key="member.name"
            class="bg-white rounded-2xl overflow-hidden shadow-sm hover:shadow-lg transition-shadow"
          >
            <div class="aspect-square bg-gray-200">
              <img
                :src="member.photo"
                :alt="member.name"
                class="w-full h-full object-cover"
              />
            </div>
            <div class="p-6">
              <h3 class="text-lg font-bold text-fps-navy">{{ member.name }}</h3>
              <p class="text-fps-blue font-medium text-sm mb-3">
                {{ member.title }}
              </p>
              <p class="text-gray-600 text-sm">{{ member.bio }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="transparency" class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="bg-fps-navy rounded-2xl p-8 lg:p-12 text-white">
          <div class="grid lg:grid-cols-2 gap-8 items-center">
            <div>
              <div
                class="w-14 h-14 bg-white/10 rounded-xl flex items-center justify-center mb-6"
              >
                <Shield class="w-7 h-7 text-white" />
              </div>
              <h2 class="text-2xl sm:text-3xl font-bold mb-4">
                Financial Transparency
              </h2>
              <p class="text-blue-100 mb-6">
                Fraser Paramedic Society is committed to financial transparency
                and responsible stewardship of all funds received.
              </p>
              <NuxtLink
                to="/transparency"
                class="inline-flex items-center gap-2 text-white font-medium hover:gap-3 transition-all"
              >
                View Financial Reports
                <ArrowRight class="w-5 h-5" />
              </NuxtLink>
            </div>
            <div class="grid grid-cols-2 gap-4">
              <div class="bg-white/10 rounded-xl p-6 text-center">
                <p class="text-3xl font-bold">85%</p>
                <p class="text-sm text-blue-100">Programs & Services</p>
              </div>
              <div class="bg-white/10 rounded-xl p-6 text-center">
                <p class="text-3xl font-bold">15%</p>
                <p class="text-sm text-blue-100">Administration</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import {
  Target,
  Eye,
  Shield,
  ArrowRight,
  Scale,
  Heart,
  Users,
  Handshake,
  Award,
} from "lucide-vue-next";

useHead({ title: "About" });

const values = [
  { name: "Integrity", icon: Scale },
  { name: "Service", icon: Heart },
  { name: "Community", icon: Users },
  { name: "Respect", icon: Handshake },
  { name: "Accountability", icon: Award },
];

const boardMembers = [
  {
    name: "Chris Michel",
    title: "President",
    bio: "Chris is a paramedic and community leader committed to strengthening morale and connection within emergency services.",
    photo: "/img/profile_m.jpg",
  },
  {
    name: "Sarah Thompson",
    title: "Vice President",
    bio: "Sarah brings extensive experience in healthcare administration and a passion for supporting first responder wellness.",
    photo: "/img/profile_f.jpg",
  },
  {
    name: "Michael Chen",
    title: "Treasurer",
    bio: "Michael is a finance professional with a background in nonprofit management.",
    photo: "/img/profile_m.jpg",
  },
  {
    name: "Jennifer Walsh",
    title: "Secretary",
    bio: "Jennifer is a paramedic with a dedication to peer support and mental health advocacy.",
    photo: "/img/profile_f.jpg",
  },
  {
    name: "David Park",
    title: "Director of Programs",
    bio: "David leads the development and execution of FPS events and initiatives.",
    photo: "/img/profile_m.jpg",
  },
  {
    name: "Emily Rodriguez",
    title: "Director of Community Relations",
    bio: "Emily manages partnerships with sponsors and community organizations.",
    photo: "/img/profile_f.jpg",
  },
];
</script>
