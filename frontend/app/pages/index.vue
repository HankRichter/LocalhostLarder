<script setup lang="ts">
</script>

<template>
  <div class="home">
    <section class="container hero">
      <div class="hero__copy">
        <h1 class="hero__heading">Software projects & experiments</h1>
        <p class="hero__text">
          A selection of full-stack web applications and fun projects built with the things I have learned in my career in software.
        </p>
      </div>
    </section>

    <section class="container projects-grid">
      <ProjectCard
        category="Portfolio"
        status="MIT License"
        title="LocalhostLarder"
        description="A website to show off my software engineer skills, sausages making recipes, and a form to people to get in touch with me."
        :tags="['Nuxt', 'Vite', 'Laravel', 'SQL']"
        project-href="https://localhostlarder.com"
        repo-href="https://github.com/HankRichter/LocalhostLarder"
      >
      </ProjectCard>

      <ProjectCard
        category="Wedding Page"
        status="MIT License"
        title="Hank & Jaime's Wedding Page"
        description="A website for Hank and Jaime's wedding, featuring event details, RSVP forms, and photo galleries."
        :tags="['Next.js', 'Vite', 'TailwindCSS']"
        project-href="https://www.jaimeandhank2026.com"
        repo-href="https://github.com/HankRichter/RichterWedding"
      >
      </ProjectCard>

      <ProjectCard
        category="Business Website"
        status="MIT License"
        title="RichterLLC"
        description="A business and marketing website for RichterLLC to show off the transformative work they do in car restoration."
        :tags="['Next.js', 'Vite', 'TailwindCSS']"
        project-href="https://richter-llc.com"
        repo-href="https://github.com/HankRichter/RichterLLC"
      >
      </ProjectCard>
    </section>

    <section class="split">
      <div class="split__image" aria-hidden="true" />
      <div class="split__copy container">
        <span class="pill">&#9670; SIDE PROJECT</span>
        <h2 class="split__heading">Both are just excuses to try something new.</h2>
        <p class="split__text">
          Making sausage from scratch is one of my favorite hobbies because it's an
          excuse to experiment and learn — new spice blends, new ratios, new combinations, just
          to see what happens and figure out why. Side projects and sausages scratch the same itch:
          there's a baseline of technique you have to respect, but everything past
          that is an open question you learn by doing. Some experiments turn out great. Some don't. Either way I walk
          away knowing more than I did before.
        </p>
        <div class="split__stats">
          <div>
            <span>Hobby</span>
            <strong>Homemade Sausage</strong>
          </div>
          <div>
            <span>Approach</span>
            <strong>Try It & See</strong>
          </div>
          <div>
            <span>Mindset</span>
            <strong>Always Learning</strong>
          </div>
        </div>
      </div>
    </section>

    <section class="container cta">
      <div class="cta__box">
        <h2 class="cta__heading">Got a project idea or just want to talk shop?</h2>
        <p class="cta__text">
          I'm always up for chatting about web apps, side projects, or trading
          notes on whatever you're building or barbecuing.
        </p>
        <div class="cta__actions">
          <NuxtLink to="/contact" class="btn btn-primary"><Icon name="lucide:mail" /> Send an Email</NuxtLink>
          <a href="#" class="btn btn-secondary">View Resume</a>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.hero {
  display: grid;
  gap: var(--gutter-lg);
  padding-block: var(--space-xl);
}

.hero__heading {
  font-size: 2.25rem;
  font-weight: 500;
  margin-block: var(--space-md);
}

.hero__text {
  max-width: 40rem;
  opacity: 0.8;
}

.projects-grid {
  display: grid;
  gap: var(--gutter);
  padding-block: var(--space-xl);
  grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr));
}

.widget {
  font-family: var(--font-mono);
  font-size: 0.75rem;
  border-radius: var(--radius);
  padding: var(--space-sm);
  background: var(--color-surface-tint);
  margin: 0;
}

.widget__row {
  display: flex;
  justify-content: space-between;
  margin-bottom: var(--space-xs);
}

.widget--chart .widget__sparkline {
  width: 100%;
  height: 1.5rem;
}

.widget--chart .widget__sparkline polyline {
  stroke: var(--color-primary);
  stroke-width: 2;
}

.widget--progress .widget__bar {
  height: 0.5rem;
  border-radius: var(--radius-pill);
  background: var(--color-border);
  overflow: hidden;
}

.widget--progress .widget__bar span {
  display: block;
  height: 100%;
  background: var(--color-secondary);
}

.widget--code {
  color: var(--color-ink);
  white-space: pre-wrap;
}

.widget--code .widget__highlight {
  color: var(--color-primary);
}

.widget--terminal {
  background: var(--color-ink-deep);
  color: var(--color-bone);
  white-space: pre-wrap;
}

.widget--pickup {
  display: flex;
  flex-direction: column;
  gap: var(--space-xs);
}

.widget--thermal {
  display: flex;
  gap: var(--space-md);
}

.widget--thermal div {
  display: flex;
  flex-direction: column;
  gap: var(--space-xs);
}

.widget--thermal strong {
  color: var(--color-primary);
  font-size: 1rem;
}

.split {
  display: grid;
  background: var(--color-surface-tint);
  padding-block: var(--space-xl);
}

.split__image {
  display: none;
}

.split__heading {
  font-size: 1.75rem;
  font-weight: 500;
  margin-block: var(--space-md);
}

.split__text {
  opacity: 0.8;
  max-width: 40rem;
}

.split__stats {
  display: flex;
  flex-wrap: wrap;
  gap: var(--gutter);
  margin-top: var(--space-lg);
}

.split__stats > div {
  display: flex;
  flex-direction: column;
  gap: var(--space-xs);
  font-family: var(--font-mono);
  font-size: 0.75rem;
}

.split__stats strong {
  font-family: var(--font-body);
  font-size: 1rem;
}

.cta {
  padding-block: var(--space-xl);
}

.cta__box {
  background: var(--color-ink-deep);
  color: var(--color-bone);
  border-radius: var(--radius);
  padding: var(--space-xl);
  display: flex;
  flex-direction: column;
  gap: var(--space-md);
}

.cta__heading {
  font-size: 1.5rem;
  font-weight: 500;
  max-width: 30rem;
}

.cta__text {
  opacity: 0.7;
  max-width: 30rem;
}

.cta__actions {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-md);
}

@media (min-width: 768px) {
  .hero {
    grid-template-columns: 2fr 1fr;
    align-items: start;
  }
}

@media (min-width: 1024px) {
  .split {
    grid-template-columns: 1fr 1fr;
  }

  .split__image {
    display: block;
    background: var(--color-ink);
    min-height: 22rem;
  }

  .split__copy {
    padding-block: var(--space-xl);
  }
}
</style>
