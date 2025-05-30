<template>
  <section
    class="relative isolate flex items-center justify-center overflow-hidden bg-gradient-to-br from-indigo-600 via-purple-600 to-fuchsia-600 py-24 text-white"
  >
    <!-- Decorative blurred blob -->
    <div
      class="pointer-events-none absolute -z-10 h-[500px] w-[500px] -translate-x-1/2 rounded-full bg-pink-400 opacity-30 blur-3xl"
      style="top: 60%; left: 50%"
    />

    <!-- Centered container, 60% width max -->
    <div class="container mx-auto flex flex-col-reverse items-center justify-between gap-12 px-4 md:flex-row md:max-w-4xl">
      <!-- Text column -->
      <div class="w-full md:w-1/2 text-center md:text-left">
        <h1 class="text-4xl font-extrabold leading-tight tracking-tight md:text-5xl lg:text-6xl">
          Hi, I’m Jake — a&nbsp;
          <span class="underline decoration-4 decoration-white/60">
            Vue&nbsp;developer
          </span>
          who designs with code.
        </h1>
        <p class="mt-4 text-lg md:text-xl">
          Cooking up performant front-ends, from pub kitchens to production servers.
        </p>
        <div class="mt-8 flex flex-col items-center gap-4 md:flex-row md:items-start">
          <RouterLink
            to="/projects"
            class="rounded-xl bg-white/90 px-6 py-3 text-indigo-700 font-semibold shadow hover:bg-white transition"
          >
            See my work →
          </RouterLink>
          <a
            href="mailto:Jake.mellenchip60@gmail.com"
            class="rounded-xl border border-white/70 px-6 py-3 font-semibold hover:bg-white/10 transition"
          >
            Hire me
          </a>
        </div>
      </div>

      <!-- Image column -->
      <div class="w-full md:w-1/2 flex justify-center">
        <img
          src="@/assets/jake.jpg"
          alt="Photo of Jake Mellenchip"
          class="h-64 w-64 rounded-full object-cover shadow-lg md:h-80 md:w-80 lg:h-96 lg:w-96"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
defineProps()
</script>

<script>
export default {
  name: 'HeroSection',
}
</script>