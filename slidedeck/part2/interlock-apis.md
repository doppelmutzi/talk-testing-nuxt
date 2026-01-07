## Interlocking of APIs

<div style="max-width: 100%; overflow: hidden">
<svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 926.9500122070312 421" width="100%" height="auto" preserveAspectRatio="xMidYMid meet" style="background-color: white;">
  <defs>
    <style>
      .fragment { opacity: 0.2 !important; transition: opacity .25s ease; }
      .fragment.visible { opacity: 1 !important; }
      text { font-family: sans-serif; }
    </style>
  </defs>

  <rect x="0" y="0" width="926.9500122070312" height="421" fill="#ffffff"></rect>

  <!-- Nuxt block (step 3) -->
  <g class="fragment" data-fragment-index="3" stroke-linecap="round" transform="translate(10 61) rotate(0 180 40)">
    <path d="M20 0 C93.19 0, 166.38 0, 340 0 C353.33 0, 360 6.67, 360 20 C360 30.96, 360 41.93, 360 60 C360 73.33, 353.33 80, 340 80 C257.99 80, 175.97 80, 20 80 C6.67 80, 0 73.33, 0 60 C0 47.54, 0 35.07, 0 20 C0 6.67, 6.67 0, 20 0" stroke="none" stroke-width="0" fill="#d4edda"></path>
    <path d="M20 0 C93.37 0, 166.74 0, 340 0 M20 0 C134.12 0, 248.23 0, 340 0 M340 0 C353.33 0, 360 6.67, 360 20 M340 0 C353.33 0, 360 6.67, 360 20 M360 20 C360 29.4, 360 38.81, 360 60 M360 20 C360 28.52, 360 37.05, 360 60 M360 60 C360 73.33, 353.33 80, 340 80 M360 60 C360 73.33, 353.33 80, 340 80 M340 80 C240.17 80, 140.34 80, 20 80 M340 80 C259.14 80, 178.29 80, 20 80 M20 80 C6.67 80, 0 73.33, 0 60 M20 80 C6.67 80, 0 73.33, 0 60 M0 60 C0 45.52, 0 31.04, 0 20 M0 60 C0 46.94, 0 33.88, 0 20 M0 20 C0 6.67, 6.67 0, 20 0 M0 20 C0 6.67, 6.67 0, 20 0" stroke="#1e1e1e" stroke-width="2" fill="none"></path>
  </g>
  <g class="fragment" data-fragment-index="3" transform="translate(30 89) rotate(0 150 20)">
    <text x="0" y="27.168" font-size="28px" fill="#1e1e1e">Nuxt Test Utils</text>
  </g>
  <g class="fragment" data-fragment-index="3" transform="translate(390 72) rotate(0 263.4750061035156 45)">
    <text x="0" y="19.608" font-size="18px" fill="#1e1e1e">• Handles Nuxt-specifics (e.g., auto-imports)</text>
    <text x="0" y="49.608000000000004" font-size="18px" fill="#1e1e1e">• Boots real Nuxt app (e.g., loads modules)</text>
    <text x="0" y="79.608" font-size="18px" fill="#1e1e1e">• Helpers to mount Vue components relying on Nuxt-specifics</text>
  </g>

  <!-- Vue Test Utils block (step 2) -->
  <g class="fragment" data-fragment-index="2" stroke-linecap="round" transform="translate(10 171) rotate(0 180 40)">
    <path d="M20 0 C142.3 0, 264.6 0, 340 0 C353.33 0, 360 6.67, 360 20 C360 33.67, 360 47.33, 360 60 C360 73.33, 353.33 80, 340 80 C236.89 80, 133.78 80, 20 80 C6.67 80, 0 73.33, 0 60 C0 50.67, 0 41.34, 0 20 C0 6.67, 6.67 0, 20 0" stroke="none" stroke-width="0" fill="#cfe8ff"></path>
    <path d="M20 0 C97.69 0, 175.37 0, 340 0 M20 0 C128.18 0, 236.36 0, 340 0 M340 0 C353.33 0, 360 6.67, 360 20 M340 0 C353.33 0, 360 6.67, 360 20 M360 20 C360 33.68, 360 47.36, 360 60 M360 20 C360 35.17, 360 50.34, 360 60 M360 60 C360 73.33, 353.33 80, 340 80 M360 60 C360 73.33, 353.33 80, 340 80 M340 80 C234.59 80, 129.18 80, 20 80 M340 80 C239.63 80, 139.25 80, 20 80 M20 80 C6.67 80, 0 73.33, 0 60 M20 80 C6.67 80, 0 73.33, 0 60 M0 60 C0 44.4, 0 28.8, 0 20 M0 60 C0 44.94, 0 29.88, 0 20 M0 20 C0 6.67, 6.67 0, 20 0 M0 20 C0 6.67, 6.67 0, 20 0" stroke="#1e1e1e" stroke-width="2" fill="none"></path>
  </g>
  <g class="fragment" data-fragment-index="2" transform="translate(30 199) rotate(0 150 20)">
    <text x="0" y="27.168" font-size="28px" fill="#1e1e1e">Vue Test Utils</text>
  </g>
  <g class="fragment" data-fragment-index="2" transform="translate(389 181) rotate(0 244.39166259765625 45)">
    <text x="0" y="19.608" font-size="18px" fill="#1e1e1e">• Mount + interact with Vue components</text>
    <text x="0" y="49.608000000000004" font-size="18px" fill="#1e1e1e">• Stub child components with global.stubs, shallowMount</text>
    <text x="0" y="79.608" font-size="18px" fill="#1e1e1e">• Interactions (e.g., click button, trigger event, etc.)</text>
  </g>

  <!-- Vitest block (visible by default) -->
  <g stroke-linecap="round" transform="translate(10 281) rotate(0 180 40)">
    <path d="M20 0 C127.4 0, 234.81 0, 340 0 C353.33 0, 360 6.67, 360 20 C360 28.37, 360 36.74, 360 60 C360 73.33, 353.33 80, 340 80 C215.79 80, 91.58 80, 20 80 C6.67 80, 0 73.33, 0 60 C0 45.8, 0 31.6, 0 20 C0 6.67, 6.67 0, 20 0" stroke="none" stroke-width="0" fill="#ffe4c4"></path>
    <path d="M20 0 C102 0, 184 0, 340 0 M20 0 C122.24 0, 224.48 0, 340 0 M340 0 C353.33 0, 360 6.67, 360 20 M340 0 C353.33 0, 360 6.67, 360 20 M360 20 C360 29.96, 360 39.92, 360 60 M360 20 C360 33.81, 360 47.62, 360 60 M360 60 C360 73.33, 353.33 80, 340 80 M360 60 C360 73.33, 353.33 80, 340 80 M340 80 C229.01 80, 118.03 80, 20 80 M340 80 C220.11 80, 100.22 80, 20 80 M20 80 C6.67 80, 0 73.33, 0 60 M20 80 C6.67 80, 0 73.33, 0 60 M0 60 C0 51.28, 0 42.57, 0 20 M0 60 C0 50.94, 0 41.88, 0 20 M0 20 C0 6.67, 6.67 0, 20 0 M0 20 C0 6.67, 6.67 0, 20 0" stroke="#1e1e1e" stroke-width="2" fill="none"></path>
  </g>
  <g transform="translate(30 309) rotate(0 150 20)">
    <text x="0" y="27.168" font-size="28px" fill="#1e1e1e">Vitest (Runner)</text>
  </g>
  <g transform="translate(385 291) rotate(0 211.4166717529297 60)">
    <text x="0" y="19.608" font-size="18px" fill="#1e1e1e">• Test runner, base testing APIs (e.g., mocking)</text>
    <text x="0" y="49.608000000000004" font-size="18px" fill="#1e1e1e">• snapshot, timers, test coverage, etc.</text>
    <text x="0" y="79.608" font-size="18px" fill="#1e1e1e">• Test environments (node, happy-dom, etc.)</text>
  </g>

</svg>
</div>