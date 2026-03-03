<template>
  <div class="min-h-screen flex flex-col">
    <!-- Navigation -->
    <header
      class="sticky top-0 z-50 bg-white/95 backdrop-blur-sm border-b border-gray-100"
    >
      <nav class="max-w-7xl mx-auto container-padding">
        <div class="flex items-center justify-between h-16 lg:h-20">
          <!-- Logo -->
          <NuxtLink to="/" class="flex items-center gap-2">
            <div class="w-14 h-14 flex items-center justify-center">
              <img src="/img/fps-logo.png" alt="Discover FPS" />
            </div>
            <span class="font-bold hidden sm:block text-fps-navy"
              >Fraser Paramedic Society</span
            >
          </NuxtLink>

          <!-- Desktop Navigation -->
          <div class="hidden lg:flex items-center gap-1">
            <NuxtLink
              v-for="item in navItems"
              :key="item.path"
              :to="item.path"
              class="px-4 py-2 text-sm font-medium text-gray-700 hover:text-fps-navy rounded-lg hover:bg-gray-300 transition-colors"
              :class="{
                'text-fps-navy bg-gray-300': $route.path === item.path,
              }"
            >
              {{ item.label }}
            </NuxtLink>
          </div>

          <!-- CTA Buttons -->
          <div class="hidden lg:flex items-center gap-3">
            <NuxtLink to="/donate" class="btn-primary text-sm">
              Donate
            </NuxtLink>
            <template v-if="!user">
              <NuxtLink
                to="/auth/login"
                class="text-sm font-medium text-gray-700 hover:text-fps-navy"
              >
                Sign In
              </NuxtLink>
            </template>
            <template v-else>
              <div class="relative">
                <button
                  @click="showUserMenu = !showUserMenu"
                  class="flex items-center gap-2 px-3 py-2 text-sm font-medium text-gray-700 hover:text-fps-navy rounded-lg hover:bg-gray-50"
                >
                  <div
                    class="w-8 h-8 bg-fps-navy rounded-full flex items-center justify-center"
                  >
                    <User class="w-4 h-4 text-white" />
                  </div>
                  <span class="max-w-[100px] truncate">{{ user.email }}</span>
                  <ChevronDown class="w-4 h-4" />
                </button>
                <div
                  v-if="showUserMenu"
                  class="absolute right-0 mt-2 w-48 bg-white rounded-lg shadow-lg border border-gray-100 py-1"
                >
                  <NuxtLink
                    to="/profile"
                    class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-50"
                    @click="showUserMenu = false"
                  >
                    Profile
                  </NuxtLink>
                  <button
                    @click="handleSignOut"
                    class="block w-full text-left px-4 py-2 text-sm text-red-600 hover:bg-red-50"
                  >
                    Sign Out
                  </button>
                </div>
              </div>
            </template>
          </div>

          <!-- Mobile Menu Button -->
          <button
            @click="mobileMenuOpen = !mobileMenuOpen"
            class="lg:hidden p-2 text-gray-700 hover:text-fps-navy"
          >
            <Menu v-if="!mobileMenuOpen" class="w-6 h-6" />
            <X v-else class="w-6 h-6" />
          </button>
        </div>

        <!-- Mobile Menu -->
        <div
          v-if="mobileMenuOpen"
          class="lg:hidden py-4 border-t border-gray-100"
        >
          <div class="flex flex-col gap-1">
            <NuxtLink
              v-for="item in navItems"
              :key="item.path"
              :to="item.path"
              class="px-4 py-3 text-sm font-medium text-gray-700 hover:text-fps-navy hover:bg-gray-300 rounded-lg"
              :class="{
                'text-fps-navy bg-gray-300': $route.path === item.path,
              }"
              @click="mobileMenuOpen = false"
            >
              {{ item.label }}
            </NuxtLink>
          </div>
          <div class="mt-4 pt-4 border-t border-gray-100 flex flex-col gap-2">
            <NuxtLink
              to="/donate"
              class="btn-primary text-center"
              @click="mobileMenuOpen = false"
            >
              Donate
            </NuxtLink>
            <template v-if="!user">
              <NuxtLink
                to="/auth/login"
                class="btn-secondary text-center"
                @click="mobileMenuOpen = false"
              >
                Sign In
              </NuxtLink>
            </template>
            <template v-else>
              <div class="px-4 py-3 bg-gray-50 rounded-lg">
                <p class="text-sm font-medium text-gray-900">
                  {{ user.email }}
                </p>
              </div>
              <button
                @click="handleSignOut"
                class="text-center px-4 py-3 text-sm font-medium text-red-600 hover:bg-red-50 rounded-lg"
              >
                Sign Out
              </button>
            </template>
          </div>
        </div>
      </nav>
    </header>

    <!-- Main Content -->
    <main class="flex-1">
      <slot />
    </main>

    <!-- Footer -->
    <footer class="bg-fps-dark text-white">
      <div class="max-w-7xl mx-auto container-padding py-12 lg:py-16">
        <div
          class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 lg:gap-12"
        >
          <!-- Brand -->
          <div class="lg:col-span-1">
            <div class="flex items-center gap-2 mb-4">
              <div
                class="w-10 h-10 bg-white rounded-lg flex items-center justify-center"
              >
                <span class="text-fps-navy font-bold text-lg">FPS</span>
              </div>
              <span class="font-semibold">Fraser Paramedic Society</span>
            </div>
            <p class="text-gray-400 text-sm mb-6">
              Supporting paramedics and first responders across British
              Columbia.
            </p>
            <div class="flex gap-4">
              <a
                v-for="social in socialLinks"
                :key="social.label"
                :href="social.href"
                target="_blank"
                rel="noopener"
                class="w-10 h-10 bg-white/10 rounded-lg flex items-center justify-center hover:bg-white/20 transition-colors"
                :aria-label="social.label"
              >
                <component :is="social.icon" class="w-5 h-5" />
              </a>
            </div>
          </div>

          <!-- Quick Links -->
          <div>
            <h3 class="font-semibold mb-4">About FPS</h3>
            <ul class="space-y-3">
              <li v-for="link in aboutLinks" :key="link.path">
                <NuxtLink
                  :to="link.path"
                  class="text-gray-400 hover:text-white text-sm transition-colors"
                >
                  {{ link.label }}
                </NuxtLink>
              </li>
            </ul>
          </div>

          <!-- Get Involved -->
          <div>
            <h3 class="font-semibold mb-4">Get Involved</h3>
            <ul class="space-y-3">
              <li v-for="link in involvedLinks" :key="link.path">
                <NuxtLink
                  :to="link.path"
                  class="text-gray-400 hover:text-white text-sm transition-colors"
                >
                  {{ link.label }}
                </NuxtLink>
              </li>
            </ul>
          </div>

          <!-- Contact -->
          <div>
            <h3 class="font-semibold mb-4">Contact</h3>
            <ul class="space-y-3 text-gray-400 text-sm">
              <li class="flex items-start gap-3">
                <Mail class="w-5 h-5 mt-0.5 flex-shrink-0" />
                <a
                  href="mailto:info@fraserparamedicsociety.com"
                  class="hover:text-white transition-colors"
                >
                  info@fraserparamedicsociety.com
                </a>
              </li>
              <li class="flex items-start gap-3">
                <MapPin class="w-5 h-5 mt-0.5 flex-shrink-0" />
                <span>British Columbia, Canada</span>
              </li>
            </ul>
          </div>
        </div>

        <!-- Bottom Bar -->
        <div
          class="mt-12 pt-8 border-t border-white/10 flex flex-col md:flex-row justify-between items-center gap-4"
        >
          <p class="text-gray-400 text-sm">
            © {{ new Date().getFullYear() }} Fraser Paramedic Society. All
            rights reserved.
          </p>
          <div class="flex gap-6">
            <NuxtLink
              v-for="link in legalLinks"
              :key="link.path"
              :to="link.path"
              class="text-gray-400 hover:text-white text-sm transition-colors"
            >
              {{ link.label }}
            </NuxtLink>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import {
  Menu,
  X,
  User,
  ChevronDown,
  Facebook,
  Instagram,
  Linkedin,
  Mail,
  MapPin,
} from "lucide-vue-next";

const user = useSupabaseUser();
const supabase = useSupabaseClient();
const router = useRouter();

const mobileMenuOpen = ref(false);
const showUserMenu = ref(false);

const navItems = [
  { label: "Home", path: "/" },
  { label: "About", path: "/about" },
  { label: "Programs", path: "/programs" },
  { label: "Events", path: "/events" },
  { label: "Get Involved", path: "/get-involved" },
  { label: "Sponsors", path: "/sponsors" },
  { label: "Contact", path: "/contact" },
];

const socialLinks = [
  { label: "Facebook", href: "https://facebook.com", icon: Facebook },
  { label: "Instagram", href: "https://instagram.com", icon: Instagram },
  { label: "LinkedIn", href: "https://linkedin.com", icon: Linkedin },
];

const aboutLinks = [
  { label: "Our Story", path: "/about" },
  { label: "Mission & Vision", path: "/about#mission" },
  { label: "Leadership", path: "/about#leadership" },
  { label: "Financial Transparency", path: "/about#transparency" },
];

const involvedLinks = [
  { label: "Volunteer", path: "/get-involved" },
  { label: "Become a Member", path: "/membership" },
  { label: "Corporate Partners", path: "/sponsors" },
  { label: "Donate", path: "/donate" },
];

const legalLinks = [
  { label: "Privacy Policy", path: "/privacy" },
  { label: "Terms of Use", path: "/terms" },
  { label: "Accessibility", path: "/accessibility" },
];

const handleSignOut = async () => {
  await supabase.auth.signOut();
  showUserMenu.value = false;
  mobileMenuOpen.value = false;
  router.push("/");
};
</script>
