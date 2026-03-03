<template>
  <div>
    <!-- Hero Section -->
    <section
      class="relative min-h-[90vh] flex items-center bg-gradient-to-br from-fps-navy via-fps-navy to-fps-blue overflow-hidden"
    >
      <!-- Background Pattern -->
      <div class="absolute inset-0 opacity-10">
        <div
          class="absolute inset-0"
          style="
            background-image: radial-gradient(
              circle at 2px 2px,
              white 1px,
              transparent 0
            );
            background-size: 40px 40px;
          "
        ></div>
      </div>

      <div class="relative max-w-7xl mx-auto container-padding py-20 lg:py-32">
        <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
          <div class="text-white">
            <h1
              class="text-4xl sm:text-5xl lg:text-6xl font-bold leading-tight mb-6"
            >
              Boosting Morale,<br />
              <span class="text-blue-300">Strengthening Camaraderie.</span>
            </h1>
            <p class="text-lg sm:text-xl text-blue-100 mb-8 max-w-xl">
              Fraser Paramedic Society strengthens morale, builds community, and
              supports paramedics and first responders across the Lower Mainland
              and Fraser Valley.
            </p>
            <div class="flex flex-wrap gap-4">
              <NuxtLink
                to="/donate"
                class="inline-flex items-center gap-2 px-8 py-4 bg-white text-fps-navy font-semibold rounded-lg hover:bg-blue-50 transition-colors"
              >
                <Heart class="w-5 h-5" />
                Donate
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
          <div class="relative hidden lg:block">
            <div class="relative rounded-2xl overflow-hidden shadow-2xl">
              <img
                src="https://placehold.co/600x400"
                alt="Paramedics in action"
                class="w-full h-[500px] object-cover"
              />
              <div
                class="absolute inset-0 bg-gradient-to-t from-fps-navy/60 to-transparent"
              ></div>
            </div>
            <!-- Floating Stats Card -->
            <div
              class="absolute -bottom-6 -left-6 bg-white rounded-xl shadow-xl p-6"
            >
              <div class="flex items-center gap-4">
                <div
                  class="w-12 h-12 bg-fps-navy rounded-lg flex items-center justify-center"
                >
                  <Users class="w-6 h-6 text-white" />
                </div>
                <div>
                  <p class="text-2xl font-bold text-fps-navy">500+</p>
                  <p class="text-sm text-gray-600">Members Supported</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Who We Are Section -->
    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid lg:grid-cols-2 gap-12 lg:gap-16 items-center">
          <div class="order-2 lg:order-1">
            <div class="relative">
              <img
                src="https://placehold.co/600x400"
                alt="FPS community event"
                class="rounded-2xl shadow-lg w-full h-[400px] object-cover"
              />
              <div
                class="absolute -bottom-4 -right-4 w-24 h-24 bg-fps-navy rounded-xl flex items-center justify-center"
              >
                <Award class="w-12 h-12 text-white" />
              </div>
            </div>
          </div>
          <div class="order-1 lg:order-2">
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
            >
              Who We Are
            </span>
            <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy mb-6">
              By Paramedics. For Paramedics.
            </h2>
            <div class="space-y-4 text-gray-600">
              <p>
                Fraser Paramedic Society (FPS) is a British Columbia–based
                nonprofit organization dedicated to supporting paramedics and
                first responders. We exist to strengthen morale, foster
                connection, and build a healthier, more resilient emergency
                services community.
              </p>
              <p>
                From peer connection initiatives to community events and
                programming, FPS focuses on what matters most: people.
              </p>
            </div>
            <NuxtLink
              to="/about"
              class="inline-flex items-center gap-2 mt-6 text-fps-navy font-semibold hover:gap-3 transition-all"
            >
              Learn More About Us
              <ArrowRight class="w-5 h-5" />
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <!-- What We Do Section -->
    <section class="section-padding bg-gray-50">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="text-center mb-12">
          <span
            class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
          >
            Our Impact
          </span>
          <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy">
            How We Make an Impact
          </h2>
        </div>

        <div class="grid md:grid-cols-3 gap-8">
          <div
            class="bg-white rounded-2xl p-8 shadow-sm hover:shadow-lg transition-shadow"
          >
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-6"
            >
              <Users2 class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-xl font-bold text-fps-navy mb-3">
              Morale & Community
            </h3>
            <p class="text-gray-600">
              We create events and experiences that bring paramedics together —
              building connection, pride, and belonging.
            </p>
          </div>
          <div
            class="bg-white rounded-2xl p-8 shadow-sm hover:shadow-lg transition-shadow"
          >
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-6"
            >
              <UserCircle class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-xl font-bold text-fps-navy mb-3">Family Support</h3>
            <p class="text-gray-600">
              We recognize that paramedic families serve too. Our programs aim
              to include and support those behind the scenes.
            </p>
          </div>
          <div
            class="bg-white rounded-2xl p-8 shadow-sm hover:shadow-lg transition-shadow"
          >
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-6"
            >
              <Globe class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-xl font-bold text-fps-navy mb-3">
              Community Initiatives
            </h3>
            <p class="text-gray-600">
              From public engagement to educational projects, FPS strengthens
              the connection between paramedics and the communities they serve.
            </p>
          </div>
        </div>

        <div class="text-center mt-10">
          <NuxtLink to="/programs" class="btn-primary"> Learn More </NuxtLink>
        </div>
      </div>
    </section>

    <!-- Upcoming Events Section -->
    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div
          class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4 mb-12"
        >
          <div>
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
            >
              Events
            </span>
            <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy">
              Upcoming Events
            </h2>
          </div>
          <NuxtLink
            to="/events"
            class="inline-flex items-center gap-2 text-fps-navy font-semibold hover:gap-3 transition-all"
          >
            View All Events
            <ArrowRight class="w-5 h-5" />
          </NuxtLink>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            class="group bg-white border border-gray-200 rounded-2xl overflow-hidden hover:shadow-lg transition-shadow"
          >
            <div class="relative h-48 overflow-hidden">
              <img
                src="https://placehold.co/600x400"
                alt="Winter Ball"
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
              />
              <div
                class="absolute top-4 left-4 bg-white rounded-lg px-3 py-2 text-center"
              >
                <p class="text-xs text-gray-500 uppercase">JAN</p>
                <p class="text-xl font-bold text-fps-navy">25</p>
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-lg font-bold text-fps-navy mb-2">
                Winter Ball 2025
              </h3>
              <div class="flex items-center gap-2 text-gray-500 text-sm mb-3">
                <MapPin class="w-4 h-4" />
                Vancouver Convention Centre
              </div>
              <p class="text-gray-600 text-sm mb-4 line-clamp-2">
                Join us for an evening of celebration, connection, and
                community. Our annual Winter Ball brings together paramedics and
                supporters.
              </p>
              <NuxtLink
                to="/events/1"
                class="inline-flex items-center gap-2 text-fps-navy font-medium text-sm hover:gap-3 transition-all"
              >
                Register
                <ArrowRight class="w-4 h-4" />
              </NuxtLink>
            </div>
          </div>

          <div
            class="group bg-white border border-gray-200 rounded-2xl overflow-hidden hover:shadow-lg transition-shadow"
          >
            <div class="relative h-48 overflow-hidden">
              <img
                src="https://placehold.co/600x400"
                alt="Peer Connection Night"
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
              />
              <div
                class="absolute top-4 left-4 bg-white rounded-lg px-3 py-2 text-center"
              >
                <p class="text-xs text-gray-500 uppercase">FEB</p>
                <p class="text-xl font-bold text-fps-navy">14</p>
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-lg font-bold text-fps-navy mb-2">
                Peer Connection Night
              </h3>
              <div class="flex items-center gap-2 text-gray-500 text-sm mb-3">
                <MapPin class="w-4 h-4" />
                Fraser Valley Community Center
              </div>
              <p class="text-gray-600 text-sm mb-4 line-clamp-2">
                An informal gathering for paramedics to connect, share
                experiences, and build supportive relationships.
              </p>
              <NuxtLink
                to="/events/2"
                class="inline-flex items-center gap-2 text-fps-navy font-medium text-sm hover:gap-3 transition-all"
              >
                Register
                <ArrowRight class="w-4 h-4" />
              </NuxtLink>
            </div>
          </div>

          <div
            class="group bg-white border border-gray-200 rounded-2xl overflow-hidden hover:shadow-lg transition-shadow"
          >
            <div class="relative h-48 overflow-hidden">
              <img
                src="https://placehold.co/600x400"
                alt="Golf Tournament"
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
              />
              <div
                class="absolute top-4 left-4 bg-white rounded-lg px-3 py-2 text-center"
              >
                <p class="text-xs text-gray-500 uppercase">MAR</p>
                <p class="text-xl font-bold text-fps-navy">22</p>
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-lg font-bold text-fps-navy mb-2">
                Spring Golf Tournament
              </h3>
              <div class="flex items-center gap-2 text-gray-500 text-sm mb-3">
                <MapPin class="w-4 h-4" />
                Burnaby Mountain Golf Course
              </div>
              <p class="text-gray-600 text-sm mb-4 line-clamp-2">
                Our annual charity golf tournament supports FPS programs while
                providing a day of relaxation and networking.
              </p>
              <NuxtLink
                to="/events/3"
                class="inline-flex items-center gap-2 text-fps-navy font-medium text-sm hover:gap-3 transition-all"
              >
                Register
                <ArrowRight class="w-4 h-4" />
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="section-padding bg-fps-navy">
      <div class="max-w-4xl mx-auto container-padding text-center">
        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-6">
          Stand With Those Who Stand for You.
        </h2>
        <p class="text-lg text-blue-100 mb-8 max-w-2xl mx-auto">
          Your support helps us strengthen morale, build connection, and invest
          in the wellbeing of paramedics and first responders.
        </p>
        <NuxtLink
          to="/donate"
          class="inline-flex items-center gap-2 px-8 py-4 bg-white text-fps-navy font-semibold rounded-lg hover:bg-blue-50 transition-colors"
        >
          <Heart class="w-5 h-5" />
          Donate Today
        </NuxtLink>
      </div>
    </section>
  </div>
</template>

<script setup>
import {
  Heart,
  Users,
  ArrowRight,
  Award,
  MapPin,
  Users2,
  UserCircle,
  Globe,
} from "lucide-vue-next";

useHead({
  title: "Home",
});
</script>
