---
title: vim
---

# vim
A personal voyage

---

# The primary thesis of this talk

You should care deeply about the editor you use, but you should not let anyone
tell you which editor to use.

---

# Why should you care which editor you use?

<v-clicks>

- It's a big cognitive investment
  - Features
  - Key bindings
  - Configuration
  - Customization
- With potentially huge returns
  - Muscle memory
  - Automation
  - Productivity
  - Reduced cognitive load
- For some of us, switching to a new editor can feel like learning a new
  language.
  - We're less productive for days or weeks as we adjust to the new ways of
    doing things.

</v-clicks>

<!--
As a software developer, your editor is the tool in which you spend the most
time.  How you work with your editor has a huge impact on your productivity.
Working with an editor that clashes with your mental model of how text is
edited won't just make it hard to edit text, it will make it hard to _think_,
because you are devoting so much cognition to struggling with your editor.
-->

---

# Why do so many people have such strong opinions about which editor is best?

<v-click>

Your experience of using an editor is _subjective_.  It depends on your
aesthetic sensibilities, your subconscious mental model of how text is mutated,
and, for most people in 2025, what you're used to.

</v-click>

<!--

I don't have any science to back up this claim, but my experience has taught me
that different developers experience their editors differently.  They end up
with a strong preference for the editor that works best with their cognitive
style.

As with so many other things, when we encounter someone who experiences our
favorite editor differently than we do, we're surprised and confused.  We tend
to want to convince them to see the world the way we do.  This rarely ends
well.

In this talk, my goal is not to make you see the world the way I do.  It's to
share with you how I experience my editor, and why I have consistently found vi
and vi-adjacent editors to be the best experience for me for the last 35 years.

If, as a result if this talk, you try vim and hate it, _that is ok_.  You've
got different aesthetic preferences than I do, or you've got a different way of
thinking about text mutation than I do, or you're just really used to a
different style of editing than I am.  All of those are fine.

-->

---
layout: image-left
image: assets/scotts-signal.png
---

# Hi. I'm Scott.

- I'm on a break from the tech industry after almost 30 years.
- I started programming as a hobbyist in the mid-1970s.
- I became a "professional" in the mid-1990s.
- I learned the basics of vi in my first programming lab session at CU, Boulder
  in a long afternoon in 1990.  vi has been my editor of choice ever since.
- I made this entire presentation in Neovim.

<!--

I refer to myself as "maybe retired and definitely grumpy."  My programming
journey started on a HP-67 programmable calculator my Dad brought home from his
job at IBM in the mid-1970s.  In my first programming course at CU Boulder, the
TA gave us a choice between learning an "easy" editor and learning a "powerful"
editor.  The "powerful" editor was vi.  I chose power.  That made for a very
long afternoon as I tried to write one of my first C programs while also trying
to understand how to manipulate text with vi.  By the end of that afternoon,
though, I was conversant with vi basics.  I have been using it ever since.

-->

---

# vim History

- ed -> ex -> vi -> vim
- Teletype constraints enforced efficiency

---

# Hard dependencies should be free

- Your editor is your sword
- Prior bad outcomes
    - Textmate
    - VS Code
    - Cursor

---

# vim reduces friction

between you and your code

- QWERTY home row
- modal
- motions

---

# vim is powerful

- Very powerful search and replace
- Fast means of making large edits to code and documents
- This entire presentation was made in vim!

---

# vim and neovim

- vim development was guided by Bram Moolenaar
- neovim forked in 2014 with an initial focus on code modernization and
  expanded scope of contribution
  - Added Lua scripting
  - Added built-in LSP client
- If you are getting started today, it is probably best to start with neovim,
  as the availability of Lua scripting has led to an explosion of plugin
  development
  - For this talk, we will install and use vim, as it is easier and faster to
    get to the tutorial on a variety of platforms

---

# vim is hard to install

---

# vim can be hard to learn

- Users are expected to go out and find features rather than having features
  surfaced for them
  - This, though, is what allows vim to be very clean, focused, and fast in the
    hands of an experienced user
  - Case in point, vim has an excellent help system and tutorial, but you need
    to know they are there and how to invoke them.

---

# Resources

- [TJ Devries Advent of
  Neovim](https://www.youtube.com/watch?v=TQn2hJeHQbM&list=PLep05UYkc6wTyBe7kPjQFWVXTlhKeQejM)
- [Typecraft Neovim from
  Scratch](https://www.youtube.com/playlist?list=PLsz00TDipIffxsNXSkskknolKShdbcALR)

---

# Let's install vim!

