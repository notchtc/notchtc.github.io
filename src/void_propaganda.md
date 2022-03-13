# Void Linux propaganda

# WARNING! This is a work in progress

## table of contents
1. [Introduction](#introduction)
1. [The install process](#the%20install%20process)
1. [xbps-src](#xbps-src)
1. [xtools](#xtools)
1. [Neat Void only software](#neat%20void%20only%20software)
1. [Other people's opinions](#other%20people&#8217;s%20opinions)
    1. [Websites](#websites)
    1. [Copypasta](#copypasta)

## introduction
[Void Linux](https://voidlinux.org) is a rolling release Linux distribution focused on stability.

It isn't based on another distro (like Arch for example), it uses it's own package manager, [XBPS](https://github.com/void-linux/xbps) (X Binary Package System), the [runit](http://smarden.org/runit/) init system (which was [modified a little bit](https://github.com/void-linux/runit)) and supports both [glibc](https://www.gnu.org/software/libc/) and [musl](http://musl.libc.org/).

I recommend using the [Void Handbook](https://docs.voidlinux.org/) for Void related stuff, it will probably help you and if it doesn't well then you could ask for help on the [#voidlinux IRC channel](ircs://irc.libera.chat/#voidlinux) on [libera.chat](https://libera.chat) or on the [subreddit](https://www.reddit.com/r/voidlinux/).

If you want to look at the source code of Void related things then take a look at their [GitHub](https://github.com/void-linux) account.

They also have a [Twitter](https://twitter.com/voidlinux) account which you could follow for news <span style="display: none;">(and a BLM tweet once in a century) </span>or you could just use their [website](https://voidlinux.org/news/) ([rss feed](https://voidlinux.org/atom.xml)).

## the install process
[Installing Void](https://docs.voidlinux.org/installation/live-images/guide.html) is pretty simple (there are some exceptions that I'm gonna talk about later).

You download a live image, create a bootable media of your choice, then once you are inside the live image, you login and just go through the installer, easy as that. The scariest thing in the install process is probably partitioning your disks but even that isn't crazy.

Now for a few things you need to [install Void via chroot](https://docs.voidlinux.org/installation/guides/chroot.html):

- [Full Disk Encryption](https://docs.voidlinux.org/installation/guides/fde.html)
- [Installing Void on a ZFS Root](https://docs.voidlinux.org/installation/guides/zfs.html)
- [ARM Devices](https://docs.voidlinux.org/installation/guides/arm-devices/index.html)

## xbps-src
If something **really** isn't in the repos, I suggest you first check if it's in the [Void packages git repository](https://github.com/void-linux/void-packages) (for example something like Discord).

Or maybe you want to change a compile flag or maybe apply a patch, but program Y depends on program X and you don't want to remove the files of the version from the repos everytime.

Well, xbps-src and xbps-pkgdb will help you with that. You want to change a compile flag? Edit the template of the package in srcpkgs. Want to apply a patch? Slap that bad boy into a patches directory inside the package directory. And then you run something ``xbps-pkgdb -m repolock <package>`` on that and voila.

I'm not gonna write a xbps-src tutorial here, all the info you need is in the [Void packages repo](https://github.com/void-linux/void-packages) but I'm gonna tell you one thing, when cloning the repository use:

```
git clone --depth 1 https://github.com/void-linux/void-packages
```

because when you don't, you will be waiting longer and more of your precious space will be taken.

## xtools
Maybe you are tired of adding --repository every time you are installing something from xbps-src. Now instead of just making an alias I recommend installing [xtools](https://git.vuxu.org/xtools/about/) and using the xi command.

Why? Because xtools has some cool stuff which can help you with xbps-src related stuff but also other commands that will help you with everyday life.

For example xlocate will locate files in all XBPS packages, xnew will create a xbps-src template for you and the list goes on.

## neat void only software
This is a list of some nice Void only software that could come in handy.

I personally don't use any of them except for xdeb (which I don't even use often).

I have already mentioned xtools and xbps-src.

- [vpm](https://github.com/netzverweigerer/vpm) - An XBPS package management helper for VoidLinux
- [vpnd](https://gitlab.com/emacsomancer/vpnd) - Notifications about Void Linux package updates, via systray icon or pop-up notifications
- [vsv](https://github.com/bahamas10/vsv) - Manage and view runit services
- [xdeb](https://github.com/toluschr/xdeb) - Convert Debian packages to Void Linux ones ([be careful with this one](https://www.reddit.com/r/voidlinux/comments/tbd7xp/please_stop_using_xdeb_use_flatpak_instead/))

---

# other people's opinions
Here are some things in text form that I found about Void Linux.

## websites
WARNING! Very creative names incoming.

- [Why Void Linux?](http://www.troubleshooters.com/linux/void/whyvoid.htm) (Steve Litt)
- [Why Void?](https://sm-idk.me/why_void/) (smn)

## copypasta
I don't know where these came from, I don't know who wrote these and I don't know if they are serious.

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
