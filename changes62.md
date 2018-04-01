AAAAA SSSSS TTTTTTT RRRRRR OOOOO L OOOOO GGGGG

A A S S T R R O O L O O G G

A A S T R R O O L O O G

AAAAAAA SSSSS T RRRRRR O O L O O G GGGG

A A S T R R O O L O O G G

A A S S T R R O O L O O G G

A A SSSSS T R R OOOOO LLLLLLL OOOOO GGGGG

\*\* VERSION 6.20 \*\*

Release notes for Astrolog version 6.20 (March 2017):

Happy Equinox and start of Aries everyone! :) This file describes the
freeware astrology software program Astrolog version 6.20 and the
additions and fixes made to it, over the previous version 6.10 which was
released exactly twelve months ago in March 2016. The main things in
this update are 3D houses, and a number of bug fixes.

NEW FEATURES {#new-features .Section}
============

Here are new additions to version 6.20 that weren\'t in previous
versions:

**1. 3D houses:** Astrolog supports 3D houses, which means that a
planet's house placement is determined by its ecliptic latitude in
addition to its zodiac longitude. To turn on 3D houses, use the -c3
switch, or in the Windows version select the "Setting / House Settings /
3D Houses" menu command. 3D houses is not a standard house system, since
it doesn't affect Astrolog's list of house cusp objects (which are still
determined by whatever house system is active). However, 3D houses does
determine which house an object is placed within.

In general, houses are based on the local horizon, in which the sky or
celestial sphere is divided into 12 equally sized \"orange wedges\",
with houses 1-6 below the horizon, and houses 7-12 above it. Similarly,
houses 10-3 are to the east of the meridian, and houses 4-9 are to the
west of the meridian. The signs of the zodiac are also a set of 12
\"orange wedges\", however they\'re oriented to a different coordinate
system, or more specifically are rotated to be aligned with the
ecliptic.

Campanus is the standard house system most similar to 3D houses, because
Campanus houses are defined by the intersection of the ecliptic with the
12 house \"orange wedges\". That means Campanus houses and 3D houses
give the same house placements for planets exactly on the ecliptic.
Since most planets are near the ecliptic, and it\'s only objects like
asteroids and especially stars that are located any significant distance
from it, Campanus is a rough approximation of 3D houses. Therefore,
Campanus is probably the best house system to use with the 3D houses
setting, since it ensures each house cusp object is placed in the right
3D house.

When 3D houses are active, the setting affects charts in the following
ways:

Standard list (-v switch): The indicating of what house a planet is
within is based on 3D houses, and not the house cusp positions of
whatever house system is active.

Graphic wheel (-v -X switches): The positioning of planets around the
wheel is based on its proportion through the house, and not its zodiac
position. Normally the wheel is "zodiac focused" and a planet is placed
based on its zodiac longitude, with its latitude (and how latitude
affects 3D house placement) ignored. When 3D houses are on, the wheel is
instead "house focused". That means positioning is based on the
proportion a planet is through its house, e.g. a planet 1/5 of the way
through the 3rd house will be positioned 1/5 of the way through the 3rd
house in the wheel, regardless of the planet's zodiac longitude. The
result is planets seem to shift slightly, especially if their latitude
is different from 0.

Text local horizon (-Z switch): Positions will be displayed in prime
vertical mode (as with the -Z0 switch), because prime vertical
coordinates define houses, in which the azimuth or 0-360 degrees
(representing house positions 1-12) follows the prime vertical from the
horizon east point through the west point via the nadir. Similarly, the
altitude or -90 to +90 degrees ranges from the north to south points on
the local horizon. In addition, instead of a 0-360 degree number, the
azimuth will be expressed as the house position 1-12, along with the
percentage the object is through the house from 0-30 degrees.

Graphic local horizon (-Z -X switches): Both versions of the graphic
local horizon chart will have added to it an overlay of dark green lines
showing the 3D houses (with each house labeled 1-12), and dark blue
lines showing the signs (with each sign labeled with its glyph). These
two sets of overlapping "orange wedges" can make it clear how 3D houses
differ from house determination by zodiac longitude only.

Graphic solar system orbit (-S -X switches): Planets will be drawn on a
logarithmic scale, resulting in planetary orbits roughly equally spaced.
One issue with the normal chart is that unless one is really zoomed in,
the inner planets are crammed together and harder to see.

Graphic globe (-XG switch): When "Modify Display" setting is active (-Xi
switch) which causes the planets to be drawn over the globe at their
zenith positions, the globe will have an overlay in dark green lines
showing the ecliptic and sign wedges. This applies to both the globe
showing the Earth's continents (which looks "down") and the celestial
sphere showing the astronomical constellations (which looks "up").

**2. Sripati houses:** Astrolog now supports the Sripati system of house
division. Sripati houses can be selected by passing 16 (or strings like
"sripati") to the -c house system selection switch. In the Windows
version there's a new "Setting / House System / Sripati" menu command.
The Sripati house system is a mixture between the Vedic and Porphyry
systems. It's computed the same as Porphyry, except that each cusp
starts in the middle of the previous house as defined by the Porphyry
system.

**3. Solar start of sign:** The new -10 switch is like the existing -1
solar chart switch, except instead of rotating house cusps so that the
Ascendant is the same as the Sun, it will rotate house cusps so that the
Ascendant is the same as the start of the Sun's sign. Similarly, the -20
switch acts like the -2 switch, and does the same for the Midheaven. In
the Windows version there's a new "Use Start Of Planet's Sign" checkbox
in the Solar Chart Setting section of the Calculation Settings dialog.

**4. Position rotation:** The new -Y1 switch is similar to the existing
-1 solar chart switch, except instead of rotating house cusps by an
offset so they're at a planet's position, it rotates all planets by an
offset so they're at the original position of some planet. This switch
takes two parameters specifying planets that represent an offset, such
that after shifting, the first planet is at the original position of the
second. If the switch is invoked as -Y10, it will instead rotate
everything so the first planet is at the start of the sign of the second
planet's original position. This option is considered turned off and
will have no effect if the two parameters are the same (and the "0" part
isn't active). This general feature allows generating certain types of
charts, such as esoteric astrology wheels.

**5. Rulership restrictions:** The new -YR7 switch controls what types
of rulerships and exaltations are shown in charts. It takes five
parameters, one for each of the five types of rulerships: Standard
rulerships, esoteric rulerships, Hierarchical rulerships, exaltations,
and Ray Rulerships. As with other restriction switches, a zero value
means show, and non-zero means restrict. In the Windows version, in the
Display Settings dialog there's a new "Rulership Restrictions" section
containing five checkboxes to cover these flags. The astrolog.as default
settings file contains a line for these variables, which is also
generated by the Save Settings command in the Windows version. Rulership
restrictions will affect what's shown in the standard -v chart list,
what's shown in the -7 esoteric chart, and also what set of rulerships
is used in the graphic -J switch dispositor chart.

**6. Midpoint objects:** The new -Fm switch will force an object's
position to always be the midpoint between two other objects. Note all
-F switch forcings are applied in object index order, so it's possible
to have midpoints involving other midpoints, as long as the more complex
midpoints have higher indexes.

**7. Smart export:** The new -YO switch tells Astrolog to do the "smart"
thing when exporting charts to other formats. This setting has two
effects: (1) When printing, if the chart background is black (which it
is by default) then the program will automatically reverse it to white
when printing. That avoids the problem of printing and getting a mostly
black piece of paper, which wastes ink. (2) When saving text charts or
copying them to the clipboard, Ansi color will automatically be
temporarily turned off. That avoids getting Ansi escape sequence
characters in the text, which in most cases isn't wanted because the
escape sequences aren't parsed in most contexts. In the Windows version
in the Display Settings dialog there's a new "Export Text And Print In
Intuitive Manner" checkbox for this setting.

**8. Different wheel settings:** The new -M2, -M3, and -M4 switches
allow different calculation settings to be used for different rings in a
bi-wheel, tri-wheel, or quad-wheel chart. The switches take 2, 3, or 4
string parameters respectively, and each string is a command line that
gets automatically applied before calculating the planet positions for
that ring. If the switch is invoked as -M20, -M30, or -M40 with an extra
"0", then it takes one final parameter for a command line to run at the
very end, which can restore settings to default values for subsequent
use of the program. With this feature you can do things such as have a
heliocentric chart and a geocentric chart displayed at the same time.
You can even do things such as (assuming all calculation methods are
compiled into the program) have one wheel with planets computed via
Swiss Ephemeris, another by the old Placalc ephemeris, and a third by
the very old Matrix formulas, to compare their accuracy side by side.

**9. Different wheel graphics:** The new -XM2, -XM3, and -XM4 switches
allow different graphics to be used for different rings in a bi-wheel,
tri-wheel, or quad-wheel chart. The switches take 2, 3, or 4 string
parameters respectively, and each string is a command line that gets
automatically applied before drawing that ring. For example, you can do
things such as have rings with different glyphs, different character
scales, or different restrictions.

**10. Windows rounding:** In the Windows version, the Display Settings
dialog has a new checkbox "Round Positions To Nearest Unit Instead Of
Crop". That covers the -Yr switch setting which determines whether a
position like 29Ari59.9' should be truncated to 29Ari59' or rounded up
to 0Tau00.

**11. Windows autosave bitmap:** The new -Wo switch causes the program
to automatically save a bitmap of the current graphics screen to the
bitmap file "astrolog.bmp", whenever the screen is updated. This
specialized feature allows external programs to get the current state of
Astrolog's screen, which can be used for scenarios such as creating the
following video: <https://www.youtube.com/watch?v=euxwoyekZow>

\--

Here\'s a summary of the 8 new command switches in Astrolog 6.20 that
weren\'t in previous versions:

**-M\[2-4\]\[0\] \<strings\>:** Define macro(s) to run when chart
calculated.

**-c3:** Place in houses using latitude as well as zodiac position.

**-Fm \<objnum\> \<obj1\> \<obj2\>:** Force object\'s position to
midpoint.

**-XM\[2-4\]\[0\] \<strings\>:** Define macro(s) to run when chart
drawn.

**-Wo:** Continually autosave graphics screen to bitmap file.

**-YO:** Automatically adjust settings when exporting and printing.

**-Y1\[0\] \<obj1\> \<obj2\>:** Rotate planets so one is at other\'s
position.

**-YR7 \<ruler\> \<exalt\> \<eso\> \<hier\> \<ray\>:** Set rulership
restrictions.

Here\'s a summary of the 2 new menu commands in the Windows version of
Astrolog 6.20 that weren\'t in previous versions:

Setting - House System - Sripati\
Setting - House Settings - 3D Houses

EXTENDED AND IMPROVED FEATURES {#extended-and-improved-features .Section}
==============================

A list of improvements to existing features in Astrolog 6.20, such as
new things you can now do with old features that you couldn't do before,
or ways existing features work better than before:

**1. Aspect restrictions:** Astrolog fully supports aspect restrictions,
or the ability to turn on or off aspects independently. Before, Astrolog
only had a number indicating the count of aspects to use, and aspects
within that count were "restricted" by setting their orb negative (which
requires manually restoring the orb to "unrestrict" it). Now, each
aspect has a flag indicating whether it should be restricted, and these
flags are automatically linked with the aspect count setting. In other
words, increasing the aspect count (whether through the -A switch or the
Aspects To Consider field in the Display Settings dialog) will
automatically unrestrict uncovered aspects, and decreasing it will
automatically restrict covered aspects. Also, manually restricting or
unrestricting aspects (whether through the -RA switch or the checkboxes
in the Aspect Settings dialog) will automatically adjust the aspect
count to be the highest unrestricted aspect.

**2. Automatic category restrictions:** Cusp objects, Uranians, and
fixed stars are normally turned on and off with the Include Cusps,
Include Uranians, and Include Stars commands (-C -u, and -U switches).
These category settings are now fully integrated with object
restrictions. In other words, restricting all objects in a category will
turn the category as a whole off, and unrestricting an object within a
category will turn the category on. Before, one could unrestrict objects
with command switches and not have them appear in charts (because their
category wasn't on), or turn on categories and have nothing appear
(because all objects within it were restricted), which could be
confusing.

**3. Star velocities:** Velocities are now displayed for fixed stars in
the standard listing (-v switch), instead of such objects having that
column blanked out with underscore characters.

**4. Relative velocity extension:** The velocities displayed relative to
average speed setting (-v0 switch) was only available when the old
Matrix formulas were active. Now it will affect Swiss Ephemeris and
Placalc generated positions as well.

**5. Tri-wheel aspects:** Aspect lines will be shown in the middle of
tri-wheels and quad-wheels. These lines will show aspects between
planets in any two different pairs of charts present. In other words, a
bi-wheel shows aspects between chart \#1 and chart \#2, and a tri-wheel
shows aspects between chart \#1 and \#2, \#1 and \#3, and \#2 and \#3.

**6. Graphic grid seconds:** The graphic aspect/midpoint grids will show
the nearest arc second of orbs and midpoints when the Print Nearest
Second setting (-b0 switch) is on, and when the character scale factor
is 400 (so that there's enough room to include seconds).

**7. Astro-graph restrictions:** The Rising And Setting Restrictions
section in the Display Settings dialog (-YRZ switch) now affects the
graphic astro-graph chart. These four restrictions will control whether
the Ascendant, Midheaven, Descendant, and Nadir lines are drawn.

**8. Astro-graph seconds:** The text mode astro-graph chart (-L switch)
will show lines to the nearest second (instead of just nearest degree)
if the Print Nearest Second setting (-b0 switch) is active.

**9. Astro-graph crossing extended:** The text mode astro-graph chart
that shows latitude crossings (-L0 switch) will now range between +90 to
-90 degrees latitude, instead of just +80 to -80. More specifically
stepping will include every degree before 90, so the default step rate
of 5 will reach 85 degrees.

**10. Graphic ephemeris lines:** The yearly ephemeris charts (which
include both the standard -Ey switch ephemeris, as well as the -7 switch
esoteric Ray ephemeris) will have a horizontal line drawn across the
chart indicating the day in question, if the show glyph labels setting
(-Xl switch) is active. That makes it easier to see where in a month the
chart time actually is.

**11. Esoteric dispositors:** The graphic dispositor chart (-J -X switch
combination) normally graphs standard rulership dispositors. However, if
standard rulerships are restricted and esoteric rulerships aren't, then
it will instead graph esoteric rulerships. If esoteric rulerships are
graphed, then the chart will include Earth and Vulcan (which means
Vulcan should be unrestricted so its position isn't 0Aries), for 12
planets instead of 10 in the chart. If both standard and esoteric
rulerships are restricted and Hierarchical rulerships aren't, then this
will instead graph Hierarchical rulerships.

**12. Esoteric rulership influence:** The influence chart (-j switch)
and the esoteric Ray chart (-7 switch) will consider the influence of
esoteric and Hierarchical rulers, as long as such rulerships are
unrestricted (via the new -YR7 switch setting).

**13. More colored text:** In the graphic wheel sidebar, the element and
hemisphere counts will now be colored appropriately, based on the
element colors. In the standard text listing (-v switch) the hemisphere
count text will also be colored appropriately.

**14. Planet info extended:** The List Planet Info command (-HS switch)
will include in its list of planets the lunar nodes and Lilith, along
with Vulcan and the Uranians (as long as they're unrestricted), since
they have definite orbital periods and locations in space.

**15. Windows aspect orb precision:** Aspect orbs in the Windows
"Setting / Aspect Settings" menu command can display aspect orbs with up
to six digits of precision to the right of the decimal point. Before
their display was limited to two digits to the right of the decimal. Orb
values could be entered with higher precision in the dialog, or
specified with higher prevision via the -YAo switch (which is in the
astrolog.as settings file), but opening and applying the dialog would
truncate orbs back to two digits. This improvement doesn't affect most
users, because most have their orbs set to whole degrees.

**16. Decimal location:** The 360 degrees display format (-sd switch)
now affects the display of longitude and latitude locations. Before it
only affected zodiac locations.

**17. Centimeter paper:** The "Horizontal and Vertical PostScript Paper
Size" fields (-YXp0 switch) has been updated to allow sizes to be
specified in centimeters instead of just inches. If the parameter ends
in "cm" then it will be parsed as centimeters, and if it ends in "in"
then it will be parsed as inches. If there's no units, then it will be
parsed based on the "Display Lengths in Metric Instead Of Imperial
Format" setting (-Yv switch). The "Horizontal and Vertical PostScript
Paper Size" fields in the Display Settings dialog will be shown in the
appropriate units based on that setting.

**18. Chart slot virtual files:** The new virtual filenames "\_\_1"
through "\_\_4" represent the current contents of the four chart slots.
They can be used to copy chart date/time fields. For example, the
command switch "-i2 \_\_4" will copy the contents of chart \#4 to chart
\#2.

**19. Local horizon accuracy:** The local horizon chart (-Z switch) is
slightly more accurate, because Astrolog now uses Swiss Ephemeris when
turned on to compute the obliquity of the ecliptic. This may update
local horizon positions by up to 10 arc seconds.

**20. Graphics scale improved:** The Character Scale and Text Scale
fields in the Graphics Settings dialog now have dropdowns allowing one
to select from the four valid percentages 100 through 400.

PROGRAM CHANGES {#program-changes .Section}
===============

A few changes that aren\'t feature additions or bug fixes have been made
to Astrolog 6.20, which means certain old assumptions are no longer
valid. Most can be considered improvements, but they still change
existing behavior. A list of these (which aren\'t useful to be aware of
unless you have used previous versions of the program) follows:

**1. Calculation method dropdown:** In the Windows version, the "Use
Ephemeris Files" checkbox in the Calculation Settings dialog has been
removed. It's been replaced with a "Calculation Method" dropdown, which
(depending on what's been compiled into the program) will allow one to
calculate planet positions by one of four methods: Swiss Ephemeris, old
and less accurate Placalc Ephemeris, very old and much less accurate
Matrix formulas, and None. When None is selected most objects will be
placed at 0Aries, which of course isn't useful except for obscure
testing scenarios.

**2. Esoteric listing removed:** The -v7 switch to include esoteric
rulerships in the standard text list has been removed. The rulerships
present in the standard list and other charts are now controlled in a
more general way by the new -YR7 switch (described earlier).

**3. Continual Daylight autodetect:** The value "Autodetect" when
entered in the "Daylight?" field in the Windows Default Chart Info
dialog (-z0 switch) is now a separate and persistent setting. Whenever a
chart for "now" is computed, Windows will determine whether Daylight
Saving Time is in effect for the current moment. For example, an
animation continually updating to the current moment will change to or
from Daylight Time at the second the annual switchovers take place.
Before, "Autodetect" was just a macro which translated to on or off
based on whether Daylight Time was in effect at the time the parameter
was evaluated, and thereafter the parameter would remain fixed on or
off. That also meant running the "Save Settings" command in the Windows
version would never save "Autodetect" to the astrolog.as default
settings file.

**4. Horizon Sky adjusted:** The local horizon graphics chart with
circular sky projection (-Z0 -X switches) has been adjusted so that all
points below the horizon have been compressed to fit between the horizon
circle and the outer boundary square, allowing all points in the sky to
be visible. Before, everything was rendered as a simple radius from the
zenith at the center, with the nadir at the corners of the square, which
meant certain areas near the nadir at the edges of the screen would be
clipped and not visible in the chart.

**5. Decimal parsing:** When parsing zodiac positions and locations,
Astrolog will understand decimal degrees, minutes, and seconds, if
there's a decimal point in the rightmost field. For example, 26Sco47.5
and 26Sco47'30" will be treated the same. Before, Astrolog treated and
parsed all delimiters (whether ":" or ".") the same, which meant that
locations always had to be specified in degrees/minutes/seconds format
(instead of fractional degrees, or degrees and fractional minutes, which
are allowed now).

**6. String parsing validation:** When a text string representing a
planet or other item is parsed, the first three characters must match.
String parsing now ensures any characters present beyond the first three
also match. Before, the string "Satxyz" would match Saturn, however now
it must be a proper substring of "Saturn".

**7. Obscure Settings renamed:** In the Windows version, the "Setting /
Obscure Settings" command has been renamed to "Display Settings". This
dialog now focuses upon general settings that change chart displays,
such as format modes or restrictions. This dialog no longer tries to
cover "obscure" or less common settings, which would require one to
remember which settings are common versus uncommon.

**8. Windows dialog fields moved:** In the Windows version, dialog
fields in the Calculation Settings, Display Settings (formerly Obscure
Settings), and Graphics Settings have been moved among each other. These
moves better reflect that Calculation Settings is reserved for settings
which affect zodiac positions of objects (such as sidereal zodiac),
Display Settings is reserved for settings which affect cosmetic changes
in charts (such as number of aspects to show), and Graphics Settings is
reserved for settings which affect graphics bitmaps (such as glyphs to
use).

"Compute True Node Instead Of Mean Node" (-Yn switch) has moved to
Calculation Settings from Obscure Settings.\
"Cusp Objects Are Positions Instead Of Angles" (-YC switch) has moved to
Calculation Settings from Obscure Settings.\
"Display Format" (-s switch) has moved to Display Settings from
Calculation Settings.\
"Aspects To Consider" (-A switch) has moved to Display Settings from
Calculation Settings.\
"Text Columns" (-I switch) has moved to Display Settings from
Calculation Settings.\
"Number Of Cells In Graphics Aspect Grid" (-YXg switch) has moved to
Graphics Settings from Obscure Settings.\
Glyph groupboxes (-YXG switch) have moved to Graphics Settings from
Obscure Settings.

BUG FIXES {#bug-fixes .Section}
=========

Here are bugs or other issues with version 6.10, all of which have been
corrected in this release:

**1. Graphics Settings error:** In the Windows version, the Graphics
Settings dialog would always display an error and never allow new
settings to be applied. This was fixed in updated downloads of version
6.10, but was still present in the initial download made available.

**2. Show Constellations crash:** In the precompiled Windows version,
the Show Constellations command would crash. The actual chart display
would crash, even if invoked by manually specifying the -HF switch in
the standard Windows or Windows command line interface versions.

**3. Porphyry houses broken:** Selecting the Porphyry system of houses
would actually compute and show Placidus positions (even though Porphyry
would be displayed as the system). This bug was only present when Swiss
Ephemeris was active.

**4. Sidereal inaccuracy:** Planet positions (but not house cusps) in
the sidereal zodiac would be displayed too far forward by about 12 arc
seconds, regardless of the ayanamsa or zodiac offset.

**5. Sidereal velocity inaccuracy:** Planet velocities in the sidereal
zodiac were slightly inaccurate, because they were the same as tropical
zodiac velocities. Sidereal zodiac velocities need to be slightly lower,
to align the fact that sidereal zodiac positions are all precessing
backwards very slowly.

**6. Graphic aspect grid orb bug:** Orbs in the graphics aspect grid
would always be shown as negative (meaning their angle is shown as too
small, even when they were actually too large) and applying (even when
they were actually separating).

**7. House placement bug:** In the Campanus, Regiomontanus, and
Topocentric house systems, at high latitudes their houses are sometimes
arranged in reverse order. In such cases, Astrolog wouldn't place
objects in houses correctly, and would always say they're in the first
house.

**8. House system bug:** The astro-graph and local horizon charts would
produce results 180 degrees opposite the expected result, if the house
system were set to Campanus, Regiomontanus, or Topocentric, and the
location was in the polar zone such that Swiss Ephemeris would flip the
MC 180 degrees. Astrolog now distinguishes between the meridian (which
never changes) and the MC (which may be flipped).

**9. Object font display:** Display of objects using the Astro font in
metafile and PostScript files would show the wrong glyphs, specifically
offset by one for later objects. For example, the 3rd cusp would show
the glyph for the IC, and the 12th cusp would show the glyph for the
South Node.

**10. Save Settings bug:** In the Windows version, the Save Settings
command would sometimes save the default house system incorrectly.
Saving with Equal (MC) active would actually save Equal (Asc), and
saving Pullen (Sinusoidal Delta) would actually save Pullen (Sinusoidal
Ratio).

**11. Missing sidebar:** The sidebar displayed to the right of graphic
wheel charts would be missing if Astrolog was launched without loading
the astrolog.as default settings file. Specifically, the -XS switch
character scale feature was set at compile time to the illegal value of
0, which would result in a zero sized sidebar. Astrolog depended upon
the astrolog.as default settings file to set the -XS switch to a valid
scale.

**12. Tri-wheel limitation:** Chart position files containing raw
positions and not date/time (as generated with the -o0 switch or the
Windows "Save Chart Positions" command) wouldn't work when loaded into
chart slots \#3 and \#4 for display in tri-wheels and quad-wheels.

**13. Transit interpretation omission:** Transit to natal charts (-t and
-T switches) wouldn't show interpretations for the Ascendant and other
angles, or Uranians.

**14. Cusp interpretation omission:** The standard list text chart (-v
switch) wouldn't show interpretations for the Ascendant and other
angles, even such objects were unrestricted.

**15. Custom aspect interpretation limitation:** Changing aspect
interpretation text (-YIA switch) wouldn't allow updating aspects beyond
the Biquintile (aspect index \#11).

**16. Midpoint interpretation omission:** The standard and relationship
midpoint chart (-m0 switch) wouldn't show summary numbers at the bottom
if interpretations were active.

**17. Moon velocity inaccuracy:** When relative velocities were active
(-v0 switch), then the Moon and Moon's Nodes would have bad velocities
that weren't relative.

**18. Sun velocity omission:** When the central planet was something
other than the Earth (geocentric) or Sun (heliocentric), then the
velocity of the Sun would be 0.

**19. Earth omission:** Earth (or whatever the central planet is) would
always have a latitude of 0.0, when really it should be the negative of
the Sun's latitude (which although always very close to zero, does
slightly deviate from it).

**20. Vulcan glitch:** When Swiss Ephemeris was turned off, Vulcan would
have a random garbage position. Vulcan requires Swiss Ephemeris to be
active, so when Swiss Ephemeris is turned off, Vulcan's position should
be 0Aries.

**21. Astro-graph crossing display:** The text mode astro-graph chart
that includes latitude crossings (-L0 switch) would show numerous
crossings of the North and South Node Ascendant and Descendant lines,
because the nodes are directly opposite each other, meaning their
Ascendant and Descendant lines are overlapping, resulting in numerous
subtle crossings. These two objects are now special cased to not
interact with each other.

**22. Astro-graph graphic display:** In the graphic astro-graph chart,
extra vertical hatch marks indicating longitude would be drawn one pixel
off the right edge of the chart.

**23. Gauquelin behavior:** The Gauquelin sector text and graphics
charts (-l switch) would automatically restrict objects that couldn't be
displayed in the chart due to their having too high latitude, and leave
them restricted after the chart is displayed. Restrictions are no longer
permanently changed by this chart.

**24. Smart cusps bug:** When the "Ignore Insignificant House Cusps
Aspects" setting (-YC switch) was active, simultaneous aspects to the
Sun and Earth would always be prevented, which is by design. However,
this would also take place even when Earth isn't the central planet,
which means the Sun isn't always opposite it. The result would be
expected aspects to the Sun being omitted.

**25. Smart cusps limitation:** Transit searches could display
simultaneous aspects to objects that are always opposite each other,
such as the North and South Nodes, and the Sun and Earth. Such
simultaneous events are now prevented with the "Ignore Insignificant
House Cusp Aspects" setting (-YC switch).

**26. Southern hemisphere bug:** Transit charts would always display the
Sun entering Capricorn as the Winter Solstice, when it's really the
Summer Solstice for chart locations in the southern hemisphere. The
Summer Solstice and the Spring and Autumn Equinoxes also needed to be
reversed for such locations.

**27. Previous chart inaccuracy:** Doing a transit display that shows
the time of a transit, and then selecting the "previous" chart via "-i
set" on the command line or pressing the "Previous" button in the Set
Chart Info dialog, would truncate the time to the minute and not include
the seconds part of the transit event.

**28. Windows Solar Chart glitch:** In the Windows version, toggling the
Solar Chart setting in the Calculation Settings dialog wouldn't also
toggle the check mark by the House Settings / Solar Chart menu item.

**29. Windows switch crash:** Passing the -Xb save as bitmap switch to
the Windows version (either on the command line or through the Enter
Command Line menu command) would crash.

**30. Compiler warning fix:** Compiling Astrolog on certain Unix systems
would result in a number of warnings saying something similar to
"deprecated conversion from string constant to char\*". These warnings
have been suppressed by adding "-Wno-write-strings" to the "CZZFLAGS"
setting in the Unix Makefile.

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

O Astrolog 6.20 homepage:
<http://www.magitech.com/astrolog/astrolog.htm> O

\* \"Who am I, What am I? As I am, I am not. But as we are, I AM. And to
\*

O you my creation, My Perfect Love is your Perfect Freedom. And I will
be O

\* with you forever and ever, until the End, and then forever more.\" -
GOD \*

O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O
