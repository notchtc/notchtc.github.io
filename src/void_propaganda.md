# Void Linux propaganda
Before/after reading this check out what [other people said](#other-peoples-opinions) about Void.

## Table of Contents
1. [Introduction](#introduction)
1. [The install process](#the-install-process)
1. [xbps-src](#xbps-src)
1. [xtools](#xtools)
1. [Creating your own ISO](#creating-your-own-iso)
1. [Neat Void only software](#neat-void-only-software)
1. [Other people's opinions](#other-peoples-opinions)
    1. [Websites](#websites)
    1. [Copypasta](#copypasta)

## Introduction
[Void Linux](https://voidlinux.org) is a rolling release Linux distribution focused on stability.

It isn't based on another distro (like Arch for example), it uses it's own package manager, [XBPS](https://github.com/void-linux/xbps) (X Binary Package System), the [runit](http://smarden.org/runit/) init system (which was [modified a little bit](https://github.com/void-linux/runit)) and supports both [glibc](https://www.gnu.org/software/libc/) and [musl](http://musl.libc.org/).

I recommend using the [Void Handbook](https://docs.voidlinux.org/) for Void related stuff, it will probably help you and if it doesn't well then you could ask for help on the [#voidlinux IRC channel](ircs://irc.libera.chat/#voidlinux) on [libera.chat](https://libera.chat) or on the [subreddit](https://www.reddit.com/r/voidlinux/).

If you want to look at the source code of Void related things then take a look at their [GitHub](https://github.com/void-linux) account.

They also have a [Twitter](https://twitter.com/voidlinux) account which you could follow for news <span style="display: none;">(and a BLM tweet once in a century) </span>or you could just use their [website](https://voidlinux.org/news/) ([rss feed](https://voidlinux.org/atom.xml)).


## The install process
[Installing Void](https://docs.voidlinux.org/installation/live-images/guide.html) is pretty simple (there are some exceptions that I'm gonna talk about later).

You download a live image, create a bootable media of your choice, then once you are inside the live image, you login and just go through the installer, easy as that. The scariest thing in the install process is probably partitioning your disks but even that isn't crazy.

Now for a few things you need to [install Void via chroot](https://docs.voidlinux.org/installation/guides/chroot.html):

- [Full Disk Encryption](https://docs.voidlinux.org/installation/guides/fde.html)
- [Installing Void on a ZFS Root](https://docs.voidlinux.org/installation/guides/zfs.html)
- [ARM Devices](https://docs.voidlinux.org/installation/guides/arm-devices/index.html)

## xbps-src
If something **really** isn't in the repos, I suggest you first check if it's in the [Void packages git repository](https://github.com/void-linux/void-packages) (for example something like Discord).

Why? Because it has a thing called xbps-src and some packages that don't have binaries in the repos.

I'm not gonna write a xbps-src tutorial here, all the info you need is in the [Void packages repo](https://github.com/void-linux/void-packages) but I'm gonna tell you one thing, when cloning the repository use:

```
git clone --depth 1 https://github.com/void-linux/void-packages
```

because when you don't, you will be waiting longer and more of your precious space will be taken.

You can also use xbps-src to change a compile flag or to apply a patch without having to remove the files of the version from the repo because some other package depends on the one you are changing. You just need to run ``xbps-pkgdb -m repolock <package name>`` so it doesn't replace the package on update.

Want something in the repos? Well you could ask for someone to create a package for it *or* you could create it yourself and submit a pull request to the Void packages repo. (You will also need to pray and hope that it gets accepted)

Or maybe some package is outdated, you can also update it and submit a pull request. Sometimes it will be as easy as just changing the version and checksum but sometimes you will maybe need to change some other stuff in the template. It's amazing that literally everyone can contribute to the Void repos that easily!

Other people have their own git repositories with xbps-src template for various package, here are a few that I found on the internet:

- [sug0/voided-packages](https://github.com/sug0/voided-packages)
- [aisamanra/void-extra-packages](https://github.com/aisamanra/void-extra-packages)
- [faenrir/void-extras](https://github.com/faenrir/void-extras)

You can also check out my own [Void packages repo](https://github.com/notchtc/custom-void-packages). I doubt the templates are of the highest quality but I got some nice stuff in there. And also I'm a lazy asshole and don't bother with doing a PR to the repo.

## xtools
Maybe you are tired of adding `--repository` every time you are installing something from xbps-src. Now instead of just making an alias I recommend installing [xtools](https://git.vuxu.org/xtools/about/) and using the xi command.

Why? Because xtools has some cool stuff which can help you with xbps-src related stuff but also other commands that will help you with everyday life.

For example:

- xlocate - Locates files in all XBPS packages
- xnew - Creates a xbps-src template
- xcheckmypkgs - Checks if your xbps-src packages are up to date

The xi, xls, xq and xrs will use the hostdir/binpkgs repo if you run them from a void-packages checkout.

- xi - Installs packages
- xls - Lists files contained in package
- xq - Queries information about XBPS package
- xrs - Will search for stuff in the Void repo

## Creating your own ISO
Now this isn't anything new or special, like archiso (for Arch, obviously) exists but I'm gonna mention it anyway.

You can create custom Void Linux ISOs with [void-mklive](https://github.com/void-linux/void-mklive), you can add packages to it, add files to it, change some stuff like the keymap and locale, maybe you want to create a very minimal ISO and use base-minimal instead of base-system.

Probably everything you need is in these scripts. And you can always edit them if you need something more to be done (sadly I don't know how much knowledge you need).

I recommend using the build-x86-images.sh script so the live image works like it should, oh and you can also build Void ISOs for some other DE's like MATE, GNOME and KDE etc if you need that (as of writing Void only has the XFCE ISO). Or you could plop down those packages into your package list in mklive.sh, the choice is yours.

There is a site that provides [custom Void ISOs](https://voidbuilds.xyz) with these DEs and more (there is even an i3 ISO) with also some additional packages.

I actually create [my own ISO](https://github.com/notchtc/voidlinux-iso-extra) (based on [this repository](https://github.com/kotoko/voidlinux-iso-extra)) with GitHub actions, it basically has the packages I use, my dotfiles and some system settings.

## Neat Void only software
This is a list of some nice Void only software that could come in handy.

I personally don't use any of them except for xdeb (which I don't even use often).

I have already mentioned xtools and xbps-src.

- [vpm](https://github.com/netzverweigerer/vpm) - An XBPS package management helper for VoidLinux
- [vpnd](https://gitlab.com/emacsomancer/vpnd) - Notifications about Void Linux package updates, via systray icon or pop-up notifications
- [vsv](https://github.com/bahamas10/vsv) - Manage and view runit services
- [xdeb](https://github.com/toluschr/xdeb) - Convert Debian packages to Void Linux ones ([be careful with this one](https://www.reddit.com/r/voidlinux/comments/tbd7xp/please_stop_using_xdeb_use_flatpak_instead/))

---

# Other people's opinions
Here are some things in text form that I found about Void Linux.

## Websites

- [Why Void Linux?](http://www.troubleshooters.com/linux/void/whyvoid.htm) (Steve Litt)
- [Void Linux](https://sm-idk.me/s/void.html) (smn)

## Copypasta
I don't know where these came from, I don't know who wrote these and I don't know if they are serious.

---

Is Void Linux based? Yes. Void Linux is based.
No, really. Super based. Omega based.

Void Linux was built in such a way that it’s basically one of the most feature complete Linux distros that we’ve seen in recent times.

The developers of Void Linux are always listening to the community and make sure that their distro is up to the task of providing the best possible experience for everyone. That is the philosophy behind Void Linux and it is the main reason why it’s so popular.

Even though the software center isn’t as good as in the past or as featured in newer distributions, Void Linux is still a very good distro that I would recommend to anyone looking for a new distro.

After using Void Linux for a while, I found that it wasn’t really something that I would just use to replace my current distro. But I think that it has plenty of value for those looking for a new distro or for those who are interested in playing with a different flavor of Linux.

Void Linux is available for a wide variety of different architectures and, because it’s not based on anything, it works on all kinds of different hardware.

Even though it’s a Linux distro, I think that it’s something that works great on the Mac.

The developers and supporters of Void Linux are super friendly and the distro works great on pretty much any hardware out there.

I’ve heard from a lot of people who use it and absolutely love it.
And they are usually pretty big Linux users so they know what they are talking about.
I’ve also talked to some people who use Void Linux and can’t stand it.
I think that’s pretty normal. Not everyone will like the distro.

---

I used to be a distrohopper until I landed on Void.

Ngl, I thought that it was a shitty minimalist meme distro at first, but good lord it's really fucking good.

XBPS is a lot better than Pacman (what I used to use before) and runit is fast as fuck.

Moreover, I can get 99% of the packages I need from xbepis, and also compile them from source if I want to.

I love Void, I hope it lives a long and prosperous life; I'll be there with it throughout.
