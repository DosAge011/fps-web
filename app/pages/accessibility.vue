<template>
  <div>
    <section class="bg-fps-navy py-16 lg:py-24">
      <div class="max-w-7xl mx-auto container-padding text-center">
        <h1 class="text-3xl sm:text-4xl lg:text-5xl font-bold text-white mb-4">Accessibility Statement</h1>
        <p class="text-lg text-blue-100 max-w-2xl mx-auto">Our commitment to making our website accessible to everyone.</p>
      </div>
    </section>

    <section class="section-padding bg-white">
      <div class="max-w-4xl mx-auto container-padding">
        <div class="prose prose-lg max-w-none text-gray-600">
          <p class="text-sm text-gray-500 mb-8">Last updated: {{ new Date().toLocaleDateString() }}</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">Our Commitment</h2>
          <p>Fraser Paramedic Society is committed to ensuring digital accessibility for people with disabilities. We are continually improving the user experience for everyone and applying the relevant accessibility standards.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">Accessibility Standards</h2>
          <p>We strive to conform to the Web Content Accessibility Guidelines (WCAG) 2.1 Level AA, which defines requirements for designers and developers to improve accessibility for people with disabilities.</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">Accessibility Features</h2>
          <p>Our website includes the following accessibility features:</p>
          <ul class="list-disc pl-6 space-y-2">
            <li><strong>Keyboard Navigation:</strong> All functionality is accessible using a keyboard</li>
            <li><strong>Screen Reader Compatibility:</strong> Content is structured for compatibility with screen readers</li>
            <li><strong>Text Alternatives:</strong> Images have descriptive alt text</li>
            <li><strong>Color Contrast:</strong> Text meets minimum contrast ratios for readability</li>
            <li><strong>Resizable Text:</strong> Text can be resized up to 200% without loss of functionality</li>
          </ul>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">Feedback and Assistance</h2>
          <p>We welcome your feedback on the accessibility of our website. If you encounter any accessibility barriers or need assistance, please contact us:</p>
          <p class="mt-2"><strong>Email:</strong> info@fraserparamedicsociety.com<br><strong>Response Time:</strong> We aim to respond within 48 hours</p>

          <h2 class="text-2xl font-bold text-fps-navy mt-8 mb-4">Continuous Improvement</h2>
          <p>We are committed to ongoing accessibility improvements. We regularly review our website and welcome suggestions from users on how we can enhance accessibility.</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
useHead({ title: 'Accessibility Statement' })
</script>
