---
title: "Markdown Cheatsheet"
date: 2023-10-28T12:00:00-07:00
draft: false
---

This post demonstrates all the awesome Markdown features supported by this Hugo site.

## Text and Links

This paragraph contains **bold text**, _italic text_, ~~strikethrough text~~, and `inline code`. You can also include [internal links](/posts/my-first-post/) and [external links to Google](https://google.com), which get a special icon.

## Blockquote

> To be, or not to be, that is the question: Whether 'tis nobler in the mind to suffer the slings and arrows of outrageous fortune, Or to take arms against a sea of troubles.

## Lists

Here are some lists.

- Unordered Item 1
- Unordered Item 2
    - A nested item.

1.  Ordered Item 1
2.  Ordered Item 2

And a cool task list:

- [x] Learn Hugo basics.
- [x] Style the theme toggle.
- [ ] Write my next great blog post.

---

## Images and Code

You can add an image like this (assuming you have one at `/images/placeholder.jpg`):

![A placeholder image](/images/placeholder.jpg "This is a placeholder")

And here is a block of `python` code with syntax highlighting:

```python
def greet(name):
  """This function greets the person passed in as a parameter."""
  print(f"Hello, {name}! Welcome to the world of Markdown.")

greet("Developer")
```
