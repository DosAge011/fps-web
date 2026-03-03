<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Contact Us
        </h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">
          We'd love to hear from you. Reach out with questions, partnership
          inquiries, or just to say hello.
        </p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="grid lg:grid-cols-2 gap-12 lg:gap-16">
          <div>
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
              >Send a Message</span
            >
            <h2 class="text-2xl sm:text-3xl font-bold text-fps-navy mb-6">
              Get in Touch
            </h2>

            <form @submit.prevent="handleSubmit" class="space-y-5">
              <div class="grid sm:grid-cols-2 gap-5">
                <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2"
                    >First Name</label
                  >
                  <input
                    v-model="form.firstName"
                    type="text"
                    required
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
                    placeholder="John"
                  />
                </div>
                <div>
                  <label class="block text-sm font-medium text-gray-700 mb-2"
                    >Last Name</label
                  >
                  <input
                    v-model="form.lastName"
                    type="text"
                    required
                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
                    placeholder="Doe"
                  />
                </div>
              </div>
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-2"
                  >Email Address</label
                >
                <div class="relative">
                  <Mail
                    class="absolute left-3 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400"
                  />
                  <input
                    v-model="form.email"
                    type="email"
                    required
                    class="w-full pl-10 pr-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
                    placeholder="you@example.com"
                  />
                </div>
              </div>
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-2"
                  >Subject</label
                >
                <select
                  v-model="form.subject"
                  required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
                >
                  <option value="">Select a subject</option>
                  <option value="general">General Inquiry</option>
                  <option value="membership">Membership</option>
                  <option value="volunteer">Volunteering</option>
                  <option value="sponsorship">Sponsorship</option>
                  <option value="events">Events</option>
                  <option value="donation">Donation</option>
                  <option value="other">Other</option>
                </select>
              </div>
              <div>
                <label class="block text-sm font-medium text-gray-700 mb-2"
                  >Message</label
                >
                <textarea
                  v-model="form.message"
                  rows="5"
                  required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none resize-none"
                  placeholder="How can we help you?"
                ></textarea>
              </div>
              <button
                type="submit"
                :disabled="isSubmitting"
                class="w-full btn-primary py-3 disabled:opacity-50"
              >
                <Loader2
                  v-if="isSubmitting"
                  class="w-5 h-5 animate-spin mr-2"
                />
                <Send v-else class="w-5 h-5 mr-2" />
                {{ isSubmitting ? "Sending..." : "Send Message" }}
              </button>
            </form>

            <div
              v-if="showSuccess"
              class="mt-6 p-4 bg-green-50 border border-green-200 rounded-lg flex items-start gap-3"
            >
              <CheckCircle
                class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
              />
              <div>
                <p class="font-medium text-green-800">Message Sent!</p>
                <p class="text-sm text-green-700">
                  Thank you for reaching out. We'll get back to you soon.
                </p>
              </div>
            </div>
          </div>

          <div>
            <span
              class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
              >Contact Information</span
            >
            <h2 class="text-2xl sm:text-3xl font-bold text-fps-navy mb-6">
              Other Ways to Connect
            </h2>

            <div class="space-y-6 mb-10">
              <div class="flex items-start gap-4">
                <div
                  class="w-12 h-12 bg-fps-navy rounded-lg flex items-center justify-center flex-shrink-0"
                >
                  <Mail class="w-6 h-6 text-white" />
                </div>
                <div>
                  <h3 class="font-bold text-fps-navy mb-1">Email</h3>
                  <a
                    href="mailto:info@fraserparamedicsociety.com"
                    class="text-gray-600 hover:text-fps-navy transition-colors"
                    >info@fraserparamedicsociety.com</a
                  >
                </div>
              </div>
              <div class="flex items-start gap-4">
                <div
                  class="w-12 h-12 bg-fps-navy rounded-lg flex items-center justify-center flex-shrink-0"
                >
                  <MapPin class="w-6 h-6 text-white" />
                </div>
                <div>
                  <h3 class="font-bold text-fps-navy mb-1">Location</h3>
                  <p class="text-gray-600">British Columbia, Canada</p>
                </div>
              </div>
            </div>

            <div>
              <h3 class="font-bold text-fps-navy mb-4">Follow Us</h3>
              <div class="flex gap-4">
                <a
                  v-for="social in socialLinks"
                  :key="social.label"
                  :href="social.href"
                  target="_blank"
                  rel="noopener"
                  class="w-12 h-12 bg-gray-100 rounded-lg flex items-center justify-center hover:bg-fps-navy hover:text-white transition-colors"
                  :aria-label="social.label"
                >
                  <component :is="social.icon" class="w-5 h-5" />
                </a>
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
  Mail,
  MapPin,
  Send,
  Loader2,
  CheckCircle,
  Facebook,
  Instagram,
  Linkedin,
} from "lucide-vue-next";

useHead({ title: "Contact" });

const route = useRoute();
const supabase = useSupabaseClient();

const form = ref({
  firstName: "",
  lastName: "",
  email: "",
  subject: route.query.subject || "",
  message: "",
});
const isSubmitting = ref(false);
const showSuccess = ref(false);

const socialLinks = [
  { label: "Facebook", href: "https://facebook.com", icon: Facebook },
  { label: "Instagram", href: "https://instagram.com", icon: Instagram },
  { label: "LinkedIn", href: "https://linkedin.com", icon: Linkedin },
];

const handleSubmit = async () => {
  isSubmitting.value = true;
  try {
    const { error } = await supabase.from("contact_messages").insert({
      first_name: form.value.firstName,
      last_name: form.value.lastName,
      email: form.value.email,
      subject: form.value.subject,
      message: form.value.message,
      created_at: new Date().toISOString(),
    });
    if (error) throw error;
    showSuccess.value = true;
    form.value = {
      firstName: "",
      lastName: "",
      email: "",
      subject: "",
      message: "",
    };
    setTimeout(() => (showSuccess.value = false), 5000);
  } catch (error) {
    console.error("Contact form error:", error);
    alert("Failed to send message. Please try again.");
  } finally {
    isSubmitting.value = false;
  }
};
</script>
