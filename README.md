# ANProto Fame

**Researching sustainable internet fame.**

ANProto Fame is an open research and software project exploring how a person can build durable public recognition, reputation, audience, and opportunity without becoming dependent on a single social platform.

The product direction is an **open-source influencer operating system**: tools for owning your identity, publishing canonically, syndicating outward, understanding your real audience, preserving attribution, and turning attention into durable relationships and opportunities.

## Thesis

Internet fame is usually optimized for short-term reach inside systems you do not control. We want to study a different model:

> **Sustainable Fame = durable recognition × relationship quality × portability ÷ maintenance burden**

The point is not to maximize followers. The point is to make influence:

- durable across years
- portable across platforms
- connected to real relationships
- attributable to the person who created the work
- useful without constant engagement farming
- resilient when platforms disappear or algorithms change

## What we're building

The first experiments focus on:

1. **Canonical identity** — one durable identity for posts, projects, media, appearances, endorsements, and collaborations.
2. **Canonical publishing** — publish from infrastructure you control, then syndicate outward.
3. **POSSE** — Publish on your Own Site, Syndicate Elsewhere.
4. **Audience graph** — distinguish followers from people who repeatedly engage, cite, collaborate, invite, introduce, or republish.
5. **Reputation objects** — public records of projects, talks, press, endorsements, collaborations, and references.
6. **Influence analytics** — measure repeat attention, relationship depth, portability, downstream sharing, and real-world outcomes.
7. **Content provenance** — preserve authorship and attribution as content moves across systems.
8. **Media workflows** — essays, short posts, images, audio, video, talks, and project updates.
9. **Relationship memory** — lightweight tools for remembering collaborators, organizers, journalists, communities, and repeat supporters.
10. **AI-assisted repurposing** — transform one canonical artifact into platform-specific versions while preserving provenance.
11. **Exportability** — your archive, graph, reputation, and metrics remain useful even if every current social platform disappears.

## What this is not

This is **not** an attempt to recreate Secure Scuttlebutt feature-for-feature.

SSB may be useful as a storage or replication backend. ANProto may be useful as an authentication and provenance layer. Git, HTTP, websites, feeds, and other systems should remain themselves.

The research target is sustainable internet fame, not protocol purity.

## Architecture direction

```text
                 ANProto Fame
        research + influencer tooling
                     |
                  Wiredove
      publishing / audience / reputation
                     |
       +-------------+-------------+
       |             |             |
     ANProto         SSB          Web/Git
 identity/provenance optional     canonical media
```

ANProto should stay small: authenticate objects, identities, references, and provenance.

Wiredove can become the user-facing operating environment for publishing, syndication, audience intelligence, reputation, and relationship memory.

## Research questions

- Can internet fame be made portable?
- What forms of recognition survive platform changes?
- Which signals predict durable influence better than follower count?
- Can reputation be represented without turning it into a centralized score?
- How much publishing work can be automated without making a person's voice generic?
- What is the minimum maintenance burden required to remain meaningfully visible?
- Can online recognition reliably create offline relationships and opportunities?
- How should attribution survive copying, remixing, screenshots, AI transformation, and syndication?
- Can an individual own enough of their social graph to leave a platform without starting over?

## Status

Early research and prototyping.

See [ROADMAP.md](ROADMAP.md), [RESEARCH.md](RESEARCH.md), [PRINCIPLES.md](PRINCIPLES.md), and [ARCHITECTURE.md](ARCHITECTURE.md).
