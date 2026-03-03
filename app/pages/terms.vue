<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">Terms of Use</h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">Terms and conditions for using our website and services.</p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-4xl mx-auto container-padding">
        <div class="prose prose-lg max-w-none text-gray-600">
          <p class="text-sm text-gray-500 mb-8">Last updated: {{ new Date().toLocaleDateString() }}</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">1. Acceptance of Terms</h2>
          <p>By accessing and using the Fraser Paramedic Society website ("the Site"), you accept and agree to be bound by these Terms of Use. If you do not agree to these terms, please do not use the Site.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">2. Use of the Site</h2>
          <p>You agree to use the Site only for lawful purposes and in a way that does not infringe the rights of others. Prohibited behavior includes:</p>
          <ul class="list-disc pl-6 space-y-2">
            <li>Harassing, abusing, or harming others</li>
            <li>Transmitting unlawful, defamatory, or obscene content</li>
            <li>Attempting to gain unauthorized access to the Site</li>
            <li>Interfering with the proper functioning of the Site</li>
          </ul>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">3. Intellectual Property</h2>
          <p>All content on the Site, including text, graphics, logos, images, and software, is the property of Fraser Paramedic Society and is protected by Canadian and international copyright laws.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">4. Membership</h2>
          <p>Membership in Fraser Paramedic Society is subject to the following conditions:</p>
          <ul class="list-disc pl-6 space-y-2">
            <li>Membership categories and eligibility are as defined on our Membership page</li>
            <li>Members must provide accurate and complete information</li>
            <li>Membership may be terminated for violation of these terms</li>
          </ul>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">5. Donations</h2>
          <p>All donations to Fraser Paramedic Society are voluntary and non-refundable. We are committed to using donations responsibly in accordance with our mission.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">6. Disclaimer of Warranties</h2>
          <p>The Site is provided "as is" without warranties of any kind, either express or implied.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">7. Governing Law</h2>
          <p>These Terms of Use shall be governed by and construed in accordance with the laws of the Province of British Columbia, Canada.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">8. Contact Information</h2>
          <p>If you have any questions about these Terms of Use, please contact us:</p>
          <p class="mt-2"><strong>Email:</strong> info@fraserparamedicsociety.com<br><strong>Address:</strong> British Columbia, Canada</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
useHead({ title: 'Terms of Use' })
</script>
