---
layout: page
title: About
seo_title: "About Anne DeSpain | AI & Operations Consultant | Park City, Utah"
description: "Anne DeSpain brings 20+ years of retail operations experience from Amazon, J.Crew, and Sundance Catalog to AI consulting for small businesses and purpose-driven brands."
subtitle: Operations expertise meets AI capability
---

## The Founder

DeSpain Consulting was founded by Anne DeSpain, who spent 20+ years inside some of retail's most complex operations: **Amazon**, **Myer**, **Sundance Catalog**, **J Crew**, and **Limited Brands**. From department store buying in Australia to wholesale sales in the surf industry, that career spanned major corporations to boutique formats, building deep expertise in merchandising, planning, inventory, and the systems that make operations run.

That background isn't separate from the AI work. It's the foundation.

## Why It Matters

AI is powerful, but it's only as good as the operational understanding behind it. Most AI implementations fail not because the technology doesn't work, but because the people building them don't understand the business problems deeply enough.

When we build an automation, we're not just connecting tools. We're drawing on decades of experience with the messy reality of how businesses actually operate: the edge cases, the workarounds, the things that look simple on paper but break in practice.

The retail operations background means we know what questions to ask, where the real friction lives, and how to build solutions that survive contact with the real world.

---

## What We Do

We specialize in helping purpose-driven brands and organizations that prioritize meaningful missions. Our work blends classic retail operations disciplines with the AI systems that now do the heavy lifting:

- **AI opportunity audits** that map where automation will save the most time and margin in your specific operation
- **Workflow automation** for the work that eats your week: invoicing, reporting, data entry, follow-ups
- **Merchandising, assortment, and pricing strategy** backed by automated margin tracking and reporting that stays current, not quarterly
- **Market and competitive intelligence systems** that monitor your category, competitors, and cost pressures, then deliver the brief to your inbox
- **Customer acquisition systems**, from programmatic ad generation to performance dashboards that recommend the next move in plain language
- **Data and knowledge systems** that turn scattered operational knowledge into structured, searchable assets your team and your AI tools can both use
- **AI enablement and leadership guidance** for teams adopting these capabilities during critical growth phases

---

## Our Approach

**Start with the problem, not the technology.** AI is powerful, but it's a tool. The real work is understanding your business deeply enough to know where that tool will make the biggest difference.

**Build for how you actually work.** Generic solutions gather dust. We create systems that fit your existing workflows, not the other way around.

**Transfer knowledge, not dependency.** Our goal is to make your team more capable, not to create ongoing reliance on outside help.

---

## What Clients Say

<div class="testimonial">
  <blockquote>"You had a terrific knack of being able to take your large company experience and distill it down to actionable, value added initiatives for our smaller company."</blockquote>
</div>

<div class="testimonial">
  <blockquote>"You exposed so many blind spots within the company."</blockquote>
</div>

<div class="testimonial">
  <blockquote>"Gave me the ability to assess the company from more of a 30,000 feet viewpoint as opposed to always being in the weeds."</blockquote>
</div>

<div class="testimonial">
  <blockquote>"Prioritize the pain points, creating a roadmap of actionable items to tackle, and then dig in."</blockquote>
</div>

<div class="testimonial">
  <blockquote>"Anne presented the information in an approachable and actionable format. She is knowledgeable, while still curious and engaged in what is coming next. I'm looking forward to learning more from Anne."</blockquote>
  <cite>— Workshop Attendee, Summit County AI Literacy Series</cite>
</div>

---

## In the Community

AI adoption moves faster when people learn together. Outside client work, Anne invests in community AI education across Utah:

- **Co-organized the 2026 Women Build AI Retreat** in Salt Lake City, a capacity three-day gathering of more than 65 women working in AI, built around hands-on workshops, live tool demos, and peer learning
- **Teaches free AI literacy workshops** for Summit County residents, covering fundamentals and safe, practical everyday use
- **Speaks in the MIT-backed Women Build AI Academy series**, including live demos of the AI systems she builds and runs herself

---

## Certifications

**Anthropic**

<div class="cert-carousel">
  <button class="cert-nav cert-nav-prev" type="button" aria-label="Previous certificates">&#8249;</button>
  <div class="cert-images">
    <img src="/assets/images/cert-anthropic-claude-101.jpg" alt="Claude 101 — Anthropic">
    <img src="/assets/images/cert-anthropic-claude-platform-101.jpg" alt="Claude Platform 101 — Anthropic">
    <img src="/assets/images/cert-anthropic-claude-code-101.jpg" alt="Claude Code 101 — Anthropic">
    <img src="/assets/images/cert-anthropic-claude-code-in-action.jpg" alt="Claude Code in Action — Anthropic">
    <img src="/assets/images/cert-anthropic-ai-fluency.jpg" alt="AI Fluency: Framework & Foundations — Anthropic">
    <img src="/assets/images/cert-anthropic-intro-claude-cowork.jpg" alt="Introduction to Claude Cowork — Anthropic">
    <img src="/assets/images/cert-anthropic-intro-agent-skills.jpg" alt="Introduction to Agent Skills — Anthropic">
  </div>
  <button class="cert-nav cert-nav-next" type="button" aria-label="Next certificates">&#8250;</button>
</div>

**AI Exchange & AI Build Lab**

<div class="cert-carousel">
  <button class="cert-nav cert-nav-prev" type="button" aria-label="Previous certificates">&#8249;</button>
  <div class="cert-images">
    <img src="/assets/images/cert-ai-operator.jpg" alt="Certified AI Operator - The AI Exchange">
    <img src="/assets/images/cert-ai-foundations.jpg" alt="How To Scale A Business With AI & Agentic Workflows - Foundations Certificate">
    <img src="/assets/images/cert-agentic-workflows.jpg" alt="Master Market-Ready Agentic AI Workflows Certificate">
    <img src="/assets/images/cert-anthropic-agent-native-os.jpg" alt="Install an Agent Native OS in One Day with Claude Code — AI Build Lab">
  </div>
  <button class="cert-nav cert-nav-next" type="button" aria-label="Next certificates">&#8250;</button>
</div>

---

## Let's Connect

<a href="https://www.linkedin.com/in/annedespain/" class="btn btn-secondary" target="_blank" rel="noopener">Follow on LinkedIn</a>
<a href="/services" class="btn btn-primary" style="margin-left: 1rem;">Book an AI Opportunity Audit</a>

<script>
(function () {
  function setupCarousel(carousel) {
    var track = carousel.querySelector('.cert-images');
    var prev = carousel.querySelector('.cert-nav-prev');
    var next = carousel.querySelector('.cert-nav-next');
    if (!track || !prev || !next) return;

    function overflows() {
      return track.scrollWidth - track.clientWidth > 1;
    }

    function updateState() {
      if (!overflows()) {
        // Everything fits — no need for arrows on this row.
        carousel.classList.remove('is-enhanced');
        return;
      }
      carousel.classList.add('is-enhanced');
      prev.disabled = track.scrollLeft <= 1;
      next.disabled = track.scrollLeft + track.clientWidth >= track.scrollWidth - 1;
    }

    function step() {
      // Advance by ~90% of the visible width so a snap point lands cleanly.
      return Math.max(track.clientWidth * 0.9, 240);
    }

    prev.addEventListener('click', function () {
      track.scrollBy({ left: -step(), behavior: 'smooth' });
    });
    next.addEventListener('click', function () {
      track.scrollBy({ left: step(), behavior: 'smooth' });
    });

    track.addEventListener('scroll', updateState, { passive: true });
    window.addEventListener('resize', updateState);
    updateState();
  }

  function init() {
    document.querySelectorAll('.cert-carousel').forEach(setupCarousel);
  }

  if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', init);
  } else {
    init();
  }
})();
</script>
