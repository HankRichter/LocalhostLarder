<script setup lang="ts">
const route = useRoute();
const currentYear = new Date().getFullYear();

const footerLinks = [
  { label: 'About', to: '/about' },
  { label: 'Projects', to: '/projects' },
  { label: 'Sausages', to: '/sausages' },
  { label: 'Contact', to: '/contact' },
];

const tabLinks = [
  { label: 'About', to: '/about', icon: 'lucide:user' },
  { label: 'Projects', to: '/projects', icon: 'lucide:layout-grid' },
  { label: 'Sausages', to: '/sausages', icon: 'lucide:chef-hat' },
  { label: 'Contact', to: '/contact', icon: 'lucide:send' },
];
</script>

<template>
  <footer class="app-footer">
    <nav class="app-footer__nav">
      <NuxtLink v-for="link in footerLinks" :key="link.to" :to="link.to">
        {{ link.label }}
      </NuxtLink>
    </nav>
    <div class="app-footer__social">
      <a href="https://github.com/HankRichter" target="_blank" rel="noopener">GitHub</a>
      <span>/</span>
      <a href="hhttps://www.linkedin.com/in/edward-richter-291785152/" target="_blank" rel="noopener">LinkedIn</a>
    </div>
    <small>&copy; {{ currentYear }} LocalHostLarder</small>
  </footer>

  <nav class="app-tabbar" aria-label="Primary">
    <NuxtLink
      v-for="link in tabLinks"
      :key="link.to"
      :to="link.to"
      class="app-tabbar__item"
      :class="{ 'is-active': route.path.startsWith(link.to) }"
    >
      <Icon :name="link.icon" />
      <span>{{ link.label }}</span>
    </NuxtLink>
  </nav>
</template>

<style scoped>
.app-footer {
  display: none;
  flex-direction: column;
  align-items: center;
  gap: var(--space-md);
  padding: var(--space-xl) var(--margin-mobile);
  border-top: 1px solid var(--color-border);
  font-family: var(--font-mono);
  font-size: 0.8125rem;
}

.app-footer__nav {
  display: flex;
  gap: var(--gutter);
}

.app-footer__nav a,
.app-footer__social a {
  text-decoration: none;
  color: var(--color-ink);
}

.app-footer__social {
  display: flex;
  gap: var(--space-sm);
  opacity: 0.7;
}

.app-tabbar {
  position: fixed;
  inset-inline: 0;
  bottom: 0;
  display: flex;
  justify-content: space-around;
  background: var(--color-surface);
  border-top: 1px solid var(--color-border);
  padding: var(--space-sm) 0;
  z-index: 10;
}

.app-tabbar__item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--space-xs);
  text-decoration: none;
  color: var(--color-ink);
  font-family: var(--font-mono);
  font-size: 0.625rem;
  letter-spacing: 0.05em;
  text-transform: uppercase;
  opacity: 0.6;
}

.app-tabbar__item.is-active {
  color: var(--color-primary);
  opacity: 1;
}

@media (min-width: 768px) {
  .app-footer {
    flex-direction: row;
    justify-content: space-between;
  }

  .app-footer__nav {
    order: 2;
  }

  .app-footer__social {
    order: 3;
  }
}

@media (min-width: 1024px) {
  .app-footer {
    display: flex;
    padding-inline: var(--margin-desktop);
  }

  .app-tabbar {
    display: none;
  }
}
</style>
