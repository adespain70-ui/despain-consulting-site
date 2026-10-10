---
layout: default
title: Test Jev on Your Own Evals with Claude Code
seo_title: "Test Jev on Your Own Evals with Claude Code: Step-by-Step | DeSpain Consulting"
description: A step-by-step how-to for testing Jev, TypeSafe's judging model, against your own eval scores, with the exact Claude Code prompts to use, from setup to a Sonnet head-to-head.
permalink: /jev-guide
---

<section class="advance-hero">
  <div class="container">
    <span class="advance-label">DeSpain Consulting</span>
    <h1>Test Jev on your own evals with <span class="advance-accent">Claude Code</span></h1>
    <p class="advance-hero-sub">The step-by-step setup and the exact prompts I used to test Jev against my own scores, put Sonnet 5.5 head to head, and find out where to trust it.</p>
  </div>
</section>

<section class="advance-intro">
  <div class="container">
    <p class="advance-quote">"Jev, Jev, Jev. But what is it, and can it grade my evals?"</p>
    <p><strong>Jev</strong> is TypeSafe's new model, and its whole job is judging. You give it text and a question, and it gives back a <strong>score plus how confident it is</strong>. It does not write anything, which makes it fast and cheap. In my test, 60 grading calls ran in about a second for under a penny.</p>
    <p>The setup that worked: <strong>Claude Code drives</strong> (it builds and runs the test), <strong>Jev grades</strong>, and <strong>your own scores are the answer key</strong>. You do not need to write code. You do need to be comfortable typing into Claude Code.</p>
  </div>
</section>

<section class="advance-intro">
  <div class="container">
    <h2>What you need</h2>
    <p><strong>Claude Code</strong> installed and working.</p>
    <p><strong>A TypeSafe account and API key.</strong> Create the key at <a href="https://console.typesafe.ai/">console.typesafe.ai</a>.</p>
    <p><strong>15 to 20 AI outputs you have already graded by hand</strong> on your rubric, in a spreadsheet, Notion, or a doc. Mine were customer emails scored 1 to 5 on clarity, tone, relevance, correctness, conciseness, and brand voice.</p>
    <p><strong>Optional, for the head-to-head:</strong> an Anthropic API key from <a href="https://console.anthropic.com/">console.anthropic.com</a>.</p>
  </div>
</section>

<section class="advance-framework">
  <div class="container">

    <div class="advance-step">
      <div class="advance-letter">1</div>
      <div class="advance-step-content">
        <h2>Store your API key safely</h2>
        <p>Save your TypeSafe key in a password manager (I use 1Password) instead of pasting it into Claude Code or your terminal. Anything you paste can end up in chat history or your shell history. Claude Code can read the key from the password manager each time the test runs, so it never shows on screen.</p>
      </div>
    </div>

    <div class="advance-step">
      <div class="advance-letter">2</div>
      <div class="advance-step-content">
        <h2>Install the TypeSafe skill in Claude Code</h2>
        <p>This gives Claude Code TypeSafe's own instructions for building with Jev. Paste this into Claude Code:</p>
        <div style="background:#F6F1EB;border:1px solid #D9CEC3;border-left:4px solid #877167;border-radius:8px;padding:14px 18px;margin:12px 0;font-family:'SFMono-Regular',Menlo,Consolas,monospace;font-size:0.9rem;line-height:1.55;color:#3f342f;white-space:pre-wrap;"><span style="display:block;font-family:Inter,sans-serif;font-size:0.72rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;color:#736962;margin-bottom:6px;">Paste into Claude Code</span>Install the TypeSafe skill: run claude plugin marketplace add typesafe-ai/skills, then claude plugin install typesafe@typesafe-ai.</div>
        <p>Before installing any plugin, ask Claude Code what it can access and where your data goes. This one is documentation only, with no hooks or background tools.</p>
      </div>
    </div>

    <div class="advance-step">
      <div class="advance-letter">3</div>
      <div class="advance-step-content">
        <h2>Kick off the test</h2>
        <p>Start a new folder for the project, open Claude Code there, and give it the full picture. This is the prompt to start with (fill in the brackets):</p>
        <div style="background:#F6F1EB;border:1px solid #D9CEC3;border-left:4px solid #877167;border-radius:8px;padding:14px 18px;margin:12px 0;font-family:'SFMono-Regular',Menlo,Consolas,monospace;font-size:0.9rem;line-height:1.55;color:#3f342f;white-space:pre-wrap;"><span style="display:block;font-family:Inter,sans-serif;font-size:0.72rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;color:#736962;margin-bottom:6px;">Paste into Claude Code</span>I want to see if Jev, TypeSafe's judging model, can grade my evals the way I do. My graded examples are in [where they live]. Each one has the AI output, the request it answered, and my 1 to 5 scores on [your rubric parts]. My brand voice guide and business facts are in [where]. Set up a calibration test: turn each rubric part into a Jev Score question, send Jev only the output, the request, and my guides, never my scores. Read my TypeSafe key from [your password manager] at run time and never print it. Run the requests in parallel and record time and cost. Then show me, for each rubric part, how often Jev is within a point of me, whether it runs harsher or kinder, and its confidence when it misses. Do a dry run with fake answers first, then wait for my go-ahead before the live run.</div>
        <p>Claude Code will build a few small files: the rubric as Jev questions, a scoring script, and a report. Ask it to explain anything you do not follow.</p>
      </div>
    </div>

    <div class="advance-step">
      <div class="advance-letter">4</div>
      <div class="advance-step-content">
        <h2>Run it and read the report</h2>
        <p>Say <strong>"run it live"</strong>. Look at three things for each rubric part: within a point of you, harsher or kinder, and confidence on the misses. My first run was close on tone and clarity, caught an add-on we cannot legally sell in Utah, and was much harsher than me on conciseness.</p>
        <p>One rubric part way off? Ask Claude Code to rewrite those score levels using your own grading notes, then rerun. Each rerun costs pennies.</p>
      </div>
    </div>

    <div class="advance-step">
      <div class="advance-letter">5</div>
      <div class="advance-step-content">
        <h2>Put a frontier model head to head</h2>
        <p>Where Jev disagrees with you, check whether a bigger model would do better. Store your Anthropic key the same way as in step 1, then:</p>
        <div style="background:#F6F1EB;border:1px solid #D9CEC3;border-left:4px solid #877167;border-radius:8px;padding:14px 18px;margin:12px 0;font-family:'SFMono-Regular',Menlo,Consolas,monospace;font-size:0.9rem;line-height:1.55;color:#3f342f;white-space:pre-wrap;"><span style="display:block;font-family:Inter,sans-serif;font-size:0.72rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;color:#736962;margin-bottom:6px;">Paste into Claude Code</span>Score [the rubric part Jev missed] on the same examples with Sonnet 5.5, using the exact same instructions and levels Jev got. Keep my scores out of the prompt, read the Anthropic key from [your password manager], and ask for a short reason with each score. Then compare me, Jev, and Sonnet side by side, with time and cost.</div>
        <p>Sonnet agreed with Jev, not me: the same score on 15 of 20 and within a point on all 20.</p>
      </div>
    </div>

    <div class="advance-step">
      <div class="advance-letter">6</div>
      <div class="advance-step-content">
        <h2>When the models agree, fix your rubric</h2>
        <p>Read the reasons Sonnet gave on the examples where you scored highest. Then tell Claude Code, in your own words, what you were really rewarding. Mine:</p>
        <div style="background:#F6F1EB;border:1px solid #D9CEC3;border-left:4px solid #877167;border-radius:8px;padding:14px 18px;margin:12px 0;font-family:'SFMono-Regular',Menlo,Consolas,monospace;font-size:0.9rem;line-height:1.55;color:#3f342f;white-space:pre-wrap;"><span style="display:block;font-family:Inter,sans-serif;font-size:0.72rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;color:#736962;margin-bottom:6px;">Paste into Claude Code</span>Repeated information counts, repeated feeling doesn't. Warmth for a frustrated customer earns its place. Missing information is not a conciseness problem. Add those rules to the question and rerun Jev and Sonnet.</div>
        <p>With those rules, Jev matched me within a point on <strong>14 of 15</strong>. Sonnet stayed at 10, at about <strong>80 times the cost per score</strong>.</p>
        <p><strong>Then stop tuning.</strong> I added a fourth rule and Jev got worse, so I took it out. Rules written from the same few examples make the score look better without proving anything.</p>
      </div>
    </div>

    <div class="advance-step">
      <div class="advance-letter">7</div>
      <div class="advance-step-content">
        <h2>Test on fresh drafts, graded blind</h2>
        <p>The real test is outputs Jev has never seen. Ask Claude Code:</p>
        <div style="background:#F6F1EB;border:1px solid #D9CEC3;border-left:4px solid #877167;border-radius:8px;padding:14px 18px;margin:12px 0;font-family:'SFMono-Regular',Menlo,Consolas,monospace;font-size:0.9rem;line-height:1.55;color:#3f342f;white-space:pre-wrap;"><span style="display:block;font-family:Inter,sans-serif;font-size:0.72rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;color:#736962;margin-bottom:6px;">Paste into Claude Code</span>Generate 15 fresh drafts from my current [skill or system prompt] for [real or sample requests], and give me a grading sheet with only the request and the draft. Once I've filled in my scores, run Jev on them using my current [skill] as the voice guide, and compare.</div>
        <p>Use your <strong>current</strong> instructions as the reference. Mine first graded against last year's voice guide, and brand voice matched me on only 1 of 15. With my current skill, it landed within a point on 12 to 15 of 15 for every rubric part.</p>
      </div>
    </div>

    <div class="advance-step">
      <div class="advance-letter">8</div>
      <div class="advance-step-content">
        <h2>Use confidence to choose what you review</h2>
        <p>Every Jev score comes with a confidence number. Ask Claude Code: <strong>"Would reviewing only Jev's lowest-confidence scores have caught its misses?"</strong> On my fresh set, the lowest-confidence quarter caught 4 of its 6 big misses. That is a small sample, so check it on your own data before relying on it.</p>
      </div>
    </div>

  </div>
</section>

<section class="advance-intro">
  <div class="container">
    <h2>What it cost</h2>
    <p>Jev charges for input only, and every Jev run in my test cost about half a cent. All the Jev runs together came to a few cents. The Sonnet head-to-head was about 6 to 7 cents per run, for one rubric part.</p>
  </div>
</section>

<section class="advance-intro">
  <div class="container">
    <h2>Where Jev fits, and where it doesn't</h2>
    <p><strong>Good fit:</strong> high-volume, repeatable judgments, like scoring every draft on tone or flagging anything that breaks a policy.</p>
    <p><strong>Keep for yourself or a bigger model:</strong> the subtle calls. Jev missed my "be more casual with someone I work with every week" note. Its own docs list math and dates as weak spots, so keep those in code.</p>
    <p><strong>If you use Claude Code's plugin evals:</strong> they cannot call an outside grader directly, so run Jev on their results as a step afterward.</p>
  </div>
</section>

<section class="advance-cta">
  <div class="container">
    <p class="advance-cta-headline">Want help setting up evals for your own AI work?</p>
    <p class="advance-cta-sub">We can build your first rubric and answer key together in one hour.</p>
    <a href="/start" class="btn btn-primary">Get Started with AI ($150)</a>
  </div>
</section>
