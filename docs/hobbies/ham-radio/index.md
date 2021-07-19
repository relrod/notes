# Ham Radio (N8SQL)

I operate out of Austin, TX, typically on 40m up through 33cm (excluding 1.25m,
currently). You can sometimes find me on local repeaters if you're in the area,
or on HF (lately, FT8).

Feel free to email me at: me@[my callsign].me and I'll respond as able.

73!


## The N8SQL Antenna Farm

Due to living in an apartment, I operate with some compromise
antennas. I have a Comet CTC-50 window feed-thru jumper to run
connections in through the sliding balcony door. Switching antennas is
currently a manual process - going out on the balcony and connecting
the antenna for the band I want to operate. I plan to fix this in the
future with a remote antenna switch, but it's not a huge priority.

My view of the world mostly runs NE and SW, at least from the back
balcony. NW is blocked by an adjacent apartment building directly
across from my balcony, and SE is blocked by my own apartment
building, although I have a front balcony and could (and might in the
future) put something directional out there. Currently all of my
antennas are on the back balcony.

My current setup is as follows (from low to high frequency):

* **40m** - For 40m, I have a custom-made dipole that is zip-tied to
  the railing posts of my balcony, in a square-wave pattern. That is,
  the antenna goes up one post, over, down the next, over, up the
  next, etc. This covers most of the length of the antenna, but there
  is some wire left on both sides, which currently just rests on the
  balcony floor. The antenna terminates to a homebrew 1:1 balun. This
  setup works "okay" and the SWR is locked down, but the antenna is
  unfortunately not very efficient. It can get me on 40m in a pinch,
  but I think the square-wave pattern limits the effectiveness of the
  antenna.

* **10m - 30m** - For the higher HF bands up through 10m, I use an
  MFJ-1782 mag loop. Although mag loops are typically considered
  compromise antennas, I've actually been very happy with the
  results. I obtained WAS and CQ WPX with the antenna and work DX
  regularly on FT8 with no issues. The Comet jumper mentioned above
  functions just fine with the loop controller. The antenna is mounted
  on a Wiregard DS-2000 22" mast, which itself is mounted to the top
  of my balcony railing with two large C-clamps, to avoid drilling
  into the wood of the balcony. (The antenna is also rope-tied to the
  balcony as a safe-guard in case the C-clamps fail for any reason).

* **6m (dipole)** - I have two antennas for 6m, the first is a small
  wire dipole which rests along the top of my balcony railing and
  terminates to a balun.

* **6m (stressed moxon)** (NOTE: I ordered this but don't actually
  have it in hand yet) The second, and newer, antenna I have for 6m
  is a stressed moxon (SM-50) from PAR Electronics. This antenna is
  mounted above the 10m - 30m mag loop, on the same Wiregard mast.

* **2m/70cm (vertical)** - This is provided by a Diamond X30A vertical
  which lives on the back balcony with the other antennas. It might
  some day move to the front balcony, to offer some separation from
  the HF antennas, as the two can interfere (talking on HF causes
  noise on 2m, for example). I also have a DPD Productions 2 meter
  blade antenna which lives indoors but rarely sees any use.

* **2m (horizontal)** - Additionally, I have a GRA-YG1443 2m/70cm
  square dipole, but it is not currently in use.

* **33cm** - For 900MHz, I have a small magmount which is currently indoors and
  works well enough to hit the two distinct 900MHz repeater systems in the area
  (K5TRA and KA5D).

## The N8SQL Shack

* **Audio** - This is currently a work in progress, but the plan is to use a
  Soundcraft Ui12 digital mixer that I had laying around. All of the radios will
  feed into it, and it will be controllable via any device on the network (such
  as my desktop, or a tablet on the desk showing the mixer console for quick
  access).

* **HF/6m** - Until recently, this was done with an IC-706mkii. However, it was
  recently replaced with an IC-7300. The IC-7300 feeds to a Daiwa CN-801
  power/SWR meter, when then feeds to the loop controller for the MFJ mag loop.
  The loop controller is left in-line constantly, as it seems to be passive if
  connected to a different antenna, so long as the tuning buttons aren't
  pressed. The loop controller output then runs along my apartment's main
  hallway (using
  [Legrand Wiremold covers](https://www.amazon.com/gp/product/B0015EDVVU/) to
  hide them) into the Comet CTC-50 which feeds through the door to the balcony.
  All patch cables (radio-meter, meter-controller) are RG400. They are wrapped
  around #31 ferrite cores as are most of the other cables and wires that are
  anywhere near the radios.

* **2m/70cm** - This is currently provided by a Kenwood TM-V71a. It works fairly
  well, but my setup has a bit of a "hiss" on some of the repeaters in the area,
  that I wish it didn't. Moving the antenna to the other balcony might fix
  this.

* **33cm** - 900MHz is provided by a Kenwood TK-941, which has some of the
  quietest, best sounding receive audio I've ever heard.
