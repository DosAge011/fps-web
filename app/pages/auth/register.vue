<template>
  <div class="min-h-screen bg-gray-50 flex items-center justify-center py-12 px-4 sm:px-6 lg:px-8">
    <div class="max-w-md w-full">
      <div class="bg-white rounded-2xl shadow-lg p-8">
        <div class="text-center mb-8">
          <div class="w-16 h-16 bg-fps-navy rounded-xl flex items-center justify-center mx-auto mb-4">
            <UserPlus class="w-8 h-8 text-white" />
          </div>
          <h1 class="text-2xl font-bold text-fps-navy">Create Account</h1>
          <p class="text-gray-600 mt-2">Join the Fraser Paramedic Society</p>
        </div>

        <div v-if="errorMessage" class="mb-6 p-4 bg-red-50 border border-red-200 rounded-lg flex items-start gap-3">
          <AlertCircle class="w-5 h-5 text-red-500 flex-shrink-0 mt-0.5" />
          <p class="text-sm text-red-700">{{ errorMessage }}</p>
        </div>

        <div v-if="successMessage" class="mb-6 p-4 bg-green-50 border border-green-200 rounded-lg flex items-start gap-3">
          <CheckCircle class="w-5 h-5 text-green-500 flex-shrink-0 mt-0.5" />
          <p class="text-sm text-green-700">{{ successMessage }}</p>
        </div>

        <form v-if="!successMessage" @submit.prevent="handleRegister" class="space-y-5">
          <div class="grid grid-cols-2 gap-4">
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-2">First Name</label>
              <input v-model="firstName" type="text" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none" placeholder="John" />
            </div>
            <div>
              <label class="block text-sm font-medium text-gray-700 mb-2">Last Name</label>
              <input v-model="lastName" type="text" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none" placeholder="Doe" />
            </div>
          </div>

          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">Email Address</label>
            <div class="relative">
              <Mail class="absolute left-3 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400" />
              <input v-model="email" type="email" required class="w-full pl-10 pr-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none" placeholder="you@example.com" />
            </div>
          </div>

          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">Password</label>
            <div class="relative">
              <Lock class="absolute left-3 top-1/2 -translate-y-1/2 w-5 h-5 text-gray-400" />
              <input v-model="password" :type="showPassword ? 'text' : 'password'" required minlength="8" class="w-full pl-10 pr-12 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none" placeholder="••••••••" />
              <button type="button" @click="showPassword = !showPassword" class="absolute right-3 top-1/2 -translate-y-1/2 text-gray-400 hover:text-gray-600">
                <Eye v-if="!showPassword" class="w-5 h-5" />
                <EyeOff v-else class="w-5 h-5" />
              </button>
            </div>
            <p class="text-xs text-gray-500 mt-1">Must be at least 8 characters</p>
          </div>

          <div>
            <label class="block text-sm font-medium text-gray-700 mb-2">Membership Type</label>
            <select v-model="membershipType" required class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-fps-navy outline-none">
              <option value="">Select membership type</option>
              <option value="regular">Regular Member (Paramedic)</option>
              <option value="allied">Allied Member (Family/First Responder)</option>
              <option value="community">Community Supporter</option>
            </select>
          </div>

          <label class="flex items-start gap-3">
            <input v-model="agreeTerms" type="checkbox" required class="w-4 h-4 mt-1 text-fps-navy border-gray-300 rounded focus:ring-fps-navy" />
            <span class="text-sm text-gray-600">
              I agree to the <NuxtLink to="/terms" class="text-fps-navy hover:underline">Terms of Use</NuxtLink> and <NuxtLink to="/privacy" class="text-fps-navy hover:underline">Privacy Policy</NuxtLink>
            </span>
          </label>

          <button type="submit" :disabled="isLoading" class="w-full btn-primary py-3 disabled:opacity-50">
            <Loader2 v-if="isLoading" class="w-5 h-5 animate-spin mr-2" />
            {{ isLoading ? 'Creating Account...' : 'Create Account' }}
          </button>
        </form>

        <div v-if="!successMessage" class="relative my-8">
          <div class="absolute inset-0 flex items-center">
            <div class="w-full border-t border-gray-200"></div>
          </div>
          <div class="relative flex justify-center text-sm">
            <span class="px-4 bg-white text-gray-500">Or continue with</span>
          </div>
        </div>

        <button v-if="!successMessage" @click="handleGoogleRegister" :disabled="isGoogleLoading" class="w-full flex items-center justify-center gap-3 px-4 py-3 border border-gray-300 rounded-lg hover:bg-gray-50 transition-colors disabled:opacity-50">
          <svg class="w-5 h-5" viewBox="0 0 24 24">
            <path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/>
            <path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/>
            <path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z"/>
            <path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"/>
          </svg>
          <span class="font-medium text-gray-700">{{ isGoogleLoading ? 'Connecting...' : 'Continue with Google' }}</span>
        </button>

        <p v-if="!successMessage" class="text-center mt-8 text-sm text-gray-600">
          Already have an account?
          <NuxtLink to="/auth/login" class="text-fps-navy font-medium hover:underline">Sign in</NuxtLink>
        </p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { UserPlus, Mail, Lock, Eye, EyeOff, AlertCircle, CheckCircle, Loader2 } from 'lucide-vue-next'

definePageMeta({ layout: 'auth' })

const supabase = useSupabaseClient()

const firstName = ref('')
const lastName = ref('')
const email = ref('')
const password = ref('')
const membershipType = ref('')
const agreeTerms = ref(false)
const showPassword = ref(false)
const isLoading = ref(false)
const isGoogleLoading = ref(false)
const errorMessage = ref('')
const successMessage = ref('')

const handleRegister = async () => {
  isLoading.value = true
  errorMessage.value = ''

  if (password.value.length < 8) {
    errorMessage.value = 'Password must be at least 8 characters long.'
    isLoading.value = false
    return
  }

  try {
    const { error } = await supabase.auth.signUp({
      email: email.value,
      password: password.value,
      options: {
        data: { first_name: firstName.value, last_name: lastName.value, membership_type: membershipType.value },
        emailRedirectTo: `${window.location.origin}/auth/callback`
      }
    })
    if (error) throw error
    successMessage.value = 'Account created successfully! Please check your email to verify your account.'
  } catch (error) {
    errorMessage.value = error.message || 'Failed to create account. Please try again.'
  } finally {
    isLoading.value = false
  }
}

const handleGoogleRegister = async () => {
  isGoogleLoading.value = true
  errorMessage.value = ''
  try {
    const { error } = await supabase.auth.signInWithOAuth({
      provider: 'google',
      options: { redirectTo: `${window.location.origin}/auth/callback` }
    })
    if (error) throw error
  } catch (error) {
    errorMessage.value = error.message || 'Failed to connect with Google.'
    isGoogleLoading.value = false
  }
}
</script>
