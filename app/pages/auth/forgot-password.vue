<template>
  <div class="min-h-screen bg-gray-50 flex items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
    <div class="max-w-md w-full">
      <div class="bg-white rounded-2xl shadow-lg p-8">
        <div class="text-center mb-8">
          <div class="w-16 h-16 bg-fps-navy rounded-xl flex items-center justify-center mx-auto mb-4">
            <KeyRound class="w-8 h-8 text-white" />
          </div>
          <h1 class="text-2xl font-bold text-fps-navy">Reset Password</h1>
          <p class="text-gray-600 mt-2">Enter your email and we'll send you a reset link</p>
        </div>

        <div v-if="showSuccess" class="mb-6 p-4 bg-green-50 border border-green-200 rounded-lg flex items-start gap-3">
          <CheckCircle class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
          <div>
            <p class="font-medium text-green-800">Reset Link Sent!</p>
            <p class="text-sm text-green-700">Check your email for instructions to reset your password.</p>
          </div>
        </div>

        <div v-if="errorMessage" class="mb-6 p-4 bg-red-50 border border-red-200 rounded-lg flex items-start gap-3">
          <AlertCircle class="w-5 h-5 text-red-500 flex-shrink-0 mt-0.5" />
          <p class="text-sm text-red-700">{{ errorMessage }}</p>
        </div>

        <form v-if="!showSuccess" @submit.prevent="handleSubmit" class="space-y-6">
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">Email Address</label>
            <div class="relative">
              <Mail class="absolute left-3 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400" />
              <input v-model="email" type="email" required class="w-full pl-10 pr-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none" placeholder="you@example.com" />
            </div>
          </div>

          <button type="submit" :disabled="isLoading" class="w-full btn-primary py-3 disabled:opacity-50">
            <Loader2 v-if="isLoading" class="w-5 h-5 animate-spin mr-2" />
            {{ isLoading ? 'Sending...' : 'Send Reset Link' }}
          </button>
        </form>

        <p class="text-center mt-8 text-sm text-gray-600">
          Remember your password?
          <NuxtLink to="/auth/login" class="text-fps-navy font-medium hover:underline">Sign in</NuxtLink>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { KeyRound, Mail, Loader2, AlertCircle, CheckCircle } from 'lucide-vue-next'

definePageMeta({ layout: 'auth' })

const supabase = useSupabaseClient()

const email = ref('')
const isLoading = ref(false)
const showSuccess = ref(false)
const errorMessage = ref('')

const handleSubmit = async () => {
  isLoading.value = true
  errorMessage.value = ''
  try {
    const { error } = await supabase.auth.resetPasswordForEmail(email.value, {
      redirectTo: `${window.location.origin}/auth/reset-password`
    })
    if (error) throw error
    showSuccess.value = true
    email.value = ''
  } catch (error) {
    errorMessage.value = error.message || 'Failed to send reset link. Please try again.'
  } finally {
    isLoading.value = false
  }
}
</script>
