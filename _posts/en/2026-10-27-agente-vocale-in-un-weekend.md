---
layout: post
title: "A voice agent in a weekend? Sure, until it has to talk to your grandma"
date: 2026-10-27 09:00:00 +0100
categories: [il-timone]
tags: [agenti-vocali, gdpr, ai-act, costi, stories]
image:
  path: /assets/img/agente-vocale-nonna-italiana.png
  alt: "Illustration: from the stage of the 'voice agent in 20 minutes' demo, a road with four signposts (the voice, data outside the EU, the budget, the AI Act) leads to a grandmother on the phone; on the right, the iceberg of the system, with the LLM as just its tip"
---

*Originally published in Italian on October 27, 2026.*

You know the promise, because these days it's everywhere: "your voice agent in twenty minutes, without writing a single line of code". The recipe is always the same. Take a synthetic voice platform like ElevenLabs, plug in a realtime model like OpenAI's, add an automation that saves the conversation somewhere, and you're done. You've got an AI that answers the phone, books appointments, keeps people company. All it needs is a bow on top.

And I'll say it right away, because it's only fair: **the demo really works.** In one afternoon you hear an agent talking to you, understanding what you say and answering with a voice that two years ago would have sounded like science fiction. Anyone who dismisses it all as marketing has probably never tried it.

Then I had to build one for 85-year-olds, in Italy. And the demo turned out to be the easy part.

Careful, folks: all that glitters is not gold. Let me explain why.

First, though, a premise that applies to the whole blog: you won't find the latest industry news here, but AI's promises put to the test in the field, with the flaws and the assumptions the demos don't show. Why I do it, and who's behind it, I explained in [About](/about/).

## The context, in three lines

Since September I've been CTO of Stories, a voice companion for older adults: someone to chat with every day, who remembers you and keeps the family a little closer. It is not a medical app and it is not an emergency alarm service — and later on we'll see that this "it is not" carries a lot more weight than it seems.

I'm telling you this for one reason only: I ran into every trap below there, in the field, and not in a tutorial.

## Trap 1: the voice isn't right

The "phenomenal" voices in the demos are built and tested mostly in English, for an audience that listens to podcasts at 1.5x speed. In Italian they can have a slightly off accent, a prosody (I wrote about it in [The soul of the voice](/posts/anima-della-voce-prosodia-ai/)) that lands in the wrong place, a rhythm too fast for an 85-year-old ear. To us it sounds natural. To her it sounds like "that young lady who talks funny".

And the problem isn't only on the way out. Speech recognition struggles with older voices, which are weaker, shakier, sometimes slurred. It struggles with dialect, or even just with regional Italian. But above all it struggles with pauses. An older person stops mid-sentence, searches for the word, picks up again three seconds later. In those three seconds the demo agent has already decided you're done and is talking over you — like a grandson finishing your sentences, minus the affection.

Figuring out when the other person has finished speaking (**turn-taking**) is, in the tutorials, a slider in a settings panel. For us it became a design problem, because if you interrupt a grandma twice, the third time she won't call back.

The warning here is simple: you picked the demo's voice, but the product's voice is judged by whoever listens to it.

## Trap 2: the data leaves the EU

Here the tone gets less fun. In the standard recipe, audio and transcripts go through the servers of American companies, and an older person's conversations almost always contain health data: blood pressure, the pill, Thursday's checkup, "I didn't sleep last night". Under the GDPR that is **special category data** (Article 9), the kind where the rules get really serious.

The good news is that options to keep data in Europe exist. The bad news is where they sit. I went and checked the official sources of the two providers in the recipe:

- **ElevenLabs** offers EU data residency, but describes it as a feature exclusive to Enterprise customers. And even there, the documentation warns that optional integrations, like an external LLM or post-call webhooks, may still process data outside the region.
- **OpenAI** lets you create API projects with European residency and zero data retention, but only for "eligible customers", on eligible endpoints, and without being able to convert an existing project.

So compliance is available: it comes with a price tag and a contract to negotiate. Which leads straight to trap 3.

Then there's **data minimisation**: you don't need the raw audio, so you shouldn't keep it. Easy to say. But when the pipeline runs on a platform that isn't yours, can you really prove where every file ends up and how long it stays there? Writing it in a privacy policy takes one line; proving it is a different job altogether.

## Trap 3: the budget blows up

In the recipe you pay for three things by the minute: speech recognition, the model that thinks, and the synthesis that speaks. Taken one by one, they're small amounts. The trouble starts when you multiply them.

Let's run the numbers, deliberately as examples, taken from public price lists and not from Stories. A managed voice platform today costs around 8 US cents per minute, and the language model isn't included: it's billed separately. A top-tier realtime model, just for audio in and out, runs between 3 and 6 dollars for a full hour of conversation. Rounding generously, an hour of chatting costs a few dollars.

Now take a grandma who talks for an hour a day, every day. That's thirty hours a month, and at that point the cost of a single user easily exceeds what a family is willing to pay for a subscription. And mind you: long, daily conversations aren't an exception to handle, they're exactly the product's use case.

It's the same Ferrari that burns a litre every hundred metres I talked about in [AI, you're amazing! Yes, but how much do you cost me?](/posts/ai-fantastica-ma-quanto-mi-costi/). Except here the engine stays on for an hour a day for every customer.

The consequence is almost unavoidable: local models, or models on your own servers in the EU, which by the way also solve trap 2 in one go. But it's no free lunch. All the work the platform used to do for you lands back on your desk: GPUs to size, latency to chase (in voice, half a second more is very noticeable), maintenance, updates and, above all, quality to **measure again** from scratch every time you swap a piece.

## Trap 4: you won't find the AI Act in the tutorial

In not one "voice agent in twenty minutes" video have I ever heard the AI Act mentioned. And yet it's there, and for a voice agent it has at least three points of contact. Necessary disclaimer: I'm not a lawyer, and this is my reading as an engineer, to be checked with someone who does this for a living.

**Transparency.** Article 50 has applied since August 2, 2026, and the Digital Omnibus didn't move it: a system that interacts with people must let them know it's a machine, unless that's obvious. With an 85-year-old user and an almost human voice, it's never obvious. So it has to be said, and repeated in a way that sticks.

**Emotion recognition.** This is the least obvious trap, and the one I spent the longest thinking about. The idea comes naturally: "let's have the agent tell from her tone of voice whether grandma is sad". Too bad the AI Act defines an **emotion recognition system** as one that infers emotions from biometric data — and voice is biometric data. Such a system has its own disclosure obligations and ends up among the high-risk systems of Annex III. Inferring someone's mood from *what* they say is one thing; inferring it from *how* they say it puts you under a different regime.

**Medical devices.** If the agent starts detecting signs of illness ("her voice is more slurred than usual, it might be...") it stops being a companion and becomes software with a medical purpose. It falls under the medical device rules and, when it needs a notified body's assessment (common for software that helps with diagnosis), the AI Act treats it as high-risk among regulated products.

On dates, to avoid any confusion: with the Digital Omnibus, in force since July 27, high-risk obligations have slipped to December 2, 2027 for Annex III systems and to August 2, 2028 for those built into regulated products (I wrote about it in [August 2 has arrived. Now what?](/posts/ai-act-2-agosto-e-adesso/)). Postponed, not abolished: a product you design today will still be around on those dates.

And that's why the earlier "it is not" carried so much weight. **Every "Stories is not…" is an architectural choice** that keeps the product out of a much heavier regime. We don't read emotions from the voice and we don't make diagnoses: those features are technically within reach, and we decided not to build them.

## The bill: what you actually need

Let's line it all up. On the left, what the platform promises; on the right, what you need when the user is an elderly Italian woman.

| Piece | What the platform promises | What you need in Italy |
|---|---|---|
| Voice in | Accurate transcription, automatic turn detection | Recognition tuned to older voices and regional Italian, turn-taking that tolerates long pauses |
| Safety filters | Generic content moderation | Rules on what the agent must never say (medical advice, medication, money) and on what to do when a sign of distress shows up |
| Orchestrator | A flow drawn with blocks | Logic that decides when to remember, when to ask, when to alert the family |
| Model | The best model of the moment | A model that costs the right amount, runs in the EU, and whose quality you can measure |
| Per-family memory | The call history | Persistent memory, separate for each person and each family, with clear rules on what is kept |
| Voice out | "Phenomenal" voices from a catalogue | An Italian voice with rhythm and prosody suited to the listener, not to whoever built the demo |
| Summaries for the family | A post-call webhook | Summaries that are useful but respectful, without turning the companion into a spy |
| Logs and monitoring | A dashboard of minutes consumed | Traceability for GDPR and the AI Act, cost per conversation, quality over time |

Looking at the table, there's one sentence I take away: **the LLM is the brain, not the system.** And the brain, paradoxically, is the easiest piece to buy.

## Someone has to be at the helm

Let me be clear: the message is not "don't use ElevenLabs" or "stay away from realtime models". They're excellent tools, and for prototyping they're unbeatable. The point is knowing what you're buying — and what you still have to build.

If you're about to pick a platform for a voice agent, before falling in love with the demo, ask yourself three questions:

- **Where does the data go?** Not in general: on which plan, under which contract, and what happens with the integrations you'll add later.
- **How much does an hour of conversation cost?** All of it, adding up listening, model and voice. Then multiply it by your users' real usage, not the demo's.
- **Who decides what the agent must never say?** If the answer is "the system prompt", you still have work to do.

That was the map. In the next posts I'll go into each trap in detail: the guardrail and how to measure it, what an hour of conversation really costs, and the GDPR applied to older people's conversations.

Meanwhile, I'll turn the question to you: if you've put a voice agent into production, what was the first thing that broke after the demo? The voice, the costs, or the first phone call from the DPO? Tell me in the comments or write to me through the form below: these problems are easier to understand when you put them side by side.
