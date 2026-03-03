<template>
  <div class="min-h-screen bg-gray-50 flex items-center justify-center">
    <div class="text-center">
      <Loader2 class="w-12 h-12 text-fps-navy animate-spin mx-auto mb-4" />
      <h1 class="text-xl font-semibold text-fps-navy">Completing sign in...</h1>
      <p class="text-gray-600 mt-2">Please wait while we verify your account.</p>
    </div>
  </div>
</template>

<script setup>
import { Loader2 } from 'lucide-vue-next'

const supabase = useSupabaseClient()
const router = useRouter()

onMounted(async () => {
  try {
    const { data, error } = await supabase.auth.getSession()
    if (error) throw error
    if (data.session) {
      router.push('/')
    } else {
      router.push('/auth/login')
    }
  } catch (error) {
    console.error('Auth callback error:', error)
    router.push('/auth/login?error=callback_failed')
  }
})
</script>
