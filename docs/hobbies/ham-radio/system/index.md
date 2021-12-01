# Repeaters and Nodes

The AI5A System currently consists of a 900MHz simplex AllStarLink node located
and accessible within EM10cf, though coverage extends roughly across the South
Central Austin area (Galindo, Dawson, Zilker, Bouldin Creek, South Lamar, SoCo,
etc.). It also consists of the [224.1 Repeater](224.100MHz.md) hosted at **The
University of Texas at Austin**, and usually linked into the KA5D
University-Link system.

The system is open for all to use!

## Affiliations and Links

The 900MHz (927.9750) simplex node ties into the N5OAK system for two nets each
week (listed below). The 224.1 repeater usually remains linked to the
University-Link system but we have plans to link it for some 220-preferred nets
in the future. As such, the 224.1 repeater carries all the nets the KA5D system
carries as well, including the Oak Hill weekly nets and the UT ARC net.

#### Nets Carried on 927.9750 Simplex Node

| Day | Time | Link | Comments |
| --- | ---- | ---- | -------- |
| Th | 20:00 | N5OAK System | Oak Hill ARC weekly net |
| F | 21:00 | N5OAK System | Oak Hill ARC weekly trivia net |

#### Nets Carried on 224.1 Repeater

| Day | Time | Link | Comments |
| --- | ---- | ---- | -------- |
| W | 20:00 | University-Link | UT ARC Social Net |
| Th | 20:00 | N5OAK System | Oak Hill ARC Social Net |
| F | 21:00 | N5OAK System | Oak Hill Arc Trivia Net |

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

## 224.1MHz (-1.6Mhz, 100Hz)

More information about the 222 repeater can be found on
[its own page](224.100MHz.md).
