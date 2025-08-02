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
  language
  - We're less productive for days or weeks as we adjust to the new ways of
    doing things

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
- I learned the basics of vi in my first programming lab session at CU,
  Boulder.
  in a long afternoon in 1990.  vi has been my editor of choice ever since.
- I made this entire presentation in Neovim.
- I am of a deeply divided mind about how to use periods in bullet lists

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

# Historical resources

- [1984 interview with Bill
  Joy](http://xahlee.info/comp/interview_with_bill_joy.html)
- [Bram Moolenaar's history of vim](https://www.moolenaar.net/vimstory.txt)
- [STEVIE by Tim Thompson](https://timthompson.com/tjt/stevie/)

---

# What is vim and what makes it good?

vim started its life as "vi-imitation."
Soon after, it was renamed to "vi-improved."

<!--

I'll now explain what vim is, where it came from, and why it might be worthy of
your consideration.

-->

---

# Great.  What's vi?

vi started its life as the "VIsual" mode for the ex editor on early versions of
UNIX before becoming an editor unto itself.

---

# Ok.  What's ex and what is a visual mode for ex?

---
layout: image-left
image: assets/Teletype-IMG_7287.jpg
backgroundSize: contain
---

Image credit:  [Wikimedia
Foundation](https://en.wikipedia.org/wiki/Teletype_Model_33)

<!--

Some early computers used teletypes as their user interface devices.  All input
and output was printed on paper.  Thus, interactions were linear.  Random
"cursor" repositioning was not possible.

This meant that early software developers had to interact with text via
indirect commands.  They would specify the mutations they wanted, and the lines
in the text file to which those mutations should apply.  Hence the term "line
editor."

Bill Joy and his contemporaries weren't using teletypes.

-->

---
layout: image-right
image:  assets/ADM_3A_(82481457).jpg
backgroundSize: contain
---

Image credit:  [Wikimedia
Foundation](https://en.wikipedia.org/wiki/File:ADM_3A_(82481457).jpg)

> I'm used to having a 24-line terminal with no ability to scroll back.

Bill Joy, 1984

<!--

Bill Joy and his contemporaries were using what were then referred to as "glass
teletypes."  These were CRT screens that had very limited capabilities.
Physically, they were monitors as we think of them today.  But the ability to
use the monitors in ways we take for granted were still being developed.

Thus, ex, and the editors upon which it was based, functioned very similarly to
as if they were on a teletype.

Users needed to _describe_ the mutations they wanted to make to text without
visually moving and changing text elements.  This constraint led to the
development of concise, terse, indirect means of describing text mutations.

-->

---

# ex demonstration

<v-clicks>

- The constraints of early hardware forced the creation of a concise language
  for manipulating text.
- The "VIsual mode" for ex combined that language with the ability to visually
  manipulate text.
- Switching "modes" between visual manipulation and descriptive manipulation
  led to expressive power that many software developers find productive.

</v-clicks>

<!--

- From the Earth to the Moon sample text
- Display the entire text
- Display a section of lines
- Find lines with "cannon"
- Display a set of lines surrounding a line containing "cannon"
- Replace "cannon" with "burrito" in that set of lines
- Append the line now containing "burrito" to its enclosing paragraph
- Delete the appended line
- Append a line to the enclosing "burrito" paragraph, typed directly
- Delete the appended line
- Replace "cannon" with "burrito" in the entire text
- Save the modified file
- Show a diff

-->

---

# In 1984, what did Bill Joy think of his creation?

> I think one of the interesting things is that vi is really a mode-based
> editor. I think as mode-based editors go, it pretty good. One of the good
> things about EMACS, though, is its programmability and the modelessness.

> The fundamental problem with vi is that it doesn't have a mouse and therefore
> you've got all these commands.

> I had almost rewritten all of the display code for windows, and that was when
> I gave up.

> I think multiple levels of undo would be wonderful, too. But fundamentally,
> vi is still ed inside. You can't really fool it.

> This business of using the same editor for 10 years - it's like living in the
> same place for 10 years. None of us does it. Everyone moves once a year,
> right?

<!--

GUIs and mice were new when Joy made these comments.  In the decades since,
some of us have come to recognize the advantages of avoiding taking our hands
off the keyboard, and of using terse, quick-to-type commands.  Meanwhile vim
has added support for extensibility, multiple windows, and multi-level undo.

-->

---

# I'll ask one more time.  What is vim?

- Throughout the 1980s, students had to learn vi, as their university's
  computer science department used BSD UNIX.  Many of those students took a
  liking to vi.
- One such student was probably Tim Thompson.
  - Tim got an Atari ST and wanted to use vi on it.  He created
    [STEVIE](https://timthompson.com/tjt/stevie/), a vi clone for the Atari ST.
- Another was Bram Moolenaar.
  - Bram got a Commodore Amiga on which he wanted to use vi.  He found STEVIE's
    code, improved it, and called it "vim," first for "vi-imitator," and then
    for "vi-improved."
    - Added vimscript, enabling extensibility
    - Added support for multiple windows and panes
    - Added a GUI, including mouse support
    - Added multi-level undo
- The vi source code was not yet open.  When early Linux distributions needed a
  vi, most of them chose vim, as it was the most capable.

<!--

In vim, Bram added everything that Bill Joy claims to have regretted leaving
out of vi.  Meanwhile, the source code was open, where vi's source code was
embroiled in a dispute between the University of California, Berkeley, and
AT&T.  Early Linux distributions needed a vi to mimic commercial UNIX.  They
found and standardized on vim.

-->

---

# What is Neovim?

Neovim is a community fork of vim.  Its goals are to

- Make it easier for many people to contribute
- Separate UI code from core editing code
- Improve extensibility

---

# What is Neovim?

In 2021, the 0.5.0 release of Neovim added two major capabilities.

- Built-in Language Server Protocol support
- Built-in support for Lua as a configuration and plugin authoring language.

<!--

LSP support allows Neovim to benefit from the work done on language support for
Visual Studio Code.

Lua support allows anyone who knows how to create scripts for a wide variety of
games, including Roblox, to author plugins for Neovim.  Lua support has led to
a Cambrian Explosion of development for Neovim.

-->

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

