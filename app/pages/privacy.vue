<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">Privacy Policy</h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">How we collect, use, and protect your information.</p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-4xl mx-auto container-padding">
        <div class="prose prose-lg max-w-none text-gray-600">
          <p class="text-sm text-gray-500 mb-8">Last updated: {{ new Date().toLocaleDateString() }}</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">1. Introduction</h2>
          <p>Fraser Paramedic Society ("we," "our," or "us") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you visit our website or use our services.</p>
          <p>By accessing or using our website, you agree to the terms of this Privacy Policy.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">2. Information We Collect</h2>
          <h3 class="text-lg font-semibold text-gray-900 mt-6 mb-2">Personal Information</h3>
          <p>We may collect personal information that you voluntarily provide to us, including:</p>
          <ul class="list-disc pl-6 space-y-2">
            <li>Name and contact information (email address, phone number)</li>
            <li>Demographic information</li>
            <li>Membership information</li>
            <li>Donation and payment information</li>
            <li>Event registration details</li>
            <li>Volunteer application information</li>
          </ul>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">3. How We Use Your Information</h2>
          <p>We use the information we collect to:</p>
          <ul class="list-disc pl-6 space-y-2">
            <li>Process membership applications and donations</li>
            <li>Communicate with you about events, programs, and updates</li>
            <li>Respond to your inquiries and requests</li>
            <li>Improve our website and services</li>
            <li>Comply with legal obligations</li>
          </ul>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">4. Information Sharing</h2>
          <p>We do not sell, trade, or rent your personal information to third parties. We may share your information with:</p>
          <ul class="list-disc pl-6 space-y-2">
            <li>Service providers who assist in our operations</li>
            <li>Legal authorities when required by law</li>
            <li>Partner organizations with your explicit consent</li>
          </ul>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">5. Data Security</h2>
          <p>We implement appropriate technical and organizational measures to protect your personal information against unauthorized access, alteration, disclosure, or destruction.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">6. Your Rights</h2>
          <p>You have the right to:</p>
          <ul class="list-disc pl-6 space-y-2">
            <li>Access your personal information</li>
            <li>Correct inaccurate information</li>
            <li>Request deletion of your information</li>
            <li>Opt-out of marketing communications</li>
          </ul>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">7. Contact Us</h2>
          <p>If you have any questions about this Privacy Policy, please contact us at:</p>
          <p class="mt-2"><strong>Email:</strong> info@fraserparamedicsociety.com<br><strong>Address:</strong> British Columbia, Canada</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
useHead({ title: 'Privacy Policy' })
</script>
