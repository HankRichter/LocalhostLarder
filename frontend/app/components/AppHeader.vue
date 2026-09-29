<script setup lang="ts">
const route = useRoute();

const navLinks = [
  { label: 'About', to: '/about' },
  { label: 'Projects', to: '/projects' },
  { label: 'Sausages', to: '/sausages' },
  { label: 'Contact', to: '/contact' },
];
</script>

<template>
  <header class="app-header">
    <div class="app-header__inner">
      <NuxtLink to="/" class="app-header__brand">
        <span class="app-header__mark">H</span>
        <span class="app-header__brand-text">
          <span class="app-header__name">Hank Richter</span>
          <span class="app-header__tagline">Full-Stack Dev &amp; Sausage Maker</span>
        </span>
      </NuxtLink>

      <nav class="app-header__nav">
        <NuxtLink
          v-for="link in navLinks"
          :key="link.to"
          :to="link.to"
          :class="{ 'is-active': route.path.startsWith(link.to) }"
        >
          {{ link.label }}
        </NuxtLink>
      </nav>

      <div class="app-header__actions">
        <NuxtLink to="/contact" class="app-header__cta">Say Hello</NuxtLink>
      </div>
    </div>
  </header>
</template>

<style scoped>
.app-header {
  background: var(--color-bone);
  border-bottom: 1px solid var(--color-border);
}

.app-header__inner {
  max-width: 1280px;
  margin-inline: auto;
  display: flex;
  align-items: center;
  gap: var(--gutter);
  padding: var(--space-md) var(--margin-mobile);
}

.app-header__brand {
  display: flex;
  align-items: center;
  gap: var(--space-sm);
  text-decoration: none;
  color: var(--color-ink);
  margin-right: auto;
}

.app-header__mark {
  display: grid;
  place-items: center;
  width: 2rem;
  height: 2rem;
  border-radius: var(--radius);
  background: var(--color-primary);
  color: #fff;
  font-family: var(--font-display);
  font-weight: 500;
}

.app-header__brand-text {
  display: flex;
  flex-direction: column;
  line-height: 1.2;
}

.app-header__name {
  font-weight: 700;
}

.app-header__tagline {
  display: none;
  font-family: var(--font-mono);
  font-size: 0.6875rem;
  letter-spacing: 0.05em;
  color: var(--color-ink);
  opacity: 0.6;
  text-transform: uppercase;
}

.app-header__nav {
  display: none;
  gap: var(--gutter);
}

.app-header__nav a {
  text-decoration: none;
  color: var(--color-ink);
}

.app-header__nav a.is-active {
  color: var(--color-primary);
}

.app-header__actions {
  display: flex;
  align-items: center;
  gap: var(--space-md);
}

.app-header__cta {
  display: none;
  padding: 0 var(--space-lg);
  height: 2.25rem;
  align-items: center;
  border-radius: var(--radius);
  background: var(--color-primary);
  color: #fff;
  text-decoration: none;
  font-weight: 600;
}

@media (min-width: 768px) {
  .app-header__tagline {
    display: block;
  }
}

@media (min-width: 1024px) {
  .app-header__inner {
    padding-inline: var(--margin-desktop);
  }

  .app-header__nav {
    display: flex;
  }

  .app-header__cta {
    display: inline-flex;
  }
}
</style>
