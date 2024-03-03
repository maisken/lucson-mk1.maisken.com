![Front view of LUCSON MK I](/images/front_view.jpg)

_March 3rd, 2024_

Roughly 1982, a slot-load vinyl player was patented and made in Italy.
Red top, white base, the LUCSON MK I offered me countless hours of entertainment when I was a child in the late '80s.
It definitely shaped who I am as I was listening to any sorts of '70s disco music, '80s synth-pop and children fairy tales, all rigorously sold on vinyls at the time.

The turntable accepts 45PRM, 7-inch vinyls, features a relatively uncommon slot-load, and is belt driven.

When I tried to put it back into shape, roughly 40 years later, I started looking for online references, but found almost absolutely nothing, surely no pictures nor documentation.
Hence this page to document and preserve its legacy.

# Overview
![Top view of LUCSON MK I](/images/top_view.jpg)

The LUCSON MK I has only one sticker: golden background, black font, all uppercase "LUCSON MK I".
No other stickers nor mentions of a registered brand name, address or other references.

On the front, we find the slot where the vinyl is loaded, with a black button on the left, to release the vinyl;
the button pops further out when the vinyl is inserted.
Two dials allows for adjustment of "TONO" (*tone*) and "VOLUME" (that actually spells the same in Italian and English!).

Usage is pretty basic, but to the point: insert the vinyl, and it starts spinning and playing.
When you're done, push the button and get the vinyl back. There's no autostop feature.

![Bottom view of LUCSON MK I](/images/bottom_view.jpg)
On the bottom, near the mains power plug, embossed in the plastic we find one English sentence: "Made in Italy", while the other few words are all in Italian.
"Brevettato", which stands for *Patented* and, next to the battery compartment, we find "6 BATTERIE DA 1.5 VOLTS", which stands for *6 1.5 Volt batteries*.

![Made in Italy writing](/images/made_in_italy.jpg) | ![Other Italian writings](/images/italian_writings.jpg)
--- | ---

# Opening the LUCSON MK I
From the outside, the LUCSON MK I has no screws. The four holes found on the bottom would call for a screw, to no avail.
Instead, the red top is clipped to the white base on the back, as seen in the pics.

![Rear view of LUCSON MK I](/images/rear_view.jpg) | ![Rear open](/images/rear_view_open.jpg)
--- | ---

Un-clipping 40 years old plastics always presents a cracking challenge. Luckily, using pry tools made the trick.
Once opened, the top is quite uninteresting, while all the power, circuitry, motor, plate and loudspeaker sit nicely on the base.

![Inside the LUCSON MK I](/images/inside_the_case.jpg)

## Powering the device
The LUCSON MK I accepts 220VAC 50Hz (standard European) mains, as well as batteries. The 6 batteries are connected in series, hinting at a 9VDC internal circuitry.
Mains go through a transformer that outputs roughly 10VAC;
this is then fed into a textbook [bridge rectifier](https://en.wikipedia.org/wiki/Diode_bridge) that outputs 9VDC, which powers the main PCB.

Alternatively, when batteries are used, the positive pole goes straigth into the positive PCB trace;
the batteries' negative pole is protected by a diode, likely as a measure to protect the electronics from inserting the batteries with wrong polarity.

## The PCB
The PCB is a fine piece of '80s artwork, with traces seemingly drawn by hand. It is attached to the white base by two crosshead screws.

It is easily accessed by lifting the black plate bed, which simply sits on top of the white base,
by means of four rubber, shock-absorbing washers (yes, sitting on the four "holes" on the white bottom which called for a screw).

![Detail of the PCB](/images/pcb_unscrewed.jpg)

The circuitry is quite neat:
a couple of capacitors to stabilize the input voltage; one circuit driving the motor; and one circuit picking the needle input to drive the loudspeaker. That's about it.
A thermal switch, implemented as a simple pair of copper plates that separate by heat expansion, ensures "safe" (for the time!) operation;
this is put in series with a further switch that closes when the vinyl is inserted, that powers the rest of the PCB.
This is actually a nice layout that keeps the batteries fully disconected when the player is not in use; with mains, only the transformer is powered.

![Thermal switch](/images/thermal_switch.jpg)
*The thermal switch, made of two vertical copper plates touching each other, can be seen roughly at the center of the picture.*

To preserve the vintage feeling (and for lack of better knowledge), I drew the reverse-engineered schematics by hand.
I didn't bother measuring the value of all resistors and capacitors, although I probably should have;
also not shown is the thermal switch: it's in series right before the "disc inserted switch".

![Schematics](/images/schematics.png)

### The motor and its driver circuit
The motor is driven by a [TCA910](https://pdf.datasheetcatalog.com/datasheets/208/499917_DS.pdf) motor speed regulator.
The IC is branded by SGS, the Italian semiconductor company founded in 1972
that merged into [ST Microelectronics](https://en.wikipedia.org/wiki/STMicroelectronics) in 1987.
This gives a further rough indication of the dating for the LUCSON MK I turntable.

The TCA910 is used exactly like in the datasheet's typical application circuit. The variable resistor that tunes the motor speed
can be set with a flat screwdriver. Being the variable resistor only accessible once the top is removed, it is meant to be set at factory, and is not end-user configurable:
a missed opportunity to give the turntable a "pro" feature; one thing less for me to mess with when I was a child, the designer must have thought better.

The motor is rather anonymous: no specs, no rated voltage, no brand/model.
Just two wires, a metal body that accepts two crosshead screws attaching it to the black plate bed, and a pulley for the belt.

![Variable speed resistor](/images/motor_speed_variable_resistor.jpg) | ![Motor](/images/motor.jpg)
--- | ---
*Variable resistor to tune motor speed. The black dial is the "TONO" one.* | *Motor seen from below. At its left, the spring-operated "disc inserted switch", made of two copper plates. The thermal switch (not depicted) looks much like the "disc inserted switch", but is normally closed, and opens by metal heat expansion.*

### The needle and its amplifier circuit
The needle is mono, which matches with the single loudspeaker design. One needle wire is connected to ground;
the other goes through the *tone* and *volume* circuits, and eventually into the SGS-branded [TBA820T](https://www.electronicoscaldas.com/datasheet/TBA820.pdf) audio amplifier.
The IC comes in a [QIP](https://en.wikipedia.org/wiki/Quad_in-line_package) packaging, that seemed to be popular at the time.

The *tone* seems to operate as a variable low pass filter which, in practice, has little effect on the non-audiophile ear.
The *volume* is a simple resistor in series; but heck it gets loud if you set it at max!
The TBA820T is used mostly as in the datasheet's example, for a load connected to the supply voltage,
except pin 13, after the capacitor, goes to ground rather than to the supply voltage.

# Bringing the LUCSON MK I back to life
In my case, the turntable was well preserved. The slot release mechanism worked fine, as well as the motor, the loudspeaker, and the PCB components.
I mostly removed a thin layer of dust in the inside by gently blowing compressed air.

The belt was, as expected, completely dusted, so I had to find a replacement one. The original belt was square, 1.5x1.5mm width.
The circumference was measured at 500mm, however the original belt was completely stretched; a 440mm circumference should do the job.
Unfortunately, such a belt seems quite hard to find; I found a 400mm circumference, 1x1mm belt at a local shop.
After soaking the belt in hot water and stretching it by about one extra centimeter, I managed to somewhat comfortably
mount it on the player, and it got working "just fine".

![Original belt](/images/original_belt.jpg) | ![Deformed belt](/images/deformed_belt.jpg)
--- | ---
The original belt as found when opening the case... | ...and how deformed it was when pulled out of its place.

The "disc inserted switch" was rusty enough that the motor wouldn't spin often times:
that was a quick fix with some fine sandpaper.
The thermal switch was rusted to a lesser extent: being normally closed it was a tougher clean,
which I actually didn't need to do.

Clipping back the red lid felt as cracky as pulling it out; again, help of pry tools made the task doable and, in fact, repeatable a couple of times.

# That's all folks (or is it?)
I'm sure much more can be said about this fine piece of Italian engineering. The patent claim on the white base means there may
be lots of intersting documentation about this turntable. However, I haven't found a means yet to search for historic Italian patents, pre 2008.

The needle also sounded "just fine", despite surely several hours of use in the past.
Audio quality is acceptable, considering this is portable equipment, with a small,
non audiophile loudspeaker and wiring. The needle seems a bit light, jumping a bit too often.
There's a spring pulling the needle against the vinyl, which may have gotten a bit loose with time;
or maybe the needle just needs replacing. I am not sure if the needle cartdrige is easily replaced;
needles are the only web results that popped up when searching for LUCSON MK I, so that's something to explore in the future.

Know more about the LUCSON MK I, or have anything to share or add? Please open a [pull request](https://github.com/maisken/lucson-mk1.maisken.com/pulls) and contribute!

![Final image](/images/dramatic_final.jpg)
