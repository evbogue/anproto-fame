# Architecture

## Product layers

```text
             ANProto Fame
       research + product model
                 |
              Wiredove
   publishing / audience / CRM / analytics
                 |
      +----------+----------+
      |          |          |
     Web       ANProto     SSB
 canonical   signatures   optional
 publishing  provenance   replication
      |
   external platforms
 distribution channels
```

## Design rule

The product model must not depend on any one transport or social protocol.

A canonical artifact should remain meaningful if it is:

- served over HTTP
- stored in Git
- signed with ANProto
- replicated through SSB
- exported as JSON
- syndicated to a social platform

## Canonical objects

The application should converge on a small set of interoperable objects.

### Identity

Represents the durable creator identity.

May reference:

- domains
- cryptographic keys
- social accounts
- public profiles
- projects

### Artifact

Something intentionally published.

Examples:

- post
- essay
- image
- video
- audio
- talk
- project
- release

Suggested fields:

```text
id
type
author
created
canonical_url
title
body / media references
references
provenance
distribution
```

### Interaction

Evidence that a person or community encountered an artifact.

Examples:

- reply
- mention
- citation
- reshare
- event attendance
- direct message
- conversation

### Relationship

A durable connection between people.

It should preserve context rather than collapse to "follow."

Examples:

- collaborator
- organizer
- journalist
- friend
- community member
- client
- repeat supporter

### Outcome

Something consequential that followed from attention.

Examples:

- invitation
- collaboration
- job
- sale
- press
- introduction
- speaking opportunity
- project contribution

This allows the system to model:

```text
artifact
   |
interaction
   |
relationship
   |
outcome
```

That chain is more useful for researching sustainable fame than an impression counter.

## ANProto's role

ANProto is useful when cryptographic authentication adds something concrete.

Potential roles:

- identity keys
- artifact signatures
- provenance
- signed endorsements
- verifiable references
- portable attestations

ANProto should not automatically absorb:

- media transport
- replication
- database storage
- recommendation algorithms
- social graph semantics

Those belong at other layers.

## SSB's role

SSB can be explored as an optional backend for:

- offline archives
- peer replication
- signed social data
- community-owned datasets

The project should consume SSB capabilities where useful rather than target SSB feature parity.

## Data ownership

The complete user dataset must have a straightforward export representation.

A useful baseline is a directory containing:

```text
identity.json
artifacts/
people/
relationships/
interactions/
outcomes/
media/
```

No essential user state should exist only inside an external platform API.

## Local-first bias

Audience intelligence and relationship memory are unusually personal datasets.

Prefer:

- local storage
- explicit synchronization
- user-owned backups
- selective publishing

over centralized collection by default.
