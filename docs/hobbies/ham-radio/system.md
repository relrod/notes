# The AI5A System

The AI5A System currently consists of a 900MHz simplex AllStarLink node located
and accessible within EM10cf (though coverage extends up North a fair bit). The
goal of the system for now is coverage for the South Central Austin area
(Galindo, Dawson, Zilker, Bouldin Creek, South Lamar, SoCo, etc.).

The system is planned to extend to become a 900MHz repeater alongside a UHF
simplex node in the future, and possibly with more remote repeaters in the
future.

The system is open for all to use!

## Affiliations and Links

The system links up to some other local repeater systems for weekly nets.
The 900MHz system (currently the only piece of the system) also links to the
927-Tech/K5TRA system every evening at 21:30 *except* when a net conflicts per
below.

The system is currently set up with the following schedule:

| Day | Time | Link | Comments |
| --- | ---- | ---- | -------- |
| W | 19:55 - 21:15 | KA5D System | UT ARC weekly net |
| Th | 19:55 - 23:00 | N5OAK System | Oak Hill ARC weekly net |
| F | 20:45 - 00:00 | N5OAK System | Oak Hill ARC weekly trivia net |
| Su, M, Tu, W, Sa | 21:30 - ?? | 927-Tech/K5TRA | (900 only) Nightly roundtable |

## Software Configuration

The system is using AllStarLink as a controller. The AllStarLink configuration
is templated extensively with the use of Ansible. I plan to open-source the
Ansible roles and configuration in the very near future. Adding a new node to
the system with a configuration that is the same as the other nodes is as simple
as editing one file to add one dictionary to an array.

The Pi controlling the system is a Raspberry Pi 3B+ running Raspberry Pi OS.

## 900MHz (927.9750 MHz)

The 900MHz node is available on **927.9750 MHz** with a tone of **151.4 Hz**.
It outputs around 15 watts into a Comet KP-20 on a second-story balcony. The
eventual plan is to turn it into a low-power repeater.

The node is currently provided by a TK-941, connected to a K5TRA interface
board, which then connects via USB to the Pi mentioned above.

**NOTE:** (Currently not relevant, but will be once there is more than one
node): The 900MHz node delinks from the rest of the system most evenings, per
the schedule above, and links into the 927-Tech system. This system is intended
to be 900MHz and higher only, so in the interest of keeping true to that, only
the 900MHz node links to it, dropping from the rest of the system.

The pictures below show the layout of the node, which currently sits on a
rack-mountable shelf. It is designed to fit in a 1U enclosure, but I have not
yet acquired one. Due to the slight slant of
[the rack](https://www.amazon.com/dp/B001U14MO8/), everything is stuck to the
shelf with 3M Command Strips to prevent it from sliding back.

![Front of rack](/images/node-rack-front.jpg)
<small style="font-style:italic">
  Front-of-rack as of late August, 2021.
</small>

![Pi and interface](/images/node-900-pi.jpg)
<small style="font-style:italic">
  900MHz node Pi and K5TRA interface board.
</small>

![Top-down](/images/node-900-topdown.jpg)
<small style="font-style:italic">
  Top-down view of the 900MHz node.
</small>

## COMING SOON: UHF (445.550 MHz)

The UHF node is served by a PM400 Motorola UHF radio using the accessory jack on
the back of the radio. It connects to a K5TRA interface board, which connects to
the same Raspberry Pi as the 900MHz node. The system puts out 45 watts.
