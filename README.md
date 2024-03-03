![Front view of LUCSON MK I](/images/front_view.jpg)

_March 3rd, 2024_

Roughly 1982, a slot-load vinyl player was patented and made in Italy. Red top, white base, the LUCSON MK I offered me countless hours of entertainment when I was a child in the late '80s.
It definitely shaped who I am as I was listening to any sorts of '70s disco music, '80s synth-pop and children fairy tales, all rigorously sold on vinyls at the time.

The turntable accepts 45PRM, 7-inch vinyls, features a relatively uncommon slot-load, and is belt driven.

When I tried to put it back into shape, roughly 40 years later, I started looking for online references, but found almost absolutely nothing, surely no pictures nor documentation.
Hence this page to document and preserve its legacy.

# Overview
![Top view of LUCSON MK I](/images/top_view.jpg)

The LUCSON MK I has only one sticker: golden background, black font, all uppercase "LUCSON MK I". No other stickers nor mentions of a brand name, address or other references.

On the front, we find the slot where the vinyl is loaded, with a black button on the left, to release the vinyl; the button pops further out when the vinyl is inserted. Two dials allows for adjustment of "TONO" (*tone*) and "VOLUME" (that actually spells the same in Italian and English!).

Usage is pretty basic, but to the point: insert the vinyl, and it starts spinning and playing. When you're done, push the button and get the vinyl back. There's no autostop feature.

![Bottom view of LUCSON MK I](/images/bottom_view.jpg)
On the bottom, near the mains power plug, embossed in the plastic we find one English sentence: "Made in Italy", while the other few words are all in Italian. "Brevettato", which stands for *Patented* and,
next to the battery compartment, we find "6 BATTERIE DA 1.5 VOLTS", which stands for *6 1.5 Volt batteries*.

![Made in Italy writing](/images/made_in_italy.jpg) | ![Other Italian writings](/images/italian_writings.jpg)
--- | ---

# Opening the LUCSON MK I
From the outside, the LUCSON MK I has no screws. The four holes found on the bottom would call for a screw, to no avail. Instead, the red top is clipped to the white base on the back, as seen in the pics.

![Rear view of LUCSON MK I](/images/rear_view.jpg) | ![Rear open](/images/rear_view_open.jpg)
--- | ---

Un-clipping 40 years old plastics always presents a cracking challenge. Luckily, using pry tools made the trick. Once opened, the top is quite uninteresting, while all the power, circuitry, motor, plate and loudspeaker sit nicely on the base.

![Inside the LUCSON MK I](/images/inside_the_case.jpg)

## Powering the device
The LUCSON MK I accepts 220V AC 50Hz (standard European) mains, as well as batteries. The 6 batteries are connected in series, hinting at a 9VDC internal circuitry.
Mains go through a transformer that outputs roughly 10VAC; this is then fed into a textbook [bridge rectifier](https://en.wikipedia.org/wiki/Diode_bridge) that outputs 9VDC, which powers the main PCB.

Alternatively, when batteries are used, the positive pole goes straigth into the positive PCB trace; the batteries' negative pole is protected by a diode, likely as a measure to protect the electronics from inserting the batteries with wrong polarity.

## The PCB
The PCB is a fine piece of '80s artwork, with traces seemingly drawn by hand. It is attached to the white base by two crosshead screws.

It is easily accessed by lifting the black plate bed, which simply sits on top of the white base, by means of four dampered holes (yes, the four "holes" on the bottom which called for a screw).

![Detail of the PCB](/images/pcb_unscrewed.jpg)

The circuitry is quite neat:
a couple of capacitors to stabilize the input voltage; one circuit driving the motor; and one circuit picking the needle input to drive the loudspeaker. That's about it.
Nice additions are: a thermal switch, implemented as a simple pair of copper plates that separate by heat expansion;
this is put in series with a switch that activates when the vinyl is inserted, that powers the rest of the PCB.

To preserve the vintage feeling (and for lack of better knowledge), I drew the reverse-engineered schematics by hand.
I didn't bother measuring the value of all resistors and capacitors, although I probably should have; also not shown is the thermal switch: it's in series right before the "disc inserted switch".

![Schematics](/images/schematics.png)

### The motor driver circuit
The motor is driven by a [TCA910](https://pdf.datasheetcatalog.com/datasheets/208/499917_DS.pdf) motor speed regulator. It's used exactly like in the datasheet's typical application circuit. The variable resistor that tunes the motor speed can be set with a flat screwdriver; being only accessible once the top is removed, it is meant to be set at factory, and is not end-user configurable.
