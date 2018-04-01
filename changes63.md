AAAAA SSSSS TTTTTTT RRRRRR OOOOO L OOOOO GGGGG

A A S S T R R O O L O O G G

A A S T R R O O L O O G

AAAAAAA SSSSS T RRRRRR O O L O O G GGGG

A A S T R R O O L O O G G

A A S S T R R O O L O O G G

A A SSSSS T R R OOOOO LLLLLLL OOOOO GGGGG

\*\* VERSION 6.30 \*\*

Release notes for Astrolog version 6.30 (October 2017):

Happy start of Scorpio everyone! :) This file describes the freeware
astrology software program Astrolog version 6.30 and the additions and
fixes made to it, over the previous version 6.20 which was released
seven months ago in March 2017. The main things in this update are 3D
chart spheres (instead of just 2D chart wheels), graphical transit
charts, and object customization.

NEW FEATURES {#new-features .Section}
============

Here are new additions to version 6.30 that weren\'t in previous
versions:

**1. Chart spheres:** Astrolog now supports chart spheres, which are
like standard chart wheels but in 3D. Chart spheres make it easy to see
the ecliptic latitude of planets in addition to their zodiac longitude.
They are most similar to Astrolog's graphic local horizon charts, except
instead of being a flat rectangular map, the celestial sphere is
rendered like a globe. Create chart spheres with the new -XX command
switch, or in the Windows version with the "Graphics / Show Chart
Sphere" menu command.

In a chart sphere, its equator marks the plane of the local horizon.
Lines are drawn from the center in the four directions, which are
labeled around the horizon. Between the zenith point straight up, and
the nadir point straight down, can be seen the prime vertical running
through the east and west points on the horizon, and the meridian
running through the north and south points on the horizon. The 3D
boundaries of the 12 houses can be seen, in which houses 1-6 are below
the horizon and houses 7-12 are above, and in which houses 1-3 and 10-12
are east of the meridian and houses 4-9 are west of the meridian.
Display of the houses can be toggled with the 3D houses flag (-c3
switch, or the Setting / House Settings / 3D Houses command, or with the
"a" key). In addition, the ecliptic and the 12 zodiac sign wedges are
displayed. Display of signs can be toggled with the Vedic format flag
(-J switch, or the Setting / House Settings / Vedic Wheel Display
command, or with the "z" key).

Planets will be plotted on the surface of the sphere based on their
zodiac position and latitude locations. Most planets will be on or near
the ecliptic, except for asteroids and especially fixed stars. Aspect
lines will be drawn through the middle of the sphere. If aspect lines
make the display too cluttered, the orbs can be reduced or aspects
turned off altogether.

The sphere overlaps its "near" and "far" sides, with the far side solid,
and the near side semitransparent in which planets and such are rendered
in gray. This simulates the viewer being inside the sphere, focusing
upon what is in distance, such as a person looking south toward the
ecliptic assuming a northern hemisphere chart location. If the -XX
switch is invoked as -XX0 instead, the transparency will be reversed and
the near side will be solid and the far side semitransparent, as if one
were outside the sphere looking upon its surface. In the Windows
version, the "Globe Halves Focus On Southern Hemisphere" flag in the
Graphics Settings dialog controls this, and can be toggled with the
Graphics / Modify Chart command. If you don't want any overlap at all,
turn on the modify display flag (with the -Xi switch, or the Graphics /
Modify Display menu command) and only the solid half of the sphere will
be drawn.

Similar to Astrolog's existing globe display, the chart sphere can be
rotated and tilted. Two optional parameters to the -XX switch indicate
how much the sphere should be rotated around its axis, and how much it
should be tilted toward or away from the viewer. While a window is up,
the sphere can be rotated left and right with the "{" and "}" keys (or
the Graphics / Globe Tilt / Rotate West and Rotate East menu commands),
and can be tilted with the "\[" and "\]" keys (the Graphics / Globe Tilt
/ Tilt North and Tilt South commands). Rotating and tilting is a good
way to better visualize the sphere and its contents.

**2. Transit graphs:** Astrolog has a graphical transit chart, which
consists of a table of transit aspects, each aspect of which has its
strength mapped over a period of time. The result makes it easy to see
when an aspect enters orb, is exact, and leaves orb. These graphs also
allow seeing cases when an aspect comes close to but never becomes
exact, which is a situation missed by charts that only display times
when aspects are exact. The transit graph comes in two forms: transit to
transit, and transit to natal. Both forms can be displayed to show
aspects within a single day, a single month, a single year, or a range
of five years. Counting text mode and graphics mode versions of these
charts, there are 2x4x2 = 16 different transit graph chart types total!
The transit to transit graph is accessed via the new -B command switch,
which is identical in syntax to the existing -d transit to transit times
search, including all subswitches. The transit to natal graph is
accessed via the new -V command switch, which is identical in syntax to
the existing -T transit influence list, including all subswitches. In
the Windows version there are new "Transit To Transit Graph" and
"Transit To Natal Graph" options in the Transits dialog.

The total number of different aspects that are active within the period
may be high, especially when considering fast moving objects like the
Moon and especially house cusps. Note that for graphic charts, if there
are too many transits to fit within the screen height, then later
aspects will be skipped. By default transit graphs don't include aspects
involving certain fast moving bodies. Graphs involving a single day will
skip house cusp objects, graphs involving a month will skip the Moon as
well, and graphs involving year(s) will skip the Sun through Mars as
well. If the -B and -V switches are invoked as -B0 and -V0, then this
automatic restriction won't happen. In the Windows version, this can be
toggled with the "Graphics / Modify Chart" command.

In text mode transit graphs, each aspect has its own row, and each
character within a row represents a time period. If the aspect is within
orb at that time, then a digit from 0-9 is placed there, in which "0"
means the orb is 0-10% exact on up to "9" which means the orb is 90-100%
exact. Peaks in influence (which usually but not always indicate when
the aspect is exact or 100% within orb) are colored white to make them
stand out better. Every row will have at least one high point marked,
even if it's on one of the edges where an orb is increasing at the
boundary. In addition, for the transit to transit graphs, the column
corresponding to the time of the chart will be marked with vertical bar
characters. Transit graphs also come in a graphics version (unlike the
existing transit time and transit influence charts which only have text
versions). In the graphics mode transit graphs, each aspect has its own
row, in which each row is a mini-graph plotting the aspect's strength
over time. Peaks and high points will be marked in white, and for the
transit to transit case, the column corresponding to the time of the
chart will be marked in dark green (unless the -Xi switch modify display
setting is active).

**3. 3D aspects:** Aspect calculations can take the latitude of the
planet into account. In other words, the angle between two planets is
based on the 3D great circle distance between them on the celestial
sphere, and not just the 2D difference between their zodiac position
longitudes. Turn on 3D aspects with the new -A3 switch, or the Windows
version with the new "3D Aspects" checkbox in the Calculation Settings
dialog.

For example, during a New Moon the Sun and Moon may be as much as 5
degrees different in latitude, which means that even when a New Moon is
exact, the 3D aspect orb between them may be up to 5 degrees. (If the
Sun and Moon are conjunct in both zodiac position and latitude, then a
solar eclipse is taking place.) For bodies with latitudes that can be
widely different from the ecliptic, such as Pluto, asteroids, and
especially fixed stars, the difference is more pronounced. For example,
a body at 0Leo and -30 latitude will be Square a body at 0Leo and +60
latitude, even though they're both at the same longitude and would be
considered Conjunct normally.

**4. Custom asteroids:** Astrolog can access custom bodies whose
positions are in external Swiss Ephemeris format ephemeris files (such
as Eris and Sedna) with the new -Yeb switch. This is similar to the -Ye
switch which allows accessing the orbital elements of fictitious bodies
in the seorbel.txt file. Simply download the desired ephemeris file from
<ftp://ftp.astro.com/pub/swisseph/ephe/> and place it in the same
directory as the other ephemeris files. Pass the number of the ephemeris
file to the -Yeb switch, and the Uranian object in question will be
replaced with the positions of the new object. For example, to show the
position of Eris, download
<ftp://ftp.astro.com/pub/swisseph/ephe/ast136/s136199.se1> and then do
"-Yeb Cup 136199" to replace the position of Cupido with Eris. See
<http://www.astro.com/swisseph/astlist.htm> for an index of which
asteroids map to which numbers. You may also want to change the object's
name and graphic glyph to complete the customization.

**5. Nodes and helions:** Astrolog can access the nodes and helion
points of planets, by defining them as custom bodies. The -Ye command
switch can be invoked in four different ways to select these points:
-Yen for the north or ascending node, -Yes for the south or descending
node, -Yep for the perihelion point or point on its orbit nearest the
Sun, and -Yea for the aphelion point or point farthest from the Sun.
These four points exist in space, and the planet in question will pass
through them along its orbit. As with the Moon's nodes, Astrolog's true
node vs. mean node setting (-Yn switch) will influence these positions.
The -Ye switch is invoked in one of three ways to indicate the type of
object in question: -Ye by itself for fictitious bodies in seorbel.txt,
-Yeb for asteroids in custom ephemeris files, and -YeO for an existing
planet in Astrolog's standard list. For example, "-Yen Cup 9" redefines
Cupido's slot to be the north node of Transpluto or seorbel.txt object
\#9, "-Yebs Cup 9" redefines Cupido to be the south node of the asteroid
Metis assuming se00009s.se1 has been downloaded, and "-YeOa Cup 9"
redefines Cupido to be the aphelion point of Neptune or Astrolog object
\#9.

**6. Swiss Ephemeris stars:** The Swiss Ephemeris is now used for
computing the positions of fixed stars. Star positions are taken from
the new file sefstars.txt that comes with Astrolog's installation. This
may cause star positions and brightness to change slightly from what
Astrolog did before. Stars can still be computed in the old manner with
the new -bU command switch. There's little reason to not use Swiss
Ephemeris, although fixed stars are computed slightly faster in the old
way.

**7. Star renaming:** Astrolog's list of stars can now be customized.
The new -YU command switch takes two parameters: The existing object
index or star name to replace, and a string for a star name from the
file sefstars.txt in the Astrolog install directory to compute instead.
This star name can be the traditional or common name in the first column
of the file, or the scientific nomenclature name in the second column of
the file if the name starts with a comma. For example, "-YU Acheron
Deneb" or "-YU 43 ,alCyg" will both replace the star Acheron (object
\#43) with the star Deneb or Alpha Cygni. You may also want to change
the object's name to complete the customization. If a star is renamed to
"" or the empty string, then that will turn off customization for that
slot, and return to Astrolog's internal default. This feature requires
Swiss Ephemeris to be the active method of star computation in order to
work.

**8. Object renaming:** Astrolog can change the name of objects, or what
string is used to display them in charts. The new -YD command switch
takes two parameters: The object index to rename, and the string to use
when displaying it. Object names must be at least three characters long,
and anything shorter will make the object revert back to its default
name. Note that renaming objects only changes how they're displayed in
charts, which means command switches and such still need to refer to the
object by its default name.

**9. Glyph redefinition:** Astrolog can change the glyphs used to
display objects in graphics charts. The new -YXD command switch takes
three parameters: The object index to rename, and two strings which
contain the small and large definitions to use for the object's glyph.
The small definition measures 9x9 units (and is used when drawing in the
small 100% character scale), and the large definition measures 17x17
(and is used when drawing in the medium 200% character scale). If the
large definition is the empty string then a double scale version of the
small glyph will be used for it, and if the small definition is the
empty string then the default glyph for that object will be used. Glyphs
are drawn in vector format by moving a pen (similar to the "draw"
command in the BASIC programming language) and drawing starts from the
middle unit coordinate. Strings consist of a sequence of actions, each
of which starts with a character indicating how to move the pen,
following by a number indicating how many units to move in that
direction (no number defaults to one unit).

The action characters "U", "D", "L", and "R" move up, down, left, and
right. Similarly, "E", "F", "G", and "H" move 45 degrees up and to the
right, down and to the right, down and left, and up and left. The action
prefix "B" before one of the directions means "blank", and moves the pen
without drawing a line while moving. The prefix "N" before one of the
directions means "no update", and doesn't move the pen after drawing a
line. For example, the default small glyph for Jupiter is:
"BH3RFDGDGDR5NDNR2U6E". Special case: If a definition consists of "T"
then don't do any pen drawing at all, but instead use the three letter
abbreviation of the object name for display, like is done with fixed
stars.

**10. Moshier Ephemeris:** When ephemeris files are unavailable, the
Swiss Ephemeris automatically falls back to using a slightly less
accurate internal ephemeris and formulas by Steve Moshier. The Moshier
ephemeris is based on the JPL DE404 ephemeris, which covers 6000 years
(-3000 BC to 3000 AD), and computes planets to within 0.1 arc seconds,
and the Moon within 3 arc seconds. The new -bs switch will force
Astrolog to use the Moshier ephemeris, even if the more accurate
ephemeris files are available. In the Windows version, in the
Calculation Settings dialog, the "Calculation Method" dropdown contains
a new "Moshier Ephemeris" entry (assuming Swiss Ephemeris itself has
been compiled into the program, of course).

**11. Semitransparent globe:** The graphic globe display (as selected
with the -XG switch, or the "Graphics / Globe" menu command) can be
displayed semitransparently, with the continents or constellations on
the back side of the globe drawn in a dotted fashion. Select this option
with the new -XG0 subswitch, or by turning on "Globe Halves Focus On
Southern Hemisphere" in Graphics Settings. In the Windows version, this
can be toggled with the "Graphics / Modify Chart" command.

**12. Reverse restriction:** A "reverse restriction" is a required
object that must be present in charts involving aspects between planets.
For example, if you want to see only aspects or transits involving Mars
(such as Mars Trine Venus, and Mars Trine Jupiter, but not Venus Trine
Jupiter) then Mars is considered required. Indicate the required planet
by passing it to the new -RO command switch, or entering it in the new
"Required Object For Aspects" field in the Display Settings dialog. Set
it to -1, "None", or the empty string to turn this option off and not
have a required object.

**13. Relationship midpoint grid:** The new -gm switch will make the
relationship aspect grid between two sets of chart data show midpoints
instead of aspects. In the Windows version, there's a new "Relationship
Aspect Grid Shows Midpoints Instead" checkbox in the Chart Settings
dialog to access this setting. Also in the Windows version, the
"Graphics / Modify Chart" command will toggle this setting and switch
between aspects and midpoints. Note that accessing the relationship
midpoint grid no longer reuses the -g0 show aspect configurations
switch, as it did in previous versions.

**14. Progress to time:** The new -pt switch is just like -p, except in
addition to month/day/year parameters for the date to progress to, it
also takes a fourth parameter for the time within the date. Progressed
charts usually move so slowly that one doesn't care about time, but time
can be specified for extra precision. (This was a rare example of
something supported in the Windows version that couldn't be done with
the command line.)

**15. Transit influence time:** The new -Tt switch is just like -T,
except in addition to month/day/year parameters for the transit
influence chart date, it also takes a fourth parameter for the time
within the date.

**16. Keep graphics square:** The new -XQ switch will force all graphics
charts to be square, assuming they can be resized arbitrarily and look
better when square. In the Windows version, there's a new "Ensure Square
Charts Remain Square" checkbox in the Graphics Settings dialog. This
option is similar to running the "Graphics / Square Screen" command
after every window resize (except it won't automatically resize the
window to fit the final chart size, but rather will draw within the
largest square area within the window). This option is on by default,
and will prevent the old behavior of resizing the initial wheel chart
resulting in a distorted elliptical wheel.

**17. Wheel decoration:** The new -YXv switch specifies how to decorate
the corners of wheel charts. Parameter \#1 is 0 for no decoration, 1 for
a spider web pattern, or 2 for a Moiré pattern. Parameter \#2 is
optional, and indicates how far along the edge of the wheel chart the
decoration extends, as a percentage from 1 to 100. For example, if this
is 50 then the patterns in each corner will just touch those in adjacent
corners. Note that values too high will impede display because they'll
start overlapping the wheel itself. Parameter \#3 is also optional, and
indicates how many lines are used to compose the spider web pattern. In
the Windows version, the Graphics Settings dialog has a new "Wheel
Corners" group with a radio button allowing one to select None, Spider
Web, or Moiré Pattern, and a control for the coverage percentage.

**18. Animation subject setting:** The new -XN switch controls whether
animating a map display (such as a globe, map, or chart sphere) will
animate the orientation of the map itself or the time of the chart
within the map. By default map displays animate the map orientation,
however this option allows one to animate the chart within the map. In
the Windows version, the Graphics Settings dialog has a new "Animate Map
Instead Of Time" checkbox to toggle this setting.

**19. Map rotation stepping:** In the Windows version, there are new
Rotate West and Rotate East menu commands (with the "{" and "}" key
shortcuts) on the Graphics / Globe Tilt submenu. They allow one to
rotate map displays, even when animation (and therefore the Step Forward
and Step Backward commands accessed via the "+" and "-" key shortcuts)
is set to affect the time of the chart. The number of degrees that these
commands rotate the map by is determined by the Animation Jump Factor
setting.

**20. Sign and house highlighting:** The new -YXk switch will cause
graphics charts to highlight zodiac sign boundaries in extra color. For
example, wheel charts, solar system orbit charts, and the graphic
ephemeris will have sign boundaries drawn in the color of each sign
instead of always in grayscale. This also influences the display of
chart spheres, and local horizon charts when 3D houses are on. If the
switch is invoked as -YXk0 instead, then the 12 houses will be
highlighted in extra color as well. Some may find the extra coloring
makes charts stand out more, while others may find it to be too much and
actually make charts harder to read.

**21. Windows Autosave bitmaps:** In the Windows version, the new -Wo0
switch causes the program to automatically save a bitmap of the current
graphics screen to a continually increasing sequence of bitmap files
whenever the screen is updated, to "ast00000.bmp", "ast00001.bmp", and
so on. Each time the -Wo0 switch is invoked, the counter will be reset
to zero. This specialized feature allows external programs to see a list
of Astrolog screenshots, which can be used for scenarios such as
creating animated GIF's:
<http://www.astrolog.org/astrolog/screen/globe.gif>

**22. Chart appending:** The new -Yq command switch allows appending
multiple text charts within a single display. It takes between 0-9
parameters, depending on whether it's invoked as -Yq0, -Yq1, and so on.
If there's no digit character after -Yq, then it's assumed to have zero
parameters, and will turn off this feature. Astrolog will treat each
parameter as a command line, and then display the resulting chart after
each command line is processed. This is basically equivalent to having a
batch script invoke Astrolog several times in a row and appending the
results together. For example, "-Yq2 '-n \_e =dm -R0 Sun Moo -A 0 -RA
Opp -YR0 1 1' '-i set \_e \_d \_YR Mer Eas 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
0 0 0 0'" will print a chart for the time of the Full Moon this month.

\--

Here\'s a summary of the 29 new command switches in Astrolog 6.30 that
weren\'t in previous versions:

**-gm:** For comparison charts, show midpoints instead of aspects.

**-B:** Like -d but graph all aspects occurring in a day.

**-B\[m,y,Y\]:** Like -B but for entire month, year, or five years.

**-B0:** Like -B but don\'t restrict fast moving objects from graph.

**-Tt \<month\> \<day\> \<year\> \<time\>:** Like -T but specify time
too.

**-V\[\...\]:** Like -t but graph all transits occurring during period.

**-V0\[\...\]:** Like \_V but don\'t restrict fast moving objects from
graph.

**-RO \<obj\>:** Require object to be present in aspects.

**-A3:** Aspect orbs consider latitude as well as zodiac position.

**-bs:** Use less accurate Moshier ephemeris instead of Swiss Ephemeris.

**-bU:** Use inaccurate Matrix formulas for fixed stars only.

**-p\[0\]t \<month\> \<day\> \<year\> \<time\>:** Like -p but specify
time too.

**-XQ:** Ensure square charts remain so regardless of bitmap size.

**-XX\[0\] \[\<degrees\> \[\<degrees\>\]\]:** Display chart sphere
instead of wheel.

**-XN:** Map animates chart time instead of rotating map itself.

**-Wo0:** Continually autosave graphics screen to numbered files.

**-Yq\[0-9\] \<strings\>:** Define command lines to run and show in
sequence.

**-Yeb \<obj\> \<index\>:** Change orbit of Uranian to external
ephemeris.

**-YeO \<obj1\> \<obj2\>:** Change orbit of Uranian to internal planet.

**-Ye\[bO\]n \<obj\> \<index\>:** Change Uranian to North Node of
object.

**-Ye\[bO\]s \<obj\> \<index\>:** Change Uranian to South Node of
object.

**-Ye\[bO\]a \<obj\> \<index\>:** Change Uranian to apihelion of object.

**-Ye\[bO\]p \<obj\> \<index\>:** Change Uranian to perihelion of
object.

**-YU \<obj\> \<name\>:** Change position of star to sefstars.txt entry.

**-YD \<obj\> \<name\>:** Customize display name of object.

**-YXD \<obj\> \<string1\> \<string2\>:** Customize glyphs for planet.

**-YXv \<type\> \[\<size\> \[\<lines\>\]\]:** Set wheel chart
decoration.

**-YXk:** Use more color for sign boundaries in graphics charts.

**-YXk0:** Use more color for house boundaries in graphics charts too.

Here\'s a summary of the 3 new menu commands in the Windows version of
Astrolog 6.30 that weren\'t in previous versions:

Graphics / Chart Sphere

Graphics / Globe Tilt / Rotate West

Graphics / Globe Tilt / Rotate East

EXTENDED AND IMPROVED FEATURES {#extended-and-improved-features .Section}
==============================

A list of improvements to existing features in Astrolog 6.30, such as
new things you can now do with old features that you couldn't do before,
or ways existing features work better than before:

**1. Text comparison listing:** The standard text chart listing now has
a relationship comparison mode. This is the text mode version of a bi,
tri, or quad wheel chart, and is displayed with the -v -r0 switch
combination, or in the Windows version by turning on "Info / Comparison
Chart" and turning off "View / Show Graphics". The two to four charts
covered will each have of their planet positions (both zodiac position
and latitude) listed side by side. Also included is a delta, listing the
distance between each pair of planets, or the maximum distance between
any two planets in the case of tri and quad charts. This delta distance
is the difference between zodiac positions (unless the 3D Aspects
setting is active, in which case it will be the great circle distance
taking latitude into account too).

**2. Sidebar multiple charts:** The sidebar next to graphic chart wheels
which lists the chart information and positions, has been extended to
better support relationship charts involving two or more charts. Before
only one set of chart information would ever be shown. Now both sets (or
all three or four sets in the case of tri and quad wheels) will be
shown. Each set of chart information will be properly labeled, such as
synastry chart sidebars will indicate which set of chart information is
determining the houses and which the planets.

**3. Graphics grid autosize:** The graphic aspect and midpoint grid can
autosize itself to cover the number of unrestricted objects present in
it. If the grid size setting is set to zero (by "-YXg 0" on the command
line, or by setting the "Number Of Cells In Graphics Aspect Grid" to 0
in the Graphics Settings dialog) then the size to use will be
autodetermined. Before, the graphic aspect grid always had a fixed
number of rows, which could truncate objects or have blank rows/columns
depending on the number of objects present.

**4. Esoteric element colors:** Setting the color of an object to
"Element" (which gets the color of the element of the sign that it
rules) now has the option to use esoteric or Hierarchical rulers, in
addition to the default standard rulers. The alternate rulership sets
will be used based on the rulership restrictions (as set with the -YR7
switch, or "Rulership Restrictions" in the Display Settings dialog).

**5. Object colors interface:** In the Windows version, the colors for
planets and other objects may be selected in the Object Settings and
More Object Settings dialogs. These dropdowns also allow selecting
"Element" or "Ray" to become the colors of the element of the sign that
the planet rules, or the Ray associated with the sign. This allows the
Windows interface to access the functionality of the -YkO command
switch.

**6. Ray colors interface:** In the Windows version, the colors of the
esoteric seven Rays may be changed in the Set Colors dialog. This allows
the Windows interface to access the functionality of the -Yk7 command
switch.

**7. Biorhythm size interface:** In the Windows version, the number of
days covered by biorhythm charts has been added to the Chart Settings
dialog. This "Number Of Days Biorhythm Chart Covers" field allows the
Windows interface to access the functionality of the -Yb command switch.

**8. 3D Houses interface:** In the Windows version, there's a new "3D
Houses" checkbox in the Calculation Settings dialog. That's another way
to access the functionality of the -c3 command switch, in addition to
the "3D Houses" menu command.

**9. World map planet zeniths:** The world map display (-XW switch) and
the polar globe display (-XP switch) will overlay the map with the
zenith locations of each object in the alternate display mode (-Xi
switch). Before, only the globe display (-XG switch) supported this
planet overlay.

**10. Globe tilt stepping:** In the Windows version, the commands on the
Globe Tilt submenu will adjust the map by the animation jump factor,
instead of always by just one unit.

**11. Alt+click relocation:** In the Windows version, when an
astro-graph or world map is being shown, holding down the Alt key and
clicking will change the longitude and latitude of the current chart to
the location clicked upon. This does the same as right mouse clicking on
the window.

**12. Windows file save improvement:** In the Windows file save dialogs,
saving a file without the extension delimiter \".\" in the name will
automatically append the default extension \".as\". If for some reason
one really does want to save a file without any extension, they should
just append a "." to the filename to give it a zero length extension.

**13. Setup improvement:** In the Windows version, the Register File
Extensions command no longer requires Administrator privileges on most
versions of Windows. Before, this command and the program's initial
install would often result in the error: "Failed to register Astrolog
file extensions. You may need to run Astrolog as Administrator for
registering to succeed."

**14. Windows command line build:** In the source code, there's a new
WCLI \#define. When uncommented, it will compile a command line version
of Astrolog on the Windows platform that has the ability to bring up a
generic window with the -X switch. This new build is different from the
standard Windows version (which is a full windowed program and not a
command line program). The WCLI window won't have a menu bar, but it
will still accept keypresses. It's basically a Windows version of the
X11 and Mac graphics versions, just compiled for Windows instead of
those alternate platforms. The WCLI version is more limited, but useful
for testing the generic window source code of the program without having
to go to different platforms.

**15. Windows 64 bit build:** Astrolog's source code can now compile 64
bit instances of the Windows version. The Windows About dialog and the
-Hc switch display will indicate whether a 32 or 64 bit version of the
program is running. Internally, the sources look for the compiler set
\#define \_WIN64 to indicate 64 bit specific content.

PROGRAM CHANGES {#program-changes .Section}
===============

A few changes that aren\'t new feature additions or bug fixes have been
made to Astrolog 6.30, which means certain old assumptions are no longer
valid. Most can be considered improvements, but they still change
existing behavior. A list of these follows (which aren\'t useful to be
aware of unless you have used previous versions of the program):

**1. Relationship midpoint grid interface:** The relationship midpoint
grid between two sets of chart data is now accessed via the new -gm
command switch, and no longer via -g0. Similarly, in the Windows version
there's a new "Relationship Aspect Grid Shows Midpoints Instead"
checkbox in the Chart Settings dialog to access this setting. In the
Windows version, the "Graphics / Modify Chart" command will toggle the
-gm setting and switch between aspects and midpoints. Before, accessing
the relationship aspect grid used the -g0 show aspect configurations
switch. Since the -g0 setting is on by default, the old behavior would
make the -g grid chart show a relationship midpoint grid by default
instead of an aspect grid, which was unintuitive.

**2. Aspect colors moved:** In the Windows version, colors for aspects
have been moved from the generic Set Colors dialog to the Aspect
settings dialog. This change allows aspect colors to be viewed and
changed along with everything else related to each aspect.

**3. Polar globe expanded.** The polar globe display (accessed via the
-XP switch, or the "Show Polar Globe" command in the Windows version)
has been changed to show the entire world instead of just the top or
bottom hemisphere. In other words, instead of the equator at the outer
edge, the opposite pole is now at the edge. If one wants the old
behavior, they can get it in the standard globe display by changing the
tilt to +/- 90 degrees.

**4. Polar globe hemisphere interface:** The hemisphere focused upon by
the polar globe chart (accessed via -XP, or the "Show Polar Globe"
command) is now controlled by the new "Globe Halves Focus On South
Hemisphere" checkbox in the Graphics Settings dialog (and also by the
-XP0 switch). Before this would be toggled by the Modify Display command
setting (-Xi switch).

**5. Ley lines interface:** Display of ley lines on the world map
display is now controlled by the 3D Houses setting (-c3 switch), when
before it would be toggled by the Modify Display command setting (-Xi
switch).

**6. Show border extended:** The Show Border command setting will now
affect globe displays, which used to always have their circular borders
displayed. The elliptical border around the Mollewide projection of the
world map is now also controlled by the show border setting, when before
it would be toggled by the Modify Display command setting (-Xi switch).

**7. Wheel decoration moved:** The spider web and moiré patterns drawn
in the corners of wheel charts are no longer unintuitively accessed by
having interpretations active (-I switch). The wheel chart decoration to
display is now accessed with the new -YXv command switch, and in the
Windows version in the new "Wheel Corners" groupbox in the Graphics
Settings dialog.

**8. -b0 behavior:** The -b0 switch which toggles whether displays are
to the nearest second, used to also affect the -b switch for ephemeris
files. This second effect no longer happens, which means -b0 and -b
should be considered completely separate switches. The old behavior
could cause confusion, because -b is on my default and -b0 is off by
default, which meant one attempting to turn on nearest seconds by doing
"-b0" would unintentionally turn ephemeris files off at the same time,
and would result in all positions becoming 0Aries.

**9. -B renamed:** The -B switch which sounds a system beep has been
replaced with -YB, since it's an obscure feature. The -B switch now
accesses the new transit graph chart.

**10. Globe Tilt commands renamed:** In the Windows version, the Globe
Tilt submenu "Increase" and "Decrease" commands have been renamed to
"Tilt North" and "Tilt South". That makes it clearer what each tilt
command actually does, and also aligns better with the new "Rotate West"
and "Rotate East" commands on the same menu.

BUG FIXES {#bug-fixes .Section}
=========

Here are bugs or other issues with version 6.20, all of which have been
corrected in this release:

**1. Daylight Autodetect bug:** The \"Autodetect\" Daylight Time setting
(as set with the -z0 command switch) is only implemented in the Windows
version. That\'s documented behavior and not a bug. However, what was a
problem is that if \"Autodetect\" was specified on any non-Windows
system, then instead of just defaulting to Daylight time being off, it
would instead produce an inaccurate \"now\" chart one day ahead.

**2. Whole houses bug:** The Whole system of houses would produce
malformed results when the sidereal zodiac is active. The sidereal
offset would be applied after the house cusps were computed in the
default tropical zodiac, which would move them away from sign
boundaries. The correct behavior is to apply the sidereal offset first,
and only then snap house cusps to the previous sign boundary.

**3. Transit influence bug:** In the Windows version, the "Transit To
Natal Influence" chart ignored the transit time setting in the Transits
dialog, and used the time of natal chart. That could be seen by doing a
transit to natal influence chart with both the natal and transiting
times set to the same date, and noticing that all planets are doing an
exact return with a 0 degree orb, regardless of the transit time.

**4. Composite transit bug:** Transit times to a chart with no time or
space (such as a composite chart) would clobber the chart positions of
the chart being transited to. As a result, the next chart refresh (such
as redrawing the screen in the Windows version) would replace the
expected chart with different positions.

**5. Synastry interpretation glitch:** Interpretation of synastry charts
would incorrectly label the North Node object as "North North Node".

**6. Rulership restriction limitation:** Standard rulerships would
always influence the power numbers in the -j switch influence chart (and
the -7 switch Ray chart that uses the same influences), even if standard
rulerships were restricted. Restricting standard rulerships will now
prevent them from contributing to power numbers in any way, similar to
how restricting esoteric and Hierarchical rulerships behave.

**7. Globe display glitch:** Creating a bitmap showing the globe and
with the 3D houses setting on would have a bunch of extraneous green
dots on the left edge of the bitmap.

**8. Dispositor display glitch:** The graphic dispositor chart (-j -X
switch combination) would draw the center boundary walls one extra pixel
off the bottom and right edges.

LICENSE {#license .Section}
=======

IMPORTANT NOTICE: Astrolog and all chart display routines and anything
not enumerated below used in this program are Copyright (C) 1991-2017 by
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
1989,1991,1993 by Astrodienst AG and Alois Treindl (<alois@astro.ch>).
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

O Astrolog 6.30 homepage:
<http://www.magitech.com/astrolog/astrolog.htm> O

\* \"Who am I, What am I? As I am, I am not. But as we are, I AM. And to
\*

O you my creation, My Perfect Love is your Perfect Freedom. And I will
be O

\* with you forever and ever, until the End, and then forever more.\" -
GOD \*

O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O
