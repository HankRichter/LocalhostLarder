<script setup lang="ts">
withDefaults(
  defineProps<{
    category: string;
    status: string;
    statusDot?: boolean;
    title: string;
    description: string;
    tags: string[];
    projectHref: string;
    projectLabel?: string;
    repoHref: string;
  }>(),
  {
    statusDot: false,
    projectLabel: 'View Project',
  },
);
</script>

<template>
  <article class="project-card">
    <header class="project-card__header">
      <span class="project-card__category">{{ category }}</span>
      <span class="project-card__status">
        <span v-if="statusDot" class="project-card__dot" />
        {{ status }}
      </span>
    </header>

    <h3 class="project-card__title">{{ title }}</h3>
    <p class="project-card__description">{{ description }}</p>

    <div v-if="$slots.default" class="project-card__widget">
      <slot />
    </div>

    <ul class="project-card__tags">
      <li v-for="tag in tags" :key="tag">{{ tag }}</li>
    </ul>

    <footer class="project-card__footer">
      <a :href="projectHref" class="project-card__link">{{ projectLabel }} <Icon name="lucide:arrow-up-right" /></a>
      <a :href="repoHref" class="project-card__link project-card__link--muted">
        <Icon name="lucide:code" /> GitHub
      </a>
    </footer>
  </article>
</template>

<style scoped>
.project-card {
  display: flex;
  flex-direction: column;
  gap: var(--space-sm);
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  padding: var(--space-lg);
}

.project-card__header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: var(--font-mono);
  font-size: 0.6875rem;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}

.project-card__category {
  color: var(--color-primary);
}

.project-card__status {
  display: inline-flex;
  align-items: center;
  gap: var(--space-xs);
  opacity: 0.7;
}

.project-card__dot {
  width: 0.4rem;
  height: 0.4rem;
  border-radius: var(--radius-pill);
  background: var(--color-tertiary);
}

.project-card__title {
  font-size: 1.25rem;
  font-weight: 500;
}

.project-card__description {
  font-size: 0.9375rem;
  opacity: 0.8;
}

.project-card__widget {
  margin-block: var(--space-xs);
}

.project-card__tags {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-xs);
  list-style: none;
  margin: 0;
  padding: 0;
  font-family: var(--font-mono);
  font-size: 0.75rem;
}

.project-card__tags li {
  padding: var(--space-xs) var(--space-sm);
  background: var(--color-surface-tint);
  border-radius: var(--radius);
}

.project-card__footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: var(--space-sm);
  font-size: 0.875rem;
}

.project-card__link {
  display: inline-flex;
  align-items: center;
  gap: var(--space-xs);
  text-decoration: none;
  color: var(--color-primary);
  font-weight: 600;
}

.project-card__link--muted {
  color: var(--color-ink);
  opacity: 0.7;
  font-weight: 400;
}
</style>
