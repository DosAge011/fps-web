<template>
  <div>
    <section class="relative h-[50vh] min-h-[400px]">
      <img
        :src="event.image"
        :alt="event.title"
        class="absolute inset-0 w-full h-full object-cover"
      />
      <div
        class="absolute inset-0 bg-gradient-to-t from-fps-navy/90 via-fps-navy/50 to-transparent"
      ></div>
      <div class="absolute bottom-0 left-0 right-0">
        <div class="max-w-7xl mx-auto container-padding py-12">
          <NuxtLink
            to="/events"
            class="inline-flex items-center gap-2 text-white/80 hover:text-white mb-4"
          >
            <ArrowLeft class="w-4 h-4" />
            Back to Events
          </NuxtLink>
          <h1
            class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4"
          >
            {{ event.title }}
          </h1>
          <div class="flex flex-wrap gap-4 text-white/90">
            <div class="flex items-center gap-2">
              <Calendar class="w-5 h-5" /> {{ event.date }}
            </div>
            <div class="flex items-center gap-2">
              <Clock class="w-5 h-5" /> {{ event.time }}
            </div>
            <div class="flex items-center gap-2">
              <MapPin class="w-5 h-5" /> {{ event.location }}
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid lg:grid-cols-3 gap-12">
          <div class="lg:col-span-2">
            <h2 class="text-2xl font-bold text-fps-navy mb-4">
              About This Event
            </h2>
            <div class="prose prose-lg text-gray-600 mb-8">
              <p
                v-for="(paragraph, index) in event.description"
                :key="index"
                class="mb-4"
              >
                {{ paragraph }}
              </p>
            </div>

            <h3 class="text-xl font-bold text-fps-navy mb-4">What to Expect</h3>
            <ul class="space-y-3 mb-8">
              <li
                v-for="(item, index) in event.whatToExpect"
                :key="index"
                class="flex items-start gap-3"
              >
                <div
                  class="w-6 h-6 bg-fps-navy rounded-full flex items-center justify-center flex-shrink-0 mt-0.5"
                >
                  <Check class="w-4 h-4 text-white" />
                </div>
                <span class="text-gray-700">{{ item }}</span>
              </li>
            </ul>

            <div
              v-if="event.sponsors && event.sponsors.length > 0"
              class="mb-8"
            >
              <h3 class="text-xl font-bold text-fps-navy mb-4">
                Event Sponsors
              </h3>
              <div class="flex flex-wrap gap-4">
                <div
                  v-for="sponsor in event.sponsors"
                  :key="sponsor.name"
                  class="bg-gray-50 rounded-lg p-4 flex items-center gap-3"
                >
                  <img
                    :src="sponsor.logo"
                    :alt="sponsor.name"
                    class="w-12 h-12 object-contain"
                  />
                  <span class="font-medium text-gray-700">{{
                    sponsor.name
                  }}</span>
                </div>
              </div>
            </div>
          </div>

          <div class="lg:col-span-1">
            <div class="bg-gray-50 rounded-2xl p-6 sticky top-24">
              <div class="mb-6">
                <p class="text-sm text-gray-500 mb-1">Date & Time</p>
                <p class="font-semibold text-fps-navy">{{ event.date }}</p>
                <p class="text-gray-700">{{ event.time }}</p>
              </div>
              <div class="mb-6">
                <p class="text-sm text-gray-500 mb-1">Location</p>
                <p class="font-semibold text-fps-navy">{{ event.location }}</p>
                <p class="text-gray-700">{{ event.address }}</p>
              </div>
              <div class="mb-6">
                <p class="text-sm text-gray-500 mb-1">Registration Fee</p>
                <p class="font-semibold text-fps-navy">{{ event.price }}</p>
              </div>
              <button
                v-if="event.status === 'upcoming'"
                @click="showRegistration = true"
                class="w-full btn-primary py-3 mb-4"
              >
                Register Now
              </button>
              <div
                v-else
                class="w-full py-3 px-4 bg-gray-200 text-gray-500 text-center rounded-lg font-medium"
              >
                Registration Closed
              </div>
              <div class="pt-4 border-t border-gray-200">
                <p class="text-sm text-gray-500 mb-2">Refund Policy</p>
                <p class="text-sm text-gray-600">{{ event.refundPolicy }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <div
      v-if="showRegistration"
      class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/50"
      @click.self="showRegistration = false"
    >
      <div
        class="bg-white rounded-2xl max-w-md w-full p-6 max-h-[90vh] overflow-y-auto"
      >
        <div class="flex items-center justify-between mb-6">
          <h3 class="text-xl font-bold text-fps-navy">
            Register for {{ event.title }}
          </h3>
          <button
            @click="showRegistration = false"
            class="text-gray-400 hover:text-gray-600"
          >
            <X class="w-6 h-6" />
          </button>
        </div>
        <form @submit.prevent="handleRegistration" class="space-y-4">
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1"
              >Full Name</label
            >
            <input
              v-model="registrationForm.name"
              type="text"
              required
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
            />
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1"
              >Email</label
            >
            <input
              v-model="registrationForm.email"
              type="email"
              required
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
            />
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1"
              >Phone</label
            >
            <input
              v-model="registrationForm.phone"
              type="tel"
              required
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
            />
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1"
              >Number of Guests</label
            >
            <select
              v-model="registrationForm.guests"
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
            >
              <option v-for="n in 5" :key="n" :value="n">{{ n }}</option>
            </select>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1"
              >Dietary Restrictions</label
            >
            <textarea
              v-model="registrationForm.dietary"
              rows="2"
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
              placeholder="Any allergies or dietary needs?"
            ></textarea>
          </div>
          <label class="flex items-start gap-2">
            <input
              v-model="registrationForm.agree"
              type="checkbox"
              required
              class="w-4 h-4 mt-1 text-fps-navy border-gray-300 rounded focus:ring-fps-navy"
            />
            <span class="text-sm text-gray-600"
              >I agree to the event terms and conditions</span
            >
          </label>
          <button
            type="submit"
            :disabled="isRegistering"
            class="w-full btn-primary py-3 disabled:opacity-50"
          >
            <Loader2 v-if="isRegistering" class="w-5 h-5 animate-spin mr-2" />
            {{ isRegistering ? "Processing..." : "Complete Registration" }}
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  ArrowLeft,
  Calendar,
  Clock,
  MapPin,
  Check,
  X,
  Loader2,
} from "lucide-vue-next";

const route = useRoute();
const showRegistration = ref(false);
const isRegistering = ref(false);
const registrationForm = ref({
  name: "",
  email: "",
  phone: "",
  guests: 1,
  dietary: "",
  agree: false,
});

const handleRegistration = async () => {
  isRegistering.value = true;
  await new Promise((resolve) => setTimeout(resolve, 1500));
  alert("Registration successful! Check your email for confirmation.");
  showRegistration.value = false;
  isRegistering.value = false;
  registrationForm.value = {
    name: "",
    email: "",
    phone: "",
    guests: 1,
    dietary: "",
    agree: false,
  };
};

const event = {
  id: route.params.id,
  title: "Winter Ball 2025",
  date: "Saturday, January 25, 2025",
  month: "JAN",
  day: "25",
  time: "6:00 PM - 11:00 PM",
  location: "Vancouver Convention Centre",
  address: "1055 Canada Place, Vancouver, BC V6C 0C3",
  price: "$75 per person",
  status: "upcoming",
  image: "https://placehold.co/600x400",
  description: [
    "Join us for an evening of celebration, connection, and community at the Fraser Paramedic Society Winter Ball 2025.",
    "The evening will feature a gourmet dinner, live entertainment, dancing, and opportunities to connect with colleagues.",
    "All proceeds support FPS programs and initiatives that strengthen morale and build community.",
  ],
  whatToExpect: [
    "Cocktail reception with hors d'oeuvres",
    "Three-course gourmet dinner",
    "Live band and dancing",
    "Silent auction with exciting prizes",
    "Recognition of outstanding paramedics",
    "Networking opportunities",
  ],
  sponsors: [
    { name: "MedCorp", logo: "https://placehold.co/100x50" },
    { name: "SafeGuard Insurance", logo: "https://placehold.co/100x50" },
  ],
  refundPolicy:
    "Full refunds available up to 7 days before the event. 50% refund up to 48 hours before. No refunds within 48 hours of the event.",
};

useHead({ title: event.title });
</script>
