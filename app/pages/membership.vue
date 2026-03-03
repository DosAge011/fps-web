<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">
          Membership
        </h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">
          Join Fraser Paramedic Society and be part of a community that believes
          connection matters.
        </p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-4xl mx-auto container-padding text-center">
        <p class="text-lg text-gray-600 leading-relaxed">
          Fraser Paramedic Society is powered by people who believe connection
          matters. Our membership brings together paramedics, families, allied
          professionals, and community supporters.
        </p>
        <p class="text-lg text-gray-600 leading-relaxed mt-4">
          When you join FPS, you're not just signing up for events. You're
          adding your voice, your energy, and your support to a growing network
          committed to standing behind those who answer the call.
        </p>
      </div>
    </section>

    <section class="section-padding bg-gray-50">
      <div class="max-w-7xl mx-auto container-padding">
        <div class="text-center mb-12">
          <span
            class="inline-block px-4 py-1 bg-blue-100 text-fps-navy text-sm font-medium rounded-full mb-4"
            >Membership Options</span
          >
          <h2 class="text-3xl sm:text-4xl font-bold text-fps-navy">
            Choose Your Membership
          </h2>
        </div>
        <div class="grid lg:grid-cols-3 gap-8">
          <div
            class="bg-white rounded-2xl p-8 shadow-sm border-2 border-fps-navy"
          >
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-4"
            >
              <UserCheck class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-xl font-bold text-fps-navy mb-2">Regular Member</h3>
            <p class="text-sm text-fps-blue font-medium mb-4">
              For active or retired paramedics
            </p>
            <p class="text-gray-600 text-sm mb-6">
              Regular Members form the core of FPS. This category ensures the
              organization remains grounded in the profession.
            </p>
            <ul class="space-y-3 mb-8">
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700">Full voting rights</span>
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Eligible for board positions</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Member pricing on events</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Early event registration</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Member-only gatherings</span
                >
              </li>
            </ul>
            <button
              @click="joinMembership('regular')"
              class="w-full btn-primary"
            >
              Become a Regular Member
            </button>
          </div>

          <div class="bg-white rounded-2xl p-8 shadow-sm">
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-4"
            >
              <Users class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-xl font-bold text-fps-navy mb-2">Allied Member</h3>
            <p class="text-sm text-fps-blue font-medium mb-4">
              For family & allied professionals
            </p>
            <p class="text-gray-600 text-sm mb-6">
              Allied Members strengthen the network around paramedics. This
              category recognizes the role families play.
            </p>
            <ul class="space-y-3 mb-8">
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Voting rights at meetings</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Eligible for committee roles</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Member pricing on events</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Family-focused programming</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Volunteer opportunities</span
                >
              </li>
            </ul>
            <button
              @click="joinMembership('allied')"
              class="w-full btn-primary"
            >
              Become an Allied Member
            </button>
          </div>

          <div class="bg-white rounded-2xl p-8 shadow-sm">
            <div
              class="w-14 h-14 bg-fps-navy rounded-xl flex items-center justify-center mb-4"
            >
              <Heart class="w-7 h-7 text-white" />
            </div>
            <h3 class="text-xl font-bold text-fps-navy mb-2">
              Community Supporter
            </h3>
            <p class="text-sm text-fps-blue font-medium mb-4">
              For community members & businesses
            </p>
            <p class="text-gray-600 text-sm mb-6">
              Community Supporters help expand the reach and sustainability of
              FPS across British Columbia.
            </p>
            <ul class="space-y-3 mb-8">
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Access to public events</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Volunteer opportunities</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >FPS newsletter and updates</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Optional website recognition</span
                >
              </li>
              <li class="flex items-start gap-2">
                <Check
                  class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5"
                /><span class="text-sm text-gray-700"
                  >Select event discounts</span
                >
              </li>
            </ul>
            <button
              @click="joinMembership('community')"
              class="w-full btn-primary"
            >
              Become a Community Supporter
            </button>
          </div>
        </div>
      </div>
    </section>

    <section class="section-padding bg-fps-navy">
      <div class="max-w-4xl mx-auto container-padding text-center">
        <h2 class="text-3xl sm:text-4xl font-bold text-white mb-6">
          Why Join?
        </h2>
        <p class="text-lg text-blue-100 mb-8 leading-relaxed">
          When you join Fraser Paramedic Society, you're investing in
          connection, morale, and the wellbeing of the people who serve our
          communities every day.
        </p>
        <p class="text-xl text-white font-semibold">
          Together, we build something stronger than any one shift.
        </p>
      </div>
    </section>

    <div
      v-if="showModal"
      class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/50"
      @click.self="showModal = false"
    >
      <div
        class="bg-white rounded-2xl max-w-md w-full p-6 max-h-[90vh] overflow-y-auto"
      >
        <div class="flex items-center justify-between mb-6">
          <h3 class="text-xl font-bold text-fps-navy">Join FPS</h3>
          <button
            @click="showModal = false"
            class="text-gray-400 hover:text-gray-600"
          >
            <X class="w-6 h-6" />
          </button>
        </div>
        <div v-if="!user" class="text-center py-8">
          <User class="w-16 h-16 text-gray-300 mx-auto mb-4" />
          <h4 class="text-lg font-semibold text-gray-700 mb-2">
            Sign in Required
          </h4>
          <p class="text-gray-600 mb-6">
            Please sign in or create an account to become a member.
          </p>
          <div class="flex gap-3">
            <NuxtLink to="/auth/login" class="flex-1 btn-primary text-center"
              >Sign In</NuxtLink
            >
            <NuxtLink
              to="/auth/register"
              class="flex-1 btn-secondary text-center"
              >Register</NuxtLink
            >
          </div>
        </div>
        <form v-else @submit.prevent="submitMembership" class="space-y-4">
          <div>USER ID : {{ user.sub }}</div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1"
              >Membership Type</label
            >
            <select
              v-model="membershipForm.type"
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
            >
              <option value="regular">Regular Member</option>
              <option value="allied">Allied Member</option>
              <option value="community">Community Supporter</option>
            </select>
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1"
              >Phone Number</label
            >
            <input
              v-model="membershipForm.phone"
              type="tel"
              required
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
              placeholder="(555) 123-4567"
            />
          </div>
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1"
              >Emergency Contact</label
            >
            <input
              v-model="membershipForm.emergencyContact"
              type="text"
              class="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none"
              placeholder="Name and phone number"
            />
          </div>
          <label class="flex items-start gap-2">
            <input
              v-model="membershipForm.agree"
              type="checkbox"
              required
              class="w-4 h-4 mt-1 text-fps-navy border-gray-300 rounded focus:ring-fps-navy"
            />
            <span class="text-sm text-gray-600"
              >I agree to the
              <NuxtLink to="/terms" class="text-fps-navy hover:underline"
                >Terms of Membership</NuxtLink
              ></span
            >
          </label>
          <button
            type="submit"
            :disabled="isSubmitting"
            class="w-full btn-primary py-3 disabled:opacity-50"
          >
            <Loader2 v-if="isSubmitting" class="w-5 h-5 animate-spin mr-2" />
            {{ isSubmitting ? "Processing..." : "Complete Membership" }}
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  UserCheck,
  Users,
  Heart,
  Check,
  X,
  User,
  Loader2,
} from "lucide-vue-next";

useHead({ title: "Membership" });

const user = useSupabaseUser();
const supabase = useSupabaseClient();

const showModal = ref(false);
const isSubmitting = ref(false);
const membershipForm = ref({
  type: "",
  phone: "",
  emergencyContact: "",
  agree: false,
});

const joinMembership = (type) => {
  membershipForm.value.type = type;
  showModal.value = true;
};

const submitMembership = async () => {
  isSubmitting.value = true;
  try {
    const { error } = await supabase.from("memberships").insert({
      user_id: user.value.sub,
      membership_type: membershipForm.value.type,
      phone: membershipForm.value.phone,
      emergency_contact: membershipForm.value.emergencyContact,
      status: "active",
      joined_at: new Date().toISOString(),
    });
    if (error) throw error;
    alert(
      "Welcome to Fraser Paramedic Society! Your membership has been activated.",
    );
    showModal.value = false;
    membershipForm.value = {
      type: "",
      phone: "",
      emergencyContact: "",
      agree: false,
    };
  } catch (error) {
    console.error("Membership error:", error);
    alert(
      "Failed to process membership. Please try again." + (error.message || ""),
    );
  } finally {
    isSubmitting.value = false;
  }
};
</script>
