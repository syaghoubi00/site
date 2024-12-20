---
title: "A Wild Blog Appeared!"
author: "Sebastian Yaghoubi"
date: "2024-11-16T13:31:29-08:00"
description: "Blogs and Binaries and CLI, Oh My"
summary: |
  A technical blog has been on my to-do list for a while now.
  With a home infrastructure rebuild on the way
  it seems like a good time to kick one off.
cover:
  image: "images/wild-pokemon-appears.jpg"
  alt: "A wild blog meme"
tags: ["hugo", "cli"]
---

I've been wanting to document some of the projects I'm working on,
and a blog seems like a great way to do that.
I also often run into problems, and a blog may help others solve similar issues
(_definitely not foreshadowing for later on in this post_ :stuck_out_tongue_winking_eye:).

But first - I need a blog!

## A Blog You Say?

I've wanted to try out a static site generator since I first heard about
them a few years ago (yes - I'm ashamed to say that this has been on my
to-do list for that long :grimacing:). Hugo is always highly recommended,
and with the recent [WordPress debacle](https://www.theverge.com/2024/9/27/24256361/wordpress-wp-engine-drama-explained-matt-mullenweg),
it was at the top of everyone's recommendation list as an alternative.
So - that's what I went with.

Getting started was easy enough, following the quick start guide
on the Hugo website, <https://gohugo.io/getting-started/quick-start/>.

### Installing Hugo

I headed over to <https://gohugo.io/installation/linux/>.
Lucky me - there was a native package available for Fedora
(my current favorite distribution for development work -
I may write a future blog post on why I've settled on Fedora
for dev work, so stay tuned for that).

Unfortunately the version packaged in Fedora is too old -
which as another aside, I've been meaning to get into maintaining
some packages, so maybe I could start by updating the package
(another item on the to-do list :sweat_smile:)!

So - let's grab the latest binary from Hugo's GitHub release page
<https://github.com/gohugoio/hugo/releases/latest>.
I downloaded the latest version, extracted the tarball,
moved the binary into my `$PATH`, and everything worked -
well for the most part.

#### Streamlining the Binary Download

![one does not simply download a binary from github](./images/one-does-not-simply.jpg)

Since I figured I would be working with Hugo a lot moving forward,
I wanted to add it to my [toolbx](https://containertoolbx.org/) `Containerfile`
(another future post inbound on container based development workflow).
Unfortunately, due to how Hugo has their releases setup
there isn't an easy way to grab just the binary from the release page.

> **Problem #1**: Hugo adds the version of the release to the filename.

This prevents the ability to grab the latest release using a constant path,
such as `https://github.com/gohugoio/hugo/releases/latest/download/hugo_extended-linux-amd64.tar.gz`,
since the `hugo_extended_${version}_linux-amd64.tar.gz` has to be included.

_Annoying._

So - now, to create a little workaround to get the `$version` of the latest release.

##### You Named Them What??

A quick search to avoid duplicating work is always a smart move;
and what do you know, just what I needed, a page on one liners to
grab the version of the latest release
[One Liner to Download the Latest Release from Github Repo - Gist](https://gist.github.com/steinwaywhw/a4cd19cda655b8249d908261a62687f8).
The cleanest solution seemed to be using the GitHub API and good ol' `jq`.

```sh
curl -s https://api.github.com/repos/gohugoio/hugo/releases/latest | jq -r '.tag_name'
```

> **Problem #2**: The GitHub `tag_name` differs from the filename `version` tag.

While this gave me the necessary version, it came prepended with a `v` for
the version - which isn't prepended to the version in the Hugo release filename.

_Argh!_

Nothing a little coreutils CLI magic using `cut` won't solve.
Let's grab everything after the first character.

```sh
curl -s https://api.github.com/repos/gohugoio/hugo/releases/latest | jq -r '.tag_name' | cut -c 2-
```

Great - now we have the `version` to add to the filename path of the `latest` release.
Nothing like a little detour to keep things interesting :unamused:.

Now we are finally able to grab the archive of the latest release.

##### Packed with Potential... Not

Instead of just providing a binary we can save directly
to our path with something like:

```sh
wget -qO ~/.local/bin/hugo https://github.com/gohugoio/hugo/releases/latest/download/hugo_extended_${version}_linux-amd64.tar.gz
```

> :mag: Wait a second - `wget`? Weren't you just using `curl`?
>
> Yes! I often default to `wget` because of
> its inclusion in `busybox`, but `curl` gets the job done too.
> Feel free to use whichever you prefer.

Hugo decided to create a compressed archive including
a `README` and `LICENSE` along with the binary.
I guess they want to make us work for it.

> **Problem #3**: Including unnecessary files along with the binary.

_Yay_ :confused:.

Ok. Well this is nothing I haven't dealt with before.
Some more CLI magic and we should be on our way.

```sh
wget -qO- https://github.com/gohugoio/hugo/releases/latest/download/hugo_extended_${version}_linux-amd64.tar.gz | tar xz hugo
```

Pipe the stdout from `wget` into `tar`,
extracting with `x` and decompressing with `z`,
and only extracting the file named `hugo` from the archive.

Great - we _FINALLY_ have a binary :triumph:.

#### Grabbing the Hugo Binary

Now we can put it all together.
We can get the latest version of the `hugo` binary
and extract it to `~/.local/bin/`.

```sh
hugo_latest_version=$(wget -qO- https://api.github.com/repos/gohugoio/hugo/releases/latest | jq -r '.tag_name' | cut -c 2-)
wget -qO- https://github.com/gohugoio/hugo/releases/latest/download/hugo_extended_${hugo_latest_version}_linux-amd64.tar.gz | tar xzv -C ~/.local/bin/ hugo
```

> :spiral_notepad: Note
>
> If using the above snippet to build a container
> be sure to extract to `/bin/`, as `~/.local/bin/` won't be available.

_Phew!_ - That was a lot of work to get a binary :sweat:.

#### Back on Track

Now that all that executable nonsense is sorted out -
I can get back to actually setting up this blog.
I followed the rest of the quick start guide, then got to the part on picking a theme.

Hmm. What other themes are available at <https://themes.gohugo.io/>.

_Uh-oh. That's a lot of options._

Rather than pursuing the perfect theme,
I decide to just get started with the first decent option I found.

The theme will likely evolve over time,
and I may even try to write my own to get some webdev/front-end experience.

But hey look at that - I have a blog now!

#### Lessons Learned

##### Problem Recap

1. Hugo added the version of the release to the filename.
2. The GitHub `tag_name` differs from the filename `version` tag.
3. Unnecessary files included in an archive with the binary.

##### Lesson

When publishing releases:

- Don't use unique filenames for each release.
  While this can be useful for users, it complicates automation efforts.
- If the filename is going to include an identifier,
  use an identifier that is easily machine obtainable.
- Don't bundle unnecessary files with the release.

### What Now?

Well - I wrote this post, that's a start.
I plan to write about my current homelab setup next,
followed by documenting its upcoming migration.

That's all I have for now, but I'm excited to share more posts in the future -
so stay tuned, and I hope you enjoyed my first post!
