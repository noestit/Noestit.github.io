---
layout: single
title: "Architectural decision records"
permalink: /documentationtechniques/adr/architectural-decision-record

sidebar:
  nav: "documentationtechniques"
---

An Architectural Decision (AD) is a software design choice that addresses a functional or non-functional requirement that is architecturally significant. To keep track of '_architecturally significant_' decisions made within the project course, we document the Architectural Decisions in ADRs (Architectural Decision Records). 

## What is an architecture decision record?

An **architecture decision record** (ADR) is a document that captures an important architectural decision made along with its context and consequences.

An **architecture decision** (AD) is a software design choice that addresses a significant requirement.

An **architecture decision log** (ADL) is the collection of all ADRs created and maintained for a particular project (or organization).

An **architecturally-significant requirement** (ASR) is a requirement that has a measurable effect on a software system’s architecture.

All these are within the topic of **architecture knowledge management** (AKM).

The goal of this document is to provide a fast overview of ADRs, how to create them, and where to look for more information.

Abbreviations:

  * **AD**: architecture decision

  * **ADL**: architecture decision log

  * **ADR**: architecture decision record

  * **AKM**: architecture knowledge management

  * **ASR**: architecturally-significant requirement


_**Architecturally Significant decisions** are those that affect the structure, non-functional characteristics, dependencies, 
    interfaces or construction techniques_.

### Keys of what your ADR should be
- ADRs should be small, modular documents with at least the change to be updated
- ADRs should at all times reflect the trade off of the AD
- With ADRs it should be possible to keep track of motivations behind certain decisions for the entire software cycle
- With ADRs it should be possible for new people to easily see how and why the software was implemented/build as is

### Structure of a ADR

- Title: The documents have names that are short noun phrases. Prefixed with ADR # (ex. 'ADR 1: LDAP for Multitenant Integration')
- Status: A decision may be '**proposed**' if the PO (product owner) haven't agreed with it yet, or '**accepted**' once it is agreed. If a later ADR changes or reverses a decision, it may be marked as '**deprecated**' or '**superseded**' with a reference to its replacement. Other statuses 
- Context: Describes the forces at play including technological, political, social and project local. These forces are probably in tension, and should be called out as such. The language in this section is value-neutral. It is simply describing facts.
- Decision: Describes our response to these forces. It is stated in full sentences, with active voice. "**We will ...**"
- Consequences: This describes the resulting context, after applying the decision. All consequences should be listed here, Positive, Negative and Neutral consequences that affect the team and project in the future.

### Links
- [Michael Nygard - documenting-architecture-decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)
- [Architectural decision from Wikipedia](https://en.wikipedia.org/wiki/Architectural_decision)