---
layout: post
title: Is it a building, service or something else?
---

When we were creating the architecture behind our tool we came across a huge discussion about the naming of the 'things' we were generating.
When can we speak of:
- a building?
- a service?
- an organisation?

The most interesting part of the discussion was that you can have an organisation that's using several buildings and provides several services.
In the following post we will discuss how we tackled this problem and why we think our approach is the right one in this proof-of-concept.

## Our approach

### Buildings

We decided to name something a building if it has an address in Belgium. In our opinion this is the easiest way since we 
have access to the Flemish building registry.

### Services and organisations

In our tool, an organisation provides several services to the public with certain openings hours.
Each organisation can provide multiple services. This circumvents the issue that we discussed already in the introduction.

An organisation can own multiple buildings, but each service is tightly connected to the building where it serves the citizens.

## Example

To describe our approach even better, we will use the following example: the administration of a city (organisation).

### Buildings

The administration of the city can be located in several buildings with a couple of services in each building.

### Services

- You need to get your ID in building A
- The birth of your child needs to be registered in building B
- ...
