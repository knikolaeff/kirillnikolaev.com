---
title: "My Linux setup"
date: 2025-01-15T14:26:31Z
categories: [ "Linux" ]
---
There comes a time in every man's life when he just has to talk about his Linux setup on the internet.

![](media/linux-screenshot.jpg)
*My desktop, neovim with this particular post and neofetch*

### Why Arch?

I use Arch Linux because I tend to follow the principle "install it, if you need it", not "delete it, if you don't need it". Although Arch can be a pain, I love it's minimalistic philosophy and hackability. 

Moreover, Arch taught me a lot about Linux it's oddities. ArchWiki is probably the most comprehensive database of a Linux knowledge.

AUR is also forever in my heart. Just try it and you will know what I mean.

### Software

- [Kitty](https://sw.kovidgoyal.net/kitty/) is my terminal emulator. It just works. Kitty is fast, easily customazable and never let me down
- I use KDE as my DM. This is my final stop after months (if not years) of distrohopping. Yes, it might not be as "cool", as tiling managers or other niche DM/WM, but it lets me do the job and do it quickly
- Most of the text/code editing is done in Vim/Neovim. It has quite a learning curve, but once you get used to it - muscle memory will kick in even in other editors like VS Code. It comes pre-installed on almost every server, so I can edit configs or apply hotfixes through SSH blazingly fast
- tmux is another tool I run daily to speed up daily tasks. I tend to use SSH **a lot** and there is nothing more frustrating than losing connection in the middle of compilation/upgrade/other long proccess

### Dotfiles

I manage my dotfiles using [yadm](https://yadm.io/). It's dead simple, as dotfiles management should be. You can find them here: https://github.com/knikolaeff/dotfiles
