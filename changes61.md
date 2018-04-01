AAAAA SSSSS TTTTTTT RRRRRR OOOOO L OOOOO GGGGG

A A S S T R R O O L O O G G

A A S T R R O O L O O G

AAAAAAA SSSSS T RRRRRR O O L O O G GGGG

A A S T R R O O L O O G G

A A S S T R R O O L O O G G

A A SSSSS T R R OOOOO LLLLLLL OOOOO GGGGG

\*\* VERSION 6.10 \*\*

Release notes for Astrolog version 6.10 (March 2016):

Happy Equinox and start of Aries everyone! :) This file describes the
freeware astrology software program Astrolog version 6.10 and the
additions and fixes made to it, over the previous version 6.00 which was
released three months ago in December 2015. The main things in this
update are more usage of the Swiss Ephemeris, and a number of bug fixes.

NEW FEATURES {#new-features .Section}
============

Here are new additions to version 6.10 that weren\'t in previous
versions:

**1. True positions:** Astrolog supports true planetary positions, which
means where planets actually are in space. Normally Astrolog shows
apparent positions, which is where planets appear in the sky, or the
true positions adjusted by the travel time of the speed of light. Most
astrologers and astrology software work with apparent positions
(although there's no definitive proof that astrological influences
travel at the speed of light). True positions will be up to half an
arc-minute ahead of apparent positions, e.g. light from the Sun takes
about 8 minutes to reach Earth, so the Sun has moved forward another 8
clock minutes through the zodiac. True positions can be turned on with
the new -YT command switch. In the Windows version in the Calculation
Settings dialog there's a new "Use True Positions" checkbox. For the -S
orbit chart, in which one is looking down at the solar system as a
whole, it's recommended to have true positions on (and topocentric
positions off).

**2. Topocentric positions:** Astrolog supports topocentric positions,
which means positions relative to one's location on the surface of the
Earth. Normally Astrolog shows positions relative to the center of the
Earth. Most astrologers and astrology software treat the Earth as a
single point (although there's no definitive proof that astrological
influences affect everybody on all parts of the Earth equally). Because
topocentric is relative to location on Earth, one's elevation above sea
level influences positions, and needs to be set separately (with the -zv
switch below). Positions with this setting may be different by more than
half a degree, with the maximum change being the Moon (because it's
closest to the Earth) and when planets are near the horizon, because in
those cases parallax has the biggest opportunity to alter positioning.
Topocentric positions can be turned on with the new -YV command switch.
In the Windows version in the Calculation Settings dialog there's a new
"Use Topocentric Positions" checkbox. Topocentric positions require
Swiss Ephemeris to be active (which it is by default) in order to work,
and also for the chart to be geocentric. For the -Z local horizon chart,
in which one is looking at light from the sky from their local position
on Earth, it's recommended to have topocentric positions on (and true
positions off).

**3. Krusinski houses:** Astrolog supports the Krusinski system of house
division. Krusinski houses can be selected by passing 10 (or strings
like "krusinski") to the -c house system selection switch. In the
Windows version there's a new "Setting / House System / Krusinski" menu
command. Krusinski houses require Swiss Ephemeris to be active (which it
is by default) in order to work.

**4. Sinusoidal ratio houses:** Astrolog supports the new "Pullen
(Sinusoidal Ratio)" house system. Sinusoidal Ratio houses can be
selected by passing 12 (or strings like "pullen" or "ratio") to the -c
house system selection switch. In the Windows version there's a new
"Setting / House System / Pullen (S-Ratio)" menu command. For more
information about sinusoidal house systems, and why they can be
considered the "best looking" house systems for wheel charts, see
<http://www.astrolog.org/astrolog/astsine.htm>

**5. Custom planets:** Astrolog supports custom planets beyond the set
of objects it normally works with. The new -Ye switch customizes planet
positions. It takes two parameters: One for the object to replace, and
another for the object to replace it with. The source object must be one
of the objects in the Uranian hypothetical object category (Vulcan or
one of the eight Uranians). The destination object is defined by an
index in the "seorbel.txt" text file in the Astrolog install directory.
For example, "-Ye Cup 9" will replace Cupido with Isis-Transpluto, and
"-Ye Had 18" will replace Hades with Proserpina. The name and glyphs in
the program won't change, but the positions will reflect the new object.
The -Ye switch requires Swiss Ephemeris to be active (which it is by
default) in order to work.

**6. All stars field:** In the Windows version, the More Object Settings
dialog has three new entries labeled \"All Stars\". They allow one to
set the maximum orb, the addition to orbs, and the influence for all
fixed stars. These values when set for stars will apply to all stars
equally.

**7. Graphics text scale:** The size for text within graphics charts
(such as the text in the wheel chart sidebar, and the text at the bottom
of the screen in other charts) can be changed with the new -XS switch.
On high resolution monitors with many pixels, the default text size may
be small enough to be hard to read. In the Windows version in the
Graphics Settings dialog, there's a new "Text Scale" field to set this.
(Also added to the Graphics Setting dialog is a field for the existing
-Xs switch "Character Scale" setting.) An entry for this setting also
now exists in the astrolog.as default settings file.

**8. Default name and location:** The default name and location strings
used for charts (most commonly for "now" charts) may be specified with
the new -zj switch. In the Windows version in the Default Chart Info
dialog, there are two new fields for "Name" and "Location". An entry for
these settings also now exists in the default astrolog.as default
settings file.

**9. Default elevation:** The default elevation used in topocentric
charts may be specified with the new -zv switch. In the Windows version
in the Default Chart Info dialog, there's a new "Elevation" field. An
entry for this setting also now exists in the astrolog.as default
settings file. Elevation above sea level can be expressed in meters
(with an "m" suffix) or feet ("ft" suffix). Note that this is a global
setting, so affects all charts. To fully support topocentric astrology,
the standard interface for specifying time and location should also ask
for elevation above sea level (although that piece of information would
of course be unnecessary for standard non-topocentric charts).

**10. Distance units:** When Astrolog displays distances, it's normally
in imperial units (feet or miles). The new -Yv switch will instead
display distances in metric units (meters or kilometers). In the Windows
version in the Obscure Settings dialog, there's a new "Display Lengths
in Metric Instead Of Imperial Format" checkbox. An entry for this
setting also now exists in the default astrolog.as default settings
file.

\--

Here\'s a summary of the 7 new command switches in Astrolog 6.10 that
weren\'t in previous versions:

**-zv \<elev\>:** Change the default elevation above sea level.

**-zj \<name\> \<place\>:** Change the default name and place strings.

**-XS \<100,200,300,400\>:** Change size of graphics chart text by %.

**-YT:** Compute true positions in space instead of apparent in sky.

**-YV:** Compute topocentric positions instead of from center of body.

**-Yv:** Display distance in metric instead of imperial units.

**-Ye \<obj\> \<index\>:** Change orbit of Uranian to seorbel.txt
object.

Here\'s a summary of the 2 new menu commands in the Windows version of
Astrolog 6.10 that weren\'t in previous versions:

Setting - House System - Krusinski\
Setting - House System - Pullen (S-Ratio)

EXTENDED AND IMPROVED FEATURES {#extended-and-improved-features .Section}
==============================

A list of improvements to existing features, such as new things you can
now do with old features that you couldn't do before, or ways existing
features work better than before:

**1. Swiss Ephemeris houses:** Astrolog 6.10 now uses the accurate Swiss
Ephemeris formulas for calculating house cusps, including the Ascendant,
Midheaven, and related variables. Before it only used Swiss Ephemeris
for planet positions. This changes the position of the Ascendant and
house cusps by several arc-seconds in most charts. This is a minor
effect, since on average house cusps change 15 arc-seconds every clock
second, however the improvement in accuracy is still present.

**2. Graphic latitude ephemeris:** The graphic ephemeris, as accessed
with the -E -X switch combination, normally graphs zodiac position or
longitude versus time. If the -gp or -ap parallel aspects setting is
active, then this chart will instead graph planetary latitudes. Normally
all planets are clustered near the 0 degree mark. The -YX7 switch
setting sets the radius in tenths of degrees to include, e.g. "-YX7 100"
shows +/- 10 degrees on either side of 0 degrees latitude, "-YX7 50"
shows +/- 5 degrees, and so on.

**3. Fractional harmonics:** Harmonic charts support non-integer and
negative values. Decimal or negative numbers may now be passed to the -x
harmonic factor switch. In the Windows version, decimal and negative
numbers may be specified in the Calculation Settings dialog in the
"Harmonic Chart Factor" field.

**4. Numeric latitudes:** The -sd switch setting to display positions in
numeric degree format will apply to latitude values in charts. This
includes the standard -v text chart listing and graphic wheel chart, and
the -E text mode ephemeris when listing latitudes.

**5. Greater stelliums:** The aspect configuration list will now detect
and list 3 and 4 planet conjunction stelliums separately. Before, only 3
planet stelliums would be shown, meaning a 4 planet stellium would be
listed as three separate 3 planet stelliums. Now, 4 planet stelliums are
listed separately, and the redundant 3 planet stelliums within it won't
be shown.

**6. Improved glyphs:** The default glyphs in graphics charts (the
medium or 200% scale size glyphs) have been improved. The glyphs for the
signs Gemini, Cancer, Leo, Virgo, and both versions of Capricorn look
slightly smoother. Similarly, the glyphs for the planets Saturn, the
Nodes, and four of the Uranians look smoother.

**7. Custom star influences:** The -Yj and -YjT switches for setting
standard and transiting object influence strengths have been extended
beyond the Uranians to include fixed stars. Setting slot \#43 (the index
of the first fixed star) will set the influence for all stars.
Similarly, the command line will parse the string \"star\" to match this
index of the first star. For example, "-Yj star star 4" will set the
influence of all stars to 4.

**8. Star influences and Rays:** The text mode -j switch influence chart
and -7 switch esoteric Ray chart now support fixed stars, and will
include them in the chart if they're unrestricted.

**9. Moon centered charts:** The -h switch heliocentric chart setting
can now accept the Moon (and related lunar objects such as the Nodes and
Lilith) as the central planet. Before, Moon centered charts weren't
supported, but now they're no different from any other planet with
respect to being the central body.

**10. Moon orbit view:** The zoom level of the graphic -S solar system
orbit chart will be a very small 0.006 AU, when the character scale is
Huge or 400%, and the -XS graphic text scale is set to 200% or larger.
That diameter is just large enough to fit the Moon's orbit, so works
well with geocentric or Moon object centered charts, to see the motion
of the Moon, Nodes, and Lilith around the Earth.

**11. Default extension improvement:** Specification of command switch
files doesn't require the default ".as" extension. For example, "-i
mychart" is equivalent to "-i mychart.as", and the program will check
both names before saying a file doesn't exist.

**12. Help improvement:** In the Windows version, pressing F1 will show
documentation and do the same as the "Help / Documentation / Open
Helpfile" command. That's assuming macro \#1 hasn't been defined (if
macro \#1 has been defined, F1 will still invoke that macro). Similarly,
pressing Alt+F4 will follow the Windows standard and close the program
(instead of first displaying an error about macro \#40 not being
defined, and then closing). If macro \#40 has been defined, Alt+F4 will
still only invoke that macro.

PROGRAM CHANGES & COMPILING UPDATES {#program-changes-compiling-updates .Section}
===================================

A few changes that aren\'t feature additions or bug fixes have been made
to this version, which means certain old assumptions are no longer
valid. A list of these (which aren\'t useful to be aware of unless you
have used previous versions of the program) follows:

**1. DOS graphics dropped:** The old DOS graphics versions of the
program no longer exist, which means the Microsoft and Borland PC
graphics MSG and BGI compile time options have also been removed. They
only worked with 16 bit Windows, which Astrolog doesn't support anymore,
so they couldn't be compiled anyway. As a result, a number of source
code and documentation sections have been deleted. The -V switch that
set DOS prompt text rows, and the -YX switch that selected PC graphics
modes have been removed. (Actually those switches still exist but do
nothing, so old command switch files containing them don't fail.)

**2. No Matrix routines:** Since Swiss Ephemeris is used for both planet
and house positions by default, it's possible to not even compile in any
of the very old much less accurate Matrix routines. The new \#define
MATRIX compile time option in astrolog.h may be commented out to do
this.

**3. Default settings on:** The command switch settings "-g0 -a0 -m0 -j0
-L0" are now on by default. Specifically the -g text aspect grid also
lists aspect configurations, the -a text aspect list also includes a
summary of aspects, the -m text midpoint list also includes a summary of
midpoints, the -j text influence chart includes sign influences, and the
-L text astro-graph includes a list of latitude crossings.

**4. Neo-Porphyry renamed:** The Neo-Porphyry house system that was
first implemented in Astrolog 4.10 has been renamed. It's now called
"Pullen (Sinusoidal Delta)", which is more descriptive and follows the
tradition of house systems being named after their inventor. In the
Windows version this house system is now selected with the "Setting /
House System / Pullen (S-Delta)" menu command. For more information
about this system and its history, see:
<http://www.astrolog.org/astrolog/astsine.htm>

BUG FIXES {#bug-fixes .Section}
=========

Here are problems with version 6.00, all of which have been corrected in
this release:

**1. Relationship midpoint display:** The text mode comparison midpoint
grid as accessed with -r0 -g0 displayed badly, with the rows containing
zodiac degrees distorted.

**2. Object Settings dialog bug:** In the Windows version, in the Object
Settings dialog, hitting OK would incorrectly apply each value to the
subsequent object indexes, with everything offset by one. That of course
would make the dialog very hard to use.

**3. Progression inaccuracy:** Secondary progressed charts would have
inaccurate house cusps (although the actual planet positions would be
correct). This could be seen by defining chart A, then doing a secondary
progressed chart for the exact same date and time as chart B (with the
degree per day value set to 1). The result should be identical to a
casting of chart B (which it was for planets, but not house cusps).

**4. Planet centric inaccuracy:** In a non-geocentric and
non-heliocentric chart, with some other planet as the central object,
the planet positions with object indexes beyond the central planet would
be wrong. For example, in a Jupiter centered chart, Saturn and beyond
would have inaccurate positions.

**5. Planet centric inaccuracy:** If the central planet was restricted
(in a non-geocentric and non-heliocentric chart, with some other planet
as the central object) then planet positions would be wrong, and would
be like they are in heliocentric charts.

**6. Uranian centric inaccuracy:** If a Uranian were set as the central
object, then the other Uranians would be positioned as they are in
heliocentric charts, instead of relative to the central object.

**7. South Node omission:** If the North Node were restricted, then the
South Node would always be placed at 0Lib. Internally, Astrolog needed
to still calculate the position of the North Node internally, if either
node was unrestricted.

**8. Node omission:** In non-geocentric charts, the Nodes would always
be positioned at 0Ari and 0Lib. This was only true when Swiss Ephemeris
was on, and was due to Astrolog calling Swiss Ephemeris with wrong
parameters in that situation.

**9. South Node omission:** In the -S switch solar system orbit chart,
the South Node's position in space would be 0, instead of opposite the
Moon from the North Node.

**10. Graphic orbit display:** In the graphic -S solar system orbit
chart, if Jupiter was the central object or restricted, then the zodiac
lines would be offset.

**11. Gauquelin sector omission:** In the -l switch text mode Gauquelin
sector chart, the velocity of the South Node wouldn't be displayed.

**12. Transit crash:** In the -d transit to transit hits search, having
more than 150 aspect or other events in a single time slice would crash.
This would require a low searching divisions value and many objects
unrestricted in order to happen.

**13. Astro-graph bug:** The graphic astro-graph chart as accessed with
the -L -X switches would overwrite the end of a stack array by one.
Usually this wouldn't affect the chart, however certain environments
such as compiling and running the debug Windows version would detect and
display an error during runtime.

**14. Astro-graph display:** Clicking on the graphic astro-graph chart
as accessed with the -L -X switches, normally resets the main chart's
location to the position clicked. However, doing do would actually place
the location one degree too far down (South) and right (East) by a
degree.

**15. Sidebar display:** In the graphic wheel chart sidebar, when the
print nearest seconds setting was on, fixed stars would display their
latitude with too much precision, and overflow the right edge of the
sidebar.

**16. Constellation display:** In the -XF constellation map display, if
the character scale was 300% or more, then extra dots would be
incorrectly drawn a pixel beyond the right edge of the chart.

**17. Placidus bug:** Placidus houses aren't defined for locations above
the Arctic Circle, and attempting to cast such a chart displays an error
message, which is good. However, Astrolog would then proceed with a
chart containing misaligned houses. Now in such a situation, Astrolog
will fall back to Porphyry houses after showing the error.

**18. Neo-Porphyry bug:** The Neo-Porphyry system (now called Pullen
Sinusoidal Delta) would produce overlapping houses when a quadrant was
less than 30 degrees in size. Now in this house system, when a small
quadrant pinches the smallest middle house to 0 size, it will remain 0
degrees as the quadrant continues to decrease, instead of becoming
negative sized.

**19. Windows resize display:** In the Windows version, the Chart
Resizes Window ("Q" hotkey) and Size Window To Cart ("Alt+u" hotkey)
menu commands would work, however when repeated they would continually
shrink the chart slightly. Now these commands will behave as expected
and do nothing more when run multiple times in a row.

**20. Defaults display:** Starting the program with no astrolog.as
default settings file present, would result in invisible black planets
on a black background in graphics charts. The Astrolog executable
initialized planets to black, which the astrolog.as file when present
would replace with the correct colors. Now the planets are initialized
internally to standard default colors, so they don't rely on astrolog.as
to set them.

LICENSE {#license .Section}
=======

IMPORTANT NOTICE: Astrolog and all chart display routines and anything
not enumerated below used in this program are Copyright (C) 1991-2016 by
Walter D. Pullen (<Astara@msn.com>,
<http://www.astrolog.org/astrolog.htm>). Permission is granted to freely
use, modify, and distribute these routines provided these credits and
notices remain unmodified with any altered or distributed versions of
the program.

The main ephemeris databases and calculation routines are from the
library SWISS EPHEMERIS and are programmed and copyright 1997-2008 by
Astrodienst AG. The use of that source code is subject to the license
for the Swiss Ephemeris Free Edition, available at
<http://www.astro.com/swisseph>. This copyright notice must not be
changed or removed by any user of this program.

Additional ephemeris databases and formulas are from the calculation
routines in the program PLACALC and are programmed and Copyright (C)
1989,1991,1993 by Astrodienst AG and Alois Treindl (<alois@azur.ch>).
The use of that source code is subject to regulations made by
Astrodienst Zurich, and the code is not in the public domain. This
copyright notice must not be changed or removed by any user of this
program.

The original planetary calculation routines used in this program have
been copyrighted and the initial core of this program was mostly a
conversion to C of the routines created by James Neely as listed in
\'Manual of Computer Programming for Astrologers\', by Michael Erlewine,
available from Matrix Software.

The PostScript code within the core graphics routines are programmed and
Copyright (C) 1992-1993 by Brian D. Willoughby (<brianw@sounds.wa.com>).

More formally: This program is free software; you can redistribute it
and/or modify it under the terms of the GNU General Public License as
published by the Free Software Foundation; either version 2 of the
License, or (at your option) any later version. This program is
distributed in the hope that it will be useful and inspiring, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General
Public License for more details, a copy of which is in the LICENSE.HTM
file included with Astrolog, and at
[http://www.gnu.org](http://www.gnu.org/)

O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O

\* Walter D. \"Cruiser1\" Pullen :) ! <Astara@msn.com> \*

O Astrolog 6.10 homepage:
<http://www.magitech.com/astrolog/astrolog.htm> O

\* \"Who am I, What am I? As I am, I am not. But as we are, I AM. And to
\*

O you my creation, My Perfect Love is your Perfect Freedom. And I will
be O

\* with you forever and ever, until the End, and then forever more.\" -
GOD \*

O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O
