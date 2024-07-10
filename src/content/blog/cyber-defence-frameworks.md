---
title: Cyber Defence Frameworks
author: kobejk
pubDatetime: 2024-07-10
featured: false
draft: false
tags:
  - security
description: A brief overview of some cyber security defence frameworks.
---

Cyber Defence Frameworks are guidelines and best practices designed to help protect information systems from cyber threats.

## Table of contents

## An introduction to frameworks

Different entities abide by different types of frameworks. The industry has many standards, but some are more common than others.

Here are some popular frameworks recognised by the industry:

- Pyramid of Pain
- Cyber Kill Chain
- Unified Kill Chain
- Diamond Model
- MITRE ATT&CK

I'll briefly go over a few below.

## The Pyramid of Pain

### Overview

The Pyramid of Pain is a model used to show the level of difficulty for an attacker to complete their objectives when defenders block certain types of indicators.

The higher the difficulty, the harder it is for an attacker to adapt the blocked technique.

![The Pyramid of Pain diagram.](@assets/images/pyramid-of-pain.png)

### Structure

It starts with simple indicators such as:

- file hashes
- ip addresses

These are easy to block and replace. They are also easy for attackers to work around.

As you move up the pyramid, indicators get a little bit harder for attackers to change such as:

- domain names
- network artifacts

At the top are the attackers tactics, techniques and procedures (TTPs), which are the hardest to change.

Blocking these causes the most disruption, as the attackers need to rethink their strategy.

### Implementation

The framework is implemented during cyber defense operations. When defenders detect a cyber threat, they use this pyramid to decide what to target based on the attacker.

You can read more [here](https://www.attackiq.com/glossary/pyramid-of-pain/).

## The Cyber Kill Chain

The Cyber Kill Chain is a model that outlines the stages of a cyber attack, from initial reconnaissance to data exfiltration.

The original model has 7 phases:

1. reconnaissance
2. weaponisation
3. delivery
4. exploitation
5. installation
6. command and control
7. actions on objectives

## The MITRE ATT&CK Framework

The MITRE ATT&CK Framework is a knowledge base of cyber adversary tactics and techniques.

This list is overseen by the MITRE organisation, and is based off real world attackers.

It has the following characteristics:

- the stages of cyber attackes
- descriptions of how attackers operate
- example indicators of compromise (IOCs) and how to detect them
- mitigations that can be put in place

It helps identify what attackers are doing, how they are doing it, and what defenses can be implemented.

## Other resources

Below are some resources for further reading if interested.

- https://www.sans.org/tools/the-pyramid-of-pain/
- https://www.attackiq.com/glossary/pyramid-of-pain/
- https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html
- https://www.crowdstrike.com/cybersecurity-101/cyber-kill-chain/
- https://www.mitre.org/who-we-are
- https://attack.mitre.org/
