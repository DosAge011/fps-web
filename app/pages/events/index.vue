<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Events
        </h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">
          Fraser Paramedic Society hosts events designed to bring paramedics,
          families, and supporters together.
        </p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="flex flex-wrap justify-center gap-2 mb-12">
          <button
            v-for="filter in filters"
            :key="filter.value"
            @click="activeFilter = filter.value"
            class="px-6 py-2 rounded-full text-sm font-medium transition-colors"
            :class="
              activeFilter === filter.value
                ? 'bg-fps-navy text-white'
                : 'bg-gray-100 text-gray-700 hover:bg-gray-200'
            "
          >
            {{ filter.label }}
          </button>
        </div>

        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
          <div
            v-for="event in filteredEvents"
            :key="event.id"
            class="group bg-white border border-gray-200 rounded-2xl overflow-hidden hover:shadow-lg transition-shadow"
          >
            <div class="relative h-56 overflow-hidden">
              <img
                :src="event.image"
                :alt="event.title"
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-300"
              />
              <div
                class="absolute top-4 left-4 bg-white rounded-lg px-3 py-2 text-center shadow-sm"
              >
                <p class="text-xs text-gray-500 uppercase">{{ event.month }}</p>
                <p class="text-xl font-bold text-fps-navy">{{ event.day }}</p>
              </div>
              <div
                class="absolute top-4 right-4 px-3 py-1 rounded-full text-xs font-medium"
                :class="
                  event.status === 'upcoming'
                    ? 'bg-green-100 text-green-700'
                    : 'bg-gray-100 text-gray-700'
                "
              >
                {{ event.status === "upcoming" ? "Upcoming" : "Past" }}
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-lg font-bold text-fps-navy mb-2">
                {{ event.title }}
              </h3>
              <div class="flex items-center gap-2 text-gray-500 text-sm mb-2">
                <MapPin class="w-4 h-4" />
                {{ event.location }}
              </div>
              <div class="flex items-center gap-2 text-gray-500 text-sm mb-3">
                <Clock class="w-4 h-4" />
                {{ event.time }}
              </div>
              <p class="text-gray-600 text-sm mb-4 line-clamp-2">
                {{ event.description }}
              </p>
              <NuxtLink
                :to="`/events/${event.id}`"
                class="inline-flex items-center gap-2 text-fps-navy font-medium text-sm hover:gap-3 transition-all"
              >
                {{
                  event.status === "upcoming" ? "Register Now" : "View Details"
                }}
                <ArrowRight class="w-4 h-4" />
              </NuxtLink>
            </div>
          </div>
        </div>

        <div v-if="filteredEvents.length === 0" class="text-center py-16">
          <Calendar class="w-16 h-16 text-gray-300 mx-auto mb-4" />
          <h3 class="text-xl font-semibold text-gray-700 mb-2">
            No events found
          </h3>
          <p class="text-gray-500">Check back soon for upcoming events.</p>
        </div>
      </div>
    </section>

    <section class="section-padding bg-gray-50">
      <div class="max-w-4xl mx-auto container-padding text-center">
        <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy mb-6">
          Want to Partner on an Event?
        </h2>
        <p class="text-lg text-gray-600 mb-8 max-w-2xl mx-auto">
          We're always looking for organizations and businesses to collaborate
          with.
        </p>
        <NuxtLink to="/sponsors" class="btn-primary">Become a Sponsor</NuxtLink>
      </div>
    </section>
  </div>
</template>

<script setup>
import { MapPin, Clock, ArrowRight, Calendar } from "lucide-vue-next";

useHead({ title: "Events" });

const activeFilter = ref("all");
const filters = [
  { label: "All Events", value: "all" },
  { label: "Upcoming", value: "upcoming" },
  { label: "Past Events", value: "past" },
];

const events = [
  {
    id: 1,
    title: "Winter Ball 2025",
    month: "JAN",
    day: "25",
    location: "Vancouver Convention Centre",
    time: "6:00 PM - 11:00 PM",
    description:
      "Join us for an evening of celebration, connection, and community.",
    image: "https://placehold.co/600x400",
    status: "upcoming",
  },
  {
    id: 2,
    title: "Peer Connection Night",
    month: "FEB",
    day: "14",
    location: "Fraser Valley Community Center",
    time: "7:00 PM - 9:00 PM",
    description:
      "An informal gathering for paramedics to connect and share experiences.",
    image: "https://placehold.co/600x400",
    status: "upcoming",
  },
  {
    id: 3,
    title: "Spring Golf Tournament",
    month: "MAR",
    day: "22",
    location: "Burnaby Mountain Golf Course",
    time: "8:00 AM - 4:00 PM",
    description: "Our annual charity golf tournament supports FPS programs.",
    image: "https://placehold.co/600x400",
    status: "upcoming",
  },
  {
    id: 4,
    title: "Family Fun Day",
    month: "APR",
    day: "12",
    location: "Stanley Park",
    time: "10:00 AM - 3:00 PM",
    description: "A day of activities for paramedic families to connect.",
    image: "https://placehold.co/600x400",
    status: "upcoming",
  },
  {
    id: 5,
    title: "Fall Gala 2024",
    month: "NOV",
    day: "15",
    location: "Richmond Ballroom",
    time: "6:00 PM - 11:00 PM",
    description: "Our annual fall celebration honoring paramedics.",
    image: "https://placehold.co/600x400",
    status: "past",
  },
  {
    id: 6,
    title: "Summer BBQ",
    month: "AUG",
    day: "10",
    location: "Burnaby Lake Park",
    time: "12:00 PM - 5:00 PM",
    description: "A casual summer gathering for paramedics and their families.",
    image: "https://placehold.co/600x400",
    status: "past",
  },
];

const filteredEvents = computed(() =>
  activeFilter.value === "all"
    ? events
    : events.filter((event) => event.status === activeFilter.value),
);
</script>
