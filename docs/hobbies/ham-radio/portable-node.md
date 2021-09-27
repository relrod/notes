# Portable AllStarLink Node

This page documents the build and operation of a portable AllStarLink node
designed by me (AI5A) originally for the Oak Hill Amateur Radio Club (N5OAK) to
use at the Belton HamExpo hamfest in 2021.

## The Idea

The idea went through several iterations and started with Kyle/KA5D suggesting
that somebody bring a portable repeater to the hamfest. Having been getting into
AllStarlink, I offered to work on it, if someone could provide the duplexer for
it.

Shortly after, Sean/W5SMS proposed that a simplex node would probably suffice,
with the goal of linking it back to the
[N5OAK repeater network](https://n5oak.org/repeaters), and allowing it to be
used, in particular, for the
[Friday night trivia net](https://wz5bbs.com/trivia/). This idea appealed to
me. I already set up one simplex node (the 900MHz node at my apartment), and it
went well. I already had plans to set up more and turn them into repeaters. So
this seemed like a good project.

So I volunteered. I took the project and ran with it.

## The Construction

I had a few things at my disposal already:

* A radio (Motorola PM400) that I wasn't using for anything and which had a port
  on the back that would work fine for interfacing.
* Interface boards (ordered from
  [Techno By George, LLC](https://technobygeorge.com/)) for experimenting.
* Two metal 10 1/4" x 9 1/2" x 2 1/2" enclosures, one of which I was willing to
  dedicate to the project.
* Familiarity with the configuration and administration of AllStarLink from my
  previous node.

That meant I needed, at minimum:

* A computer to dedicate to it - originally I considered using a laptop, but I
  wanted something that would fit in the enclosure, so I with with a Raspberry
  Pi (3B+) instead.
* A solution for power, including powering the Pi.
* A solution for heat.
* A solution for RF (antenna connection).
* A solution for getting the thing online, not knowing how WiFi would be at the
  hamfest.

I ordered the Raspberry Pi from Vilros. It got delayed (USPS) but ended up
showing up on time anyway. Phew.

For power, I realized that the radio (even on high power, which I'm not planning
to use) only drew 9A according to the specification sheet. The Pi won't draw too
much because it's not going to be under much load. And the fans will hardly draw
anything at all. So, I decided to get a
[12.5A switching power supply](https://www.amazon.com/gp/product/B08CZKJCZ6)
from Amazon, snip the end off, and terminate it with an Anderson Power Pole
connector. The power problem was mostly solved. I still needed a way to power
the Pi, so I bought a
[USBbuddy](https://powerwerx.com/usbbuddy-powerpole-usb-converter-device-charger)
from Powerwerx, along with a
[PD-4](https://powerwerx.com/4-position-powerpole-distribution-block) to
distribute power to the various devices. I ran a short Power Pole pigtail out of
the enclosure through one of the punch-outs and into the PD-4, and lo and
behold, I had power. The power supply is kept outside of the enclosure (and is
optional - if 12vdc power exists nearby, it can be used instead directly into
the enclosure, otherwise the switching supply can be used from 110vac).

The problem of heat is something a bit harder to deal with and that I am still
keeping an eye on. The radio I'm using (PM400) has its heat sink on the bottom,
not on the back. So it is hard to cool with a fan. In any case, I bought a few
[Noctua fans](https://www.amazon.com/gp/product/B072JK9GX6) having had good luck
with them in the past. They're nice and quiet. I have one blowing toward the
back of the radio, and one blowing out the side of the enclosure (blowing out
another punch-out hole). So far, nothing has overheated to the point of
failing.

Attaching an antenna to the node is done by way of a
[panel mount SO239 coupler](https://www.amazon.com/gp/product/B014MCCYM8), whose
connector goes through one of the punch-outs in the enclosure, and whose base is
screwed into the enclosure with two small drill holes and screws. The radio
expects a Mini UHF connector, and the easiest (and shortest) way to get there
was [PL259 to SMA](https://www.amazon.com/gp/product/B00COWFD6I/), then
[SMA to Mini UHF](https://www.amazon.com/gp/product/B014KQ1B0W). There might be
a better way, but this seemed to work well enough and let me use a small (6")
jumper easily (the PL259 to SMA).

Getting the thing online was another challenge, and took some research for the
cheapest, no-contract 4G option I could find. I ended up going with
Straight Talk's prepaid
[hotspot plan](https://www.straighttalk.com/plans/hotspots). They offered a
refurbished hotspot device for free when you first sign up, so for $15, I was
set with 2GB of 4G data. This is not a promotional post for Straight Talk, and I
have no idea how well it will do, but it's what I went with.

Getting everything mounted in the case was a bit of a Tetris-like puzzle, but
with some diligence, I was able to make things fit. Things are mounted in with
3M Command Strips, which in theory should be strong enough to hold things up
with the enclosure being vertical or horizontal. In my testing, I've kept it
horizontal.

The Pi was configured using Ansible. I will be publishing my AllStarLink Ansible
configuration in the near future as open source. This made it trivial to get the
node up and working, I had to do very little configuration myself. (I later went
back and tweaked things to make it slightly nicer to use, like shorter tails and
courtesy tones, and some custom scripting to make it announce the PL
occasionally (as a reminder to people who don't have it set).

Some later additions included a status script that I wrote which will make it
ping the 4G hotspot to request service level and battery level and say them over
the air. A temperature sensor was added under the radio to report the heat sink
temperature along with the Pi CPU temperature at the touch of a DTMF code. I
also subscribed to [tailscale VPN](https://tailscale.com/) and joined the Pi to
the hosted VPN, to give myself a way to backdoor into it if needed. I can
connect to it and SSH into it from any other device on the VPN such as a phone
or laptop. So far it's worked well, and I've been really happy with the service
in my few days of testing. Another late addition was that of a DTMF matrix
keypad and some custom code to take input from it and sent it allong to
AllStarLink/asterisk.

![Construction 1](/images/portable-1.jpg){align=left width=48%}
![Construction 2](/images/portable-2.jpg){align=right width=45%}

<!-- ugh -->
<div style="clear: both"></div>
<!-- /ugh -->

## Final-ish Product

Minor tweaks have taken place since this shot was taken, but it shows the mostly
finished product.

![Final-ish product](/images/portable-3.jpg)

## Future Plans

* The wiring needs to be a bit cleaner - mostly by making the wires be shorter
  than they are instead of coiling them up. This is a future enhancement.

* Working out a better solution to the heating problem is another enhancement,
  but will require much experimentation. The heat sink being on the bottom of
  the radio makes it a hard problem to solve.

* More fancy scripting ideas. Anything goes here - stuff useful to portable
  operations. Weather alerts?
