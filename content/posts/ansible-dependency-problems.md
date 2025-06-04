---
title: "The Unexpected Mess of Ansible Dependency Management"
author: "Sebastian Yaghoubi"
date: 2025-01-10
description: |
  A Trek Through the Jungle of Ansible’s Dependency Management Complexities.
summary: |
  While working on some Ansible roles for my Day-1 Homelab Ops, I
  discovered that managing dependencies in Ansible isn't as straightforward as
  one might expect.
# cover:
#     alt: "" # alt text displayed if image can't load
#     caption: "" # display caption under cover
#     image: "<image path/url>" # image path/url
tags: ["Ansible", "DevOps", "Automation", "Homelab", "Infrastructure-as-Code"]
keywords: ["Ansible", "Dependency Management", "DevOps", "Homelab", "Automation"]
---

Well folks, buckle up for a story that wasn't supposed to be a story at all.
What started as a simple "let me document my homelab migration" turned into a
fascinating journey through the wonderland of Ansible dependency management. And
by fascinating, I mean "why is this so unnecessarily complicated?"

## A Bit of History (Because Context is Everything)

Let's travel back to the simpler times, pre-2020, before Ansible decided we all
needed a more "sophisticated" approach to role management. Back then, life was
straightforward: one repo per role, upload to Ansible Galaxy, done. Need to use
a role? Just add `namespace.role` to your `requirements.yaml`, run
`ansible-galaxy role install -r requirements.yaml`, and you're off to the races.

These `requirements.yaml` files were actually quite nice - you could name your
roles (shocking, I know), pull from sources other than Ansible Galaxy, and
generally live a peaceful existence. This process worked perfectly fine when
pulling in a few remote roles for a playbook.

But oh, you want to do anything beyond that? Well... _grabs popcorn_

## The Problems I Ran Into (Or: How I Learned to Stop Worrying and Love the Pain)

Picture this: there I was, innocently setting up an Ansible role to install a
DHCP server for my new homelab. It turned out my DHCP role needed EPEL (Extra
Packages for Enterprise Linux) to install the DHCP package. Being the good
developer I am (pat on the back), I thought, "Let's keep things clean and follow
single responsibility principles!" My `ansible-role-dhcp` role needed EPEL. No
problem, right? I already had a role for that!

Oh, isn't that adorable. Past me was so naive.

And this is where things got interesting.

### Ansible Role Dependency Handling: A Comedy of Errors

So, Ansible roles have this thing called `meta/main.yaml` for handling
dependencies. Great! Problem solved, right?

Ha. Ha... If only.

I thought it would be as simple as:

```yaml
dependencies:
  - name: syaghoubi00.epel
    src: https://github.com/syaghoubi00/ansible-role-epel
```

Spoiler alert: it wasn't.

#### Problem #1: You Can't Name Roles Within a Dependency

Because obviously, why would you want to do something so logical? I quickly
discovered you can't name roles within a dependency declaration. Instead,
Ansible Galaxy decides to install the dependency as `ansible-role-epel`,
dropping any namespaces and stubbornly naming the role as the name of the repo
from the `src`. This broke the expected inclusion pattern of `syaghoubi00.epel`.

Beautiful.

#### Problem #2: Ansible Galaxy is Currently Broken

"Well," I thought, "I'll just upload it to Ansible Galaxy!"

But it wasn't that simple.

Turns out, since the migration to Ansible Galaxy NG (because we definitely
needed that), where collections became the new golden child, individual roles
have been demoted to "legacy" status. And boy, does that "legacy" status shine
through in the bug count. Want to upload roles from a different branch? Good
luck with that!

#### Problem #3: The Pre-requisite Dance

"_Fine_" I muttered, "I'll drop the namespaces and just use a dependency."

But wait! There's more! The `meta/main.yaml` dependency logic decides to run
dependencies before all other tasks. Because apparently, flexibility is
overrated. Need to include that role in the middle of your tasks? Too bad!

This rigid ordering doesn't work when you need to include the dependent role's
tasks at a specific point within your role's execution.

#### Problem #4: The Requirements That Aren't Required

Deep in the documentation (where hope goes to die), there are mentions of a
`meta/requirements.yaml`. Perfect, right? All the abilities of a normal
`requirements.yaml`, with the bonus of being able to name roles!

Except... it doesn't resolve dependencies automatically. Because of course it
doesn't.

After burning through four different approaches and watching each one fail
spectacularly, I had to face the truth: maybe, just maybe, there was a reason
Ansible was pushing everyone toward collections. Not that I was happy about it,
but at least I understood the why of it all.

## Submit to the Ansible Collection Paradigm (Or: Resistance is Futile)

At this point, you might be thinking, "Geez, that seemed like a lot of work just
to avoid using a collection."

Yes. Yes, it was. But let me tell you why I was trying to avoid collections in
the first place.

### Collections: The Giant Monorepo Nobody Asked For

Collections are essentially giant monorepos. Sure, I tried to work around this
with git submodules. I even tried using a requirements file and installing the
roles with git sources to the repo using a custom path. But both approaches just
led to more mess and complexity.

Want to manually manage a changelog and try to manually do semver bumping? Hope
you enjoy pain! With a monorepo, this could be automated using commit history,
but good luck doing that with the submodules or requirements approaches.

### Why I've Been Avoiding the Collections Monorepo

Here's a fun question: at what point does a monorepo become too much to manage?
20+ roles? 50? And what if I only need a single role - now I have to pull in the
entire collection? That seems... efficient.

Collections aren't without their drawbacks:

1. **Monorepo Management**: As the number of roles grows, repository management
   becomes more complex.
2. **All-or-Nothing Updates**: Changes to a single role affect the entire
   collection's versioning.
3. **Loss of Individual Role Versioning**: You can't tag releases for individual
   roles anymore.

## The Silver Lining (Because We Need Something Positive)

After all this complaining (_some_ of it justified, I might add), I have to
admit there are a few advantages to collections (but don't tell Ansible I said
this).

### The Good Parts

1. One command to rule them all:
   `ansible-galaxy collection install syaghoubi00.homelab`
2. Efficient distribution thanks to tarball compression (I would test the size
   differences, but since I'm stuck with collections anyway, why bother?)
3. Automated version management

### Making the Best of It

If you're going to be forced into the collections world, here's how to make it
less painful:

- Group related roles into collections based on their purpose (e.g., `homelab`,
  `security`, `monitoring`)
- Start any new projects with collections rather than individual roles - trust
  me, future you will be grateful
- Embrace the monorepo workflow (if you can't beat 'em, join 'em)

## Conclusion

So here we are, at the end of this unexpected journey through Ansible dependency
management. What started as a simple homelab role turned into a deep dive into
the evolution of Ansible's tooling - from the simplicity of individual roles to
the "sophisticated" world of collections.

Am I happy about migrating all my individual role repos to a giant collections
repo? Not particularly. Did I have much choice? Also not particularly. But
that's the thing about working with tools in the ever-evolving landscape of
DevOps - sometimes you have to adapt to the platform's vision, even when that
vision feels like it's complicating your life.

For those still clinging to individual role repositories (I see you, and I
understand), start planning your migration to collections now. The writing is on
the wall - the "legacy" status of individual role management in Ansible Galaxy
isn't just a label, it's a glimpse into your future headaches if you don't
adapt.

The moral of this story? Maybe it's that everything eventually becomes a
monorepo. Or perhaps it's that dependency management is just universally painful
across all technologies. But more likely, it's that sometimes the path of least
resistance is to accept that fighting against the tool's preferred patterns is
more painful than adapting to them - even if those patterns seem unnecessarily
complicated.

Choose your own moral. I'll be here, migrating my roles to collections and
pretending this is fine.

This is fine.

_...sips coffee while staring at terminal..._
