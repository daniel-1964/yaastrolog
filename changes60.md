AAAAA SSSSS TTTTTTT RRRRRR OOOOO L OOOOO GGGGG

A A S S T R R O O L O O G G

A A S T R R O O L O O G

AAAAAAA SSSSS T RRRRRR O O L O O G GGGG

A A S T R R O O L O O G G

A A S S T R R O O L O O G G

A A SSSSS T R R OOOOO LLLLLLL OOOOO GGGGG

\*\* VERSION 6.00 \*\*

Release notes for Astrolog version 6.00 (December 2015):

Happy Winter Solstice everyone! This file describes the freeware
astrology software program Astrolog version 6.00 and the additions and
fixes made to it, over the previous version 5.40 which was released back
in December 1998. The main things in this update are the more accurate
Swiss Ephemeris, features supporting esoteric astrology, and a good
number of bug fixes.

NEW FEATURES {#new-features .Section}
============

Here are new additions to version 6.00 that weren\'t in previous
versions:

**1. Swiss Ephemeris:** Astrolog 6.00 now uses the Swiss Ephemeris,
which is more accurate and covers more years than the Placalc ephemeris
it used before. The Swiss Ephemeris is a compressed version of NASA's
Jet Propulsion Laboratory (JPL) DE431 ephemeris, and reproduces it with
0.001 arc seconds precision. The Uranian objects in Astrolog are
computed using the Swiss Ephemeris too, and are much more accurate than
the Matrix routines used before. Their zodiac positions may vary up to
10 arc minutes from before, and their latitudes (which were always fixed
at 0 before) may vary by up to 59 arc minutes.

Ephemeris files: The ephemeris files used by the Swiss Ephemeris cover
10800 years. Three different files cover each date range, which are
named "se\*.se1", in which "se" stands for "Swiss Ephemeris". The files
"sepl\*.se1" cover the planets ("pl" stands for planets), the files
"semo\*.se1" cover the Moon ("mo" stands for Moon), and the files
"seas\*.se1" cover the asteroids and Chiron ("as" stands for asteroids).
The last three digits in an ephemeris filename indicate the date range
covered, which consists of six centuries starting with the number
indicated, in which "\_" means a positive year, and "m" means minus or
negative years BC. Note since there is no year 0 (1 BC is followed by 1
AD) negative ephemeris file ranges are offset by 1 year. The three files
"se\*\_18.se1" cover the years 1800 through 2400 AD, which is good for
most modern purposes and take up 2012K of space. These three files are
included in the standard setup of Astrolog. For users who want to cover
more years, the complete set of files is available online. The following
is a list of the years covered by each ephemeris file:

Files seplm54.se1 / semom54.se1 / seasm54.se1 cover -5401 BC - -4801 BC.

Files seplm48.se1 / semom48.se1 / seasm48.se1 cover -4801 BC - -4201 BC.

Files seplm42.se1 / semom42.se1 / seasm42.se1 cover -4201 BC - -3601 BC.

Files seplm36.se1 / semom36.se1 / seasm36.se1 cover -3601 BC - -3001 BC.

Files seplm30.se1 / semom30.se1 / seasm30.se1 cover -3001 BC - -2401 BC.

Files seplm24.se1 / semom24.se1 / seasm24.se1 cover -2401 BC - -1801 BC.

Files seplm18.se1 / semom18.se1 / seasm18.se1 cover -1801 BC - -1201 BC.

Files seplm12.se1 / semom12.se1 / seasm12.se1 cover -1201 BC - -601 BC.

Files seplm06.se1 / semom06.se1 / seasm06.se1 cover -601 BC - -1 BC.

Files sepl\_00.se1 / semo\_00.se1 / seas\_00.se1 cover -1 BC - 600 AD.

Files sepl\_06.se1 / semo\_06.se1 / seas\_06.se1 cover 600 AD - 1200 AD.

Files sepl\_12.se1 / semo\_12.se1 / seas\_12.se1 cover 1200 AD - 1800
AD.

Files sepl\_18.se1 / semo\_18.se1 / seas\_18.se1 cover 1800 AD - 2400
AD. \*

Files sepl\_24.se1 / semo\_24.se1 / seas\_24.se1 cover 2400 AD - 3000
AD.

Files sepl\_30.se1 / semo\_30.se1 / seas\_30.se1 cover 3000 AD - 3600
AD.

Files sepl\_36.se1 / semo\_36.se1 / seas\_36.se1 cover 3600 AD - 4200
AD.

Files sepl\_42.se1 / semo\_42.se1 / seas\_42.se1 cover 4200 AD - 4800
AD.

Files sepl\_48.se1 / semo\_48.se1 / seas\_48.se1 cover 4800 AD - 5400
AD.

If a chart is cast for a date without the required ephemeris files, an
error message will be displayed (only one error message per chart, to
avoid a long string of errors when doing charts like transit searches
and ephemeris tables). Then, the program will fall back to using a less
accurate internal ephemeris and formulas by Steve Moshier. The Moshier
ephemeris is based on the JPL DE404 ephemeris, which covers 6000 years
(-3000 BC to 3000 AD), and computes planets to within 0.1 arc seconds,
and the Moon within 3 arc seconds. Note that the position of Chiron is
only available for 3975 years at most, from Jan 1, 675 through Dec 31,
4649, regardless of ephemeris files available. That's because outside
those dates Chiron's orbit becomes impossible to accurately determine,
due to close encounters with Saturn. Attempting to cast a chart for
Chiron outside of this range with Swiss Ephemeris will display an error
and place it at 0Aries.

Old ephemeris: The less accurate Placalc ephemeris that Astrolog used to
use is still available with the new -bp switch. There's little reason
for the average user to ever need or want to do this. The old ephemeris
routines are still available for obscure situations such as comparing
accuracy of different calculation methods, testing against previous
version output with known positions, or a need to run Astrolog in
limited disk space environments. (The Placalc ephemeris is 4.8 megabytes
total or 57K per century, while Swiss Ephemeris is 37.1 megabytes or
344K per century.)

Old formulas: When no ephemeris files are available for a given date,
previous versions of Astrolog would fall back to very old formulas based
on those created by Matrix Software. The new -bm switch allows those
formulas to still be used. When this setting is off, the Matrix formulas
will never be used no matter what, in which case the lack of ephemeris
files will result in planets being at 0Aries. That may be desired
behavior, to ensure only the best Swiss Ephemeris positions are ever in
place. Many may prefer the error condition of no positions, to
relatively inaccurate and potentially misleading positions. Again
there's little reason for the average user to ever need or want to turn
this on, although some features like defining your own orbital elements
(-YE switch) make use of the simple Matrix formulas.

**2. Vulcan object:** Astrolog now supports the position of Vulcan, a
hypothetical planet located inside Mercury's orbit. Vulcan is
significant in esoteric astrology, and is computed according to the
research of L.H. Weston. Vulcan is object \#34 in Astrolog, and is added
to the Uranians group of objects (which are also hypothetical planets).
That means commands like "Include Uranians" (-u switch) will now include
Vulcan along with the actual Uranians. In the Windows version, Vulcan
appears in the More Object Settings dialog and the Restrictions dialogs.
Computing Vulcan requires the Swiss Ephemeris routines to be active, and
it will be placed at 0Aries otherwise. The orbital formula for Vulcan is
defined in the file "seorbel.txt" in the Astrolog install directory, and
like the larger ephemeris files that text file needs to be present in
order for Vulcan to be computed. Note the insertion of Vulcan means the
other Uranians and fixed stars have increased their index numbers by
one.

**3. South Node object:** Astrolog contains a new object position for
the South Node of the Moon, which is of course always located opposite
the North Node. The South Node is object \#17, inserted right after the
North Node. In the Windows version, the South Node appears in the Object
Settings dialog and the Restrictions dialogs. Note the insertion of the
South Node means other minor objects, the house cusps objects, the
Uranians, and the fixed stars have increased their index numbers by one.

**4. Earth object:** Astrolog supports the position of Earth in the same
way it does other objects. Earth is object \#0, placed before all other
objects so nothing has its index numbers changed. In the Windows
version, the Earth appears in the Object Settings dialog and the
Restrictions dialogs. This addition means that many settings and command
switches in the program that take object indexes will accept numbers 0
and above, instead of only 1 and above as before. Note because Earth is
its own official object, heliocentric charts will no longer
automatically replace the Sun with the Earth, and so Earth needs to be
unrestricted to see it. If Earth is unrestricted in a geocentric chart,
it will be the heliocentric position of the Earth (i.e. directly
opposite the Sun). Similar logic will be applied whenever the central
object is unrestricted (with an unrestricted Sun in a heliocentric chart
being the geocentric position of the Earth, i.e. opposite the Earth).

**5. Esoteric chart:** A chart for esoteric astrology is available with
the new -7 command switch, and in the Windows version (when text mode is
active) with the new "Chart / Esoteric" command. It will list planets,
showing the planet's Ray, the planet's position and the Ray(s) of its
zodiac sign, and rulership information about the planet's zodiac
position and house position. That includes whether the planet
exoterically rules or is debilitated in the sign (indicated with "R" or
"d" characters), whether the planet esoterically rules or is debilitated
in the sign ("S" or "s" characters), whether the planet Hierarchically
rules or is debilitated in the sign ("H" or "h" characters), whether the
planet exalts or falls in the sign ("X" or "f" characters), and finally
whether the planet Ray rules or is Ray debilitated in the sign i.e.
whether the planet's Ray is the same as one of its sign's Rays ("Y" or
"z" characters). Finally the power of each planet is listed, based on
its inherent strength, positioning, and aspects, which is computed in
the same way as in the -j switch influence chart.

The esoteric chart also lists the seven Rays, showing the count of
planetary sign positionings that are associated with that Ray, the total
power of those planets, and the rank of each Ray's total power and the
percentage covered by that Ray. This can be used to see which Rays are
most influential in a chart. The same counts and powers are repeated,
however this time a sign associated with multiple Rays only contributes
proportional slices of power. By default, each Ray is associated with
three signs, so for balanced Ray coverage that gives each Ray an equal
potential for power, the first "count" values are preferred. However,
some signs are associated with one Ray, while others are with two or
three, which means certain signs have triple potential to contribute
power, so for balanced planet coverage that gives each sign an equal
potential for power, the second "slice" values are preferred.

**6. Esoteric Ray graphic ephemeris:** A graphical ephemeris of esoteric
Ray influences is available by combining the -7 with the -X command
switch, and in the Windows version by selecting the "Chart / Esoteric"
command (when graphics mode is active). This chart is effectively the
Ray power values in the text mode chart graphed over time. The seven
Rays and their powers (and average power) are listed on the horizontal
axis, and time on the vertical axis. If "Graphics / Modify Chart" is
set, this chart will graph an entire year instead of just a month. If
"Graphics / Modify Display" is set, it will graph the "slice" power of
each Ray instead of the "count" power.

Ray column width: The new -YX7 \<num\> switch specifies the width in
influence units of each Ray's column in the esoteric graphic ephemeris.
For example, given "-YX7 600", then a Ray influence value of 400 will
fill 2/3 of the column.

**7. Ray info:** Information about the seven Rays used in esoteric
astrology is available with the new -H7 command switch, and in the
Windows version with the new "Help / List Rays" command. Each Ray is
listed, along with its name in esotericism, and the aspect of will that
Ray covers. The signs associated with each Ray will be printed (by
default each Ray is associated with exactly three signs), and the
planets associated with each Ray. Finally is printed the "slice" value
of the Ray, which is the count of signs associated with that Ray, each
proportioned by the number of other Rays associated with that sign. For
example, Ray 5 is associated with Leo (along with Ray 1), Sagittarius
(along with Rays 4 and 6), and Aquarius (only Ray 5). Therefore Ray 5's
slice value is 1/2 + 1/3 + 1/1 = 1.83.

**8. Windows wallpaper:** The Windows version has three new menu
commands to save the current graphics chart as the Windows desktop
background. The "File / Save As Wallpaper / Stretch Bitmap" command will
save the chart, stretching or shrinking both its dimensions separately
to cover the background dimensions. The "File / Save As Wallpaper / Fit
Bitmap" command will stretch or shrink the bitmap to just fit within the
desktop while preserving proportion, so will leave space on the
horizontal or vertical edges if the proportions are different from the
background. The "File / Save As Wallpaper / Fill Bitmap" command will
stretch or shrink the bitmap to completely fill the desktop area while
preserving proportion, so will crop content on the horizontal or
vertical edges of the bitmap if its proportions are different from the
background. Note the "Fit" and "Fill" commands will only work on Windows
7 or later, which supports these styles of background.

**9. Windows setup:** Astrolog for Windows can do its own setup in many
respects. The new "Help / Setup / Program Group (User)" menu command
(and the new -WSg switch) will create a Windows program group for the
current user containing pointers to the Astrolog executable, the main
and update documentation files, and the Astrolog website. The "Help /
Setup / Program Group (All)" command (-WSG switch) will create the same
program group, but for all users. The "Help / Setup / Desktop Icon"
command (-WSd switch) will create a Windows desktop icon to launch
Astrolog. The "Help / Setup / File Extensions" command (-WSx switch)
will associate Astrolog with ".as" extension files in the Windows
registry. The "Help / Setup / Uninstall Extensions" command (-WSu
switch) undoes the effect of the previous command, and unassociates
Astrolog from ".as" extension files in the Windows registry, which is
useful for uninstall. Finally, the "-setup" switch is a convenience to
do the combination of "-WSg -WSd -WSx" all together. Note the last two
menu commands edit the Windows registry, which is protected on Vista and
newer versions of Windows, meaning the command may fail and display an
error message. Hence Astrolog may need to be run as Administrator in
order for the program to have permission to change the registry.

**10. Windows website:** The new "Help / Documentation / Open Website
Mirror" menu command will open the Astrolog website mirror location at
magitech.com in the default browser.

**11. Windows license:** The new "Help / Documentation / Open License"
menu command launches the default browser and has it automatically open
the Daedalus license file "license.htm", displaying legal information on
how you may use the program. Astrolog now uses the GNU General Public
License (GPL). There are no major changes in the rights intended with
respect to using Astrolog, however the GPL expresses this in a more
clear and standard manner.

**12. Esoteric Pluto glyph:** An alternate glyph is supported for Pluto,
an upward pointing arrow often used by esoteric astrologers. One may
select the new radio button "Esoteric" in the "Pluto Glyph" section of
the Obscure Settings dialog, or pass the digit 3 to the 10's place in
the -YXG command switch.

**13. Object colors:** Colors of planets and other objects can be set
with the new -YkO command switch, which takes at least three parameters.
The first two parameters are the low and high object indexes to change.
The next parameters are the new colors for objects within that range. If
a color is "Element" (or the number 16), that means use the element
color of the sign the planet rules (which is the default color setting
for the main planets and house cusps). If a color is "Ray" (or the
number 17), that means use the color of the Ray associated with the
planet. Note that signs will use the colors of the house cusp objects
corresponding to them, e.g. the Pisces glyph and zodiac positions in
Pisces will be printed in the color of the 12th house cusp object.

**14. Ray colors:** Colors of esoteric Rays can be set with the new -Yk7
command switch, which takes at least three parameters. The first two
parameters are the low and high Ray numbers to change, ranging from 1 to
7. The next parameters are the new colors for the Rays within that
range.

**15. Object Rays:** The Ray associated with each planet can be
customized with the new -Y7O command switch. The first two parameters
are the low and high object indexes to change. The next parameters are
the new Rays for objects within those indexes, ranging from 1 to 7.

**16. Sign Rays:** The Rays associated with each zodiac sign can be
customized with the new -Y7C command switch. The first two parameters
are the low and high sign indexes to change. The next parameters are the
set of Rays for each sign within those indexes. Since a sign may be
associated with more than one Ray, each setting change may be multiple
digits, for example "-Y7C Cap Cap 137" will make Capricorn associated
with Rays 1, 3, and 7.

**17. Esoteric rulerships:** The new -YJ7 and -YJ70 switches customize
esoteric and Hierarchical rulerships. They are very similar to the
existing -YJ switch that customizes a standard exoteric rulership. These
switches take three parameters: The planet to change the rulership of,
the sign that it rules, and a second sign that it also rules if any.

**18. Esoteric influences:** The new -Yj7 switch defines power numbers
for esoteric positionings, as used by the -7 switch esoteric charts. It
takes six parameters. The first three are the power added to a planet
when it's in the sign it esoterically rules, the power when a planet's
in the sign it Hierarchically rules, and the power when a planet's in
the sign it Ray rules. The second three are the same, but are the power
added to a planet when it's in the house corresponding to the sign it
esoterically, Hierarchically, or Ray rules.

**19. Esoteric chart listing:** The new -v7 switch is like the standard
-v chart listing switch, except the text listing will indicate esoteric
astrology rulerships. Normally shown is whether the planet exoterically
rules or is debilitated in the sign (indicated with "R" or "d"
characters), and whether the planet exalts or falls in the sign ("X" or
"f" characters). With this setting, also included is whether the planet
esoterically rules or is debilitated in the sign ("S" or "s"
characters), whether the planet Hierarchically rules or is debilitated
in the sign ("H" or "h" characters), and whether the planet Ray rules or
is Ray debilitated in the sign i.e. whether the planet's Ray is the same
as one of the sign's Rays ("Y" or "z" characters). In case of multiple
alignments applying, the order of priority is to show a standard
exoteric rulership or debilitation, an exaltation or fall, an esoteric
rulership, a Hierarchical rulership, and finally a Ray rulership.

**20. Position rounding:** Previous versions of Astrolog would display
zodiac positions rounded up or down to the nearest minute (or second
when Print Nearest Second was active). Zodiac positions are no longer
rounded up by default, so a position of 12Lib34 means the actual
position is somewhere between 12Lib34:00 and 12Lib34:59. Not rounding is
better when animating Astrolog, so for example the moment when
29Sag59:59 turns to 0Cap00:00 is the exact instant of the Solstice. The
new -Yr switch will make it so positions are rounded as before.

**21. Polar houses:** When a chart is cast in a polar region within the
Arctic or Antarctic Circle, the Ascendant may be more than 180 degrees
after the MC, which makes it impossible to have proper house cusps (at
least for systems that associate the Asc with the 1st house and the MC
with the 10th). Normally Astrolog addresses this by flipping the
Ascendant 180 degrees if it's in the wrong half of the zodiac. If the
new -Yp switch is set, the MC will be flipped 180 degrees instead.

**22. Windows file extensions:** Astrolog setup claims ownership the
file extension ".as", standing for Astrolog Switch file. The ".as"
extension files appear in Windows as a gray ringed planet icon. Double
clicking a ".as" file (or right clicking it and selecting "Open") will
launch Astrolog and have it automatically open that file. Right clicking
a ".as" file and selecting "Edit" will open the file in the text editor
Notepad.

File command line: If Astrolog is invoked with a single parameter that
doesn't look like a command switch (e.g. "astrolog file.as") and that
parameter exists as a file, then the command line will be converted to a
parameter being passed to the -i switch (e.g. "astrolog -i file.as").
This is needed internally because the Windows "Open" verb is implemented
by launching the program and passing it the file as a parameter.

\--

Here\'s a summary of the 21 new command switches in Astrolog 6.00 that
weren\'t in previous versions:

**-H7:** Display information about the seven esoteric Rays.

**-v7:** Like -v but include esoteric and Ray rulership placements.

**-7:** Display esoteric astrology and ray summary for chart.

**-bp:** Use less accurate Placalc files instead of Swiss Ephemeris.

**-bm:** Use inaccurate Matrix formulas when ephemeris unavailable.

**-WSg:** Setup Windows program group, for current user only.

**-WSG:** Setup Windows program group, for all users.

**-WSd:** Setup Windows desktop icon for program.

**-WSx:** Setup registering Windows file extensions for program.

**-WSu:** Unregister Windows file extensions for program.

**-setup:** Setup Windows program group for current user, desktop icon,
and file extensions for program.

**-Yr:** Round positions to nearest unit instead of crop fraction.

**-Yp:** Fix polar houses by preserving Ascendant instead of MC.

**-Yj7 \<inf1\> \<inf2\> \<inf3\> \<inf4\> \<inf5\> \<inf6\>:** Set
influences for in esoteric, hierarchical, Ray ruling sign, plus same for
ruling house.

**-YJ7 \<obj\> \<sign\> \<cosign\>:** Set signs planet esoterically
rules.

**-YJ70 \<obj\> \<sign\> \<cosign\>:** Set signs planet hierarchically
rules.

**-Y7O \<obj1\> \<obj2\> \<ray1\>..\<ray2\>:** Customize object rays.

**-Y7C \<sign1\> \<sign2\> \<rays1\>..\<rays2\>:** Customize sign rays.

**-YkO \<obj1\> \<obj2\> \<col1\>..\<col2\>:** Customize planet colors.

**-Yk7 \<1..7\> \<1..7\> \<col1\>..\<col2\>:** Customize Ray colors.

**-YX7 \<inf\>:** Set influence width for graphic esoteric ephemeris.

Here\'s a summary of the 12 new menu commands in the Windows version of
Astrolog 6.00 that weren\'t in previous versions:

File / Save As Wallpaper / Stretch Bitmap

File / Save As Wallpaper / Fit Bitmap

File / Save As Wallpaper / Fill Bitmap

Chart / Esoteric

Help / List Rays

Help / Documentation / Open License

Help / Documentation / Open Website Mirror

Help / Setup / Program Group (User)

Help / Setup / Program Group (All)

Help / Setup / Desktop Icon

Help / Setup / File Extensions

Help / Setup / Uninstall Extensions

EXTENDED AND IMPROVED FEATURES {#extended-and-improved-features .Section}
==============================

A list of improvements to existing features, such as new things you can
now do with old features that you couldn't do before, or ways existing
features work better than before:

**1. Nearest second times:** The Print Nearest Second setting as set
with the -b0 switch affects many more areas in the program.

Time display: When Print Nearest Second is on, all clock times will
include seconds. Exact times in the Transits In Day search list (-d
switch), the Transit To Natal search list (-t switch), and the Rising
and Setting Times list (-Zd switch) will all be displayed to the second,
instead of just to the minute. This will also affect the time and
location values in chart header text.

Time entry: Entry of times in the Enter Chart Info dialogs and command
switches that take time will now parse seconds (this is true regardless
of the Print Nearest Second setting). For example, "12:34:56am"
translates to 12 hours, 34 minutes, and 56 seconds. Fractional seconds
can be entered, e.g. "12:34:56.78" means 12 hours, 34 minutes, and 56.78
seconds. One can still enter times like "12:34pm" without a seconds
qualifier, in which case 0 seconds will be used. Similarly, seconds can
also be entered for longitude and latitude locations, in formats such as
"122W19:59" or "122:19:59W". When Print Nearest Second is on, times and
locations in the Enter Chart Info dialog fields will also be displayed
to the nearest second.

Zodiac display: When Print Nearest Second is on, the text mode aspect
and midpoint grids (-g switch) will have an extra row for the zodiac arc
second of the orb or midpoint position.

Azimuth display: When Print Nearest Second is on, the text mode rising
and setting chart (-Zd switch) will display the rising and setting
horizon azimuth point to the nearest second. Before, only zenith and
nadir points could have their altitude displayed to the nearest second.

**2. HTML documentation:** The main documentation file for Astrolog is
now HTML with text formatting, which is much more readable. Before it
was plain text with 80 column lines. Similarly, the update file
describing changes to the latest version (what you're reading here) is
also now HTML instead of plain text.

**3. Windows clock:** The Windows version of Astrolog will use Windows
calls to compute the current time for "now" charts. This should ensure
"now" charts are always correct, and avoid having to set the TZ
environment variable, or use the -Yz switch, to prevent "now" charts
from being off from the expected result by some number of hours.

**4. Time zone directions:** The -z switch time zone setting (and time
zone fields in Windows dialogs) will accept "W" and "E" suffixes, in
order to indicate whether the time zone is west or east of GMT. Time
zones will be output with "W" or "E" (or neither in the case of GMT
itself) in all charts and files, instead of positive or negative signs
as before. One can still use positive numbers to indicate west of GMT,
and negative numbers to indicate east of GMT, however the new default
format makes both entry and display of time zones more consistent and
understandable.

**5. Daylight autodetect:** The -z0 switch default Daylight Saving Time
setting will accept "autodetect" (which may be abbreviated as "auto" or
"a"), in order to compute whether Daylight time is on or off at the
current moment. This allows charts for "now" to automatically use
Daylight time when the computer's internal clock is using it. Previously
one would have to manually change this in their default settings file
twice a year. Presently the "auto" value is only implemented to detect
this in the Windows version.

**6. Ayanamsa addition:** The zodiac degree offset dropdown in the
Windows "Setting / Calculation Settings" command dialog has been
extended to include the Djwhal Khul system, which is -3.619166 degrees
(or -3 degrees 37' and 9") different from the default of Fagan-Bradley.
Djwhal Khul is a significant figure in esoteric astrology, so that
ayanamsa is good to include with other esoteric astrology features.

**7. Date Difference extension:** The Date Difference chart (-rd switch)
will now show fractional amounts for the years, months, weeks, days,
hours, minutes, and even seconds that have passed between the two chart
times. Also, the difference in location between the two charts is
included. The degree differences between longitude and latitude are
shown, as is the actual distance between the two spots on the globe when
measured around a great circle (displayed to the degree, as well as in
miles or kilometers based on whether the European date format is
active).

**8. Sign help extension:** The List Signs table (-HC switch) has been
extended to include esoteric astrology information. For each sign,
listed are the Rays associated with the sign, the sign's standard
exoteric planetary rulers, the sign's esoteric rulers, the sign's
Hierarchical rulers, the planet exalted in the sign, the exoteric
detriments in the sign, and the planet that falls in the sign.

**9. Object help extension:** The List Objects table (-HO switch) has
been extended to include esoteric astrology information. For each
planet, also listed are the signs the planet esoterically rules, the
signs the planet Hierarchically rules, and the Ray associated with the
planet.

**10. Ephemeris cusps:** The text and graphics ephemeris charts (-E
switch) will include house cusp and other fast moving objects that move
around the zodiac in a single day, if such objects are unrestricted. In
such cases, it's important to remember that object positions in the
ephemeris are only plotted once per day, so when an object such as the
Ascendant changes only a degree or so between one day and the next,
within the day the object did move around the entire zodiac.

**11. Ephemeris format:** The text mode ephemeris charts (-E switch)
will now respect the 360 degrees display format (-sd switch) and hours
and minutes display format (-sh switch), when Print Nearest Seconds is
off.

**12. Star aspect orbs:** Aspects to fixed stars may now have their
maximum orbs defined. The -Am and -YAm switches to specify the maximum
orbs for object(s), along with the -Ad and -YAd switches to specify orb
additions to object(s), will now accept the object index for the first
star (i.e. \#43). The values assigned to this slot will apply to all
fixed stars. Before, aspects to stars were always hardcoded to two
degrees, which couldn't be changed.

**13. Aspect logic improved:** The "Ignore Insignificant House Cusp
Aspects" setting (-YC switch) has been improved to show more aspects,
when normally redundant aspects wouldn't ever appear due to object
and/or aspect restrictions. If one object has been restricted, any
aspect will be allowed to an object always opposite it (e.g. if
Ascendant restricted allow any aspect to the Descendant). Also if one
aspect has been restricted, anything involving the supplemental aspect
will be allowed (e.g. if Trine restricted allow all Sextiles).

**14. Extended characters:** Astrolog's internal graphics font for text
characters has been extended to include glyphs for the high-Ansi 128-255
character range. These glyphs cover the common Windows-1252 codepage,
which is a superset of ISO 8859-1 (Latin 1) but with extra characters
defined for the 128-159 range.

**15. Animation improved:** In the Windows version, the animation jump
rate (as set on the "Animation / Jump Rate" submenu) can now be set
independent of whether animation is on or off. That allows the Step
Forward and Step Backward commands ("+" and "-" hotkeys) to step by any
rate now. The "Stop Animation" command is now called "Do Animation", and
shows a check mark when animation is on instead of off.

**16. Windows icons extended:** The Windows version comes with 48x48
pixel and 256 color versions of Astrolog's ringed planet icon. Before
there were only 32x32 pixel 16 color icons, which didn't display nicely
in modern versions of Windows which use 48x48 pixel icons most often.

**17. Windows redraws:** In the Windows version, the "View / Windows
Settings / Buffer Redraws" (Tab hotkey) setting is now on by default.
Also, when this setting is on, resizing the window won't blank the
screen first. Together, this makes screen updates (especially when
resizing the window) look much smoother.

**18. Windows DLL's:** The default Windows executable of Astrolog is now
statically linked with the C runtime. That has zero effect on behavior
of the program, however it will avoid the occasional scenario that could
make the program fail to launch with an error like: "This application
has failed to start because the application configuration is incorrect."
Without static linking, the program would depend on runtime DLL's being
on the system (which they usually are, installed by Windows Update)
however on certain systems they would be absent, resulting in a
confusing error and requiring manual installing of the runtime
separately before Astrolog would launch.

PROGRAM CHANGES {#program-changes .Section}
===============

A few changes that aren\'t feature additions or bug fixes have been made
to this version, which means certain old assumptions are no longer
valid. A list of these (which aren\'t useful to be aware of unless you
have used previous versions of the program) follows:

**1. Astrolog.dat renamed:** The "astrolog.dat" default settings file
has been renamed to "astrolog.as". On startup, Astrolog will search for
and load the contents of "astrolog.as" instead of "astrolog.dat".
Astrolog now uses the ".as" extension (standing for "Astrolog Switch"
file) for chart info files and setting files. This extension isn't
required, so existing chart info files don't need to be renamed.

**2. Helpfile renamed:** The "Helpfile.540" comprehensive documentation
file has been renamed to "astrolog.htm", and converted from plain text
to HTML.

**3. Update file renamed:** The "Update.540" file containing changes to
the newest version has been renamed to "changes.htm", and converted from
plain text to HTML.

**4. Readme removed:** The "Readme.540" file containing a summary of
Astrolog's features has been removed. Its contents are now a summary
section in the main "astrolog.htm" documentation file. The "Help /
Documentation / Open ReadMe" command in the Windows version that opened
this file has been removed.

**5. Summary file removed:** The "file\_id.diz" file identification
description format file containing a brief summary of Astrolog has been
removed. Its contents are now within the main "astrolog.htm"
documentation file. The "Help / Documentation / Open Summary" command in
the Windows version that opened this file has been removed.

**6. History file archived:** The "History.540" file containing a
history of everything added to each version of Astrolog (which is
basically a list of all the Update files for each version concatenated
together) is no longer being updated. The list of Astrolog versions and
their release dates have been moved into the main "astrolog.htm"
documentation file. The most recent history file is still available in
the file "history.txt" alongside with the source code.

**7. Rulership terminology:** Astrolog now calls the sign opposite a
planet's rulership its "detriment", and the sign opposite a planet's
exaltation its "fall". This is the most common terminology. Astrolog
used to call the sign opposite a rulership its fall, and the sign
opposite an exaltation a debilitation. That's much less common, however
it's still how some have referred to it, e.g. the book "The Inner Sky"
(second printing, page 207) says, "The sign of a planet's fall is always
opposed to the sign of its rulership." Because of this change, the
standard text mode chart listing now uses "R" and "d" to indicate
rulerships and detriments, and "X" and "f" for exaltations and falls.

**8. Exaltations changed:** Mercury is now considered to exalt in Virgo
by default (instead of Aquarius as before). Neptune is now considered to
exalt in Cancer (instead of Sagittarius as before). The North Node is
now considered to exalt in Gemini and the South Node in Sagittarius
(instead of Virgo and Pisces as before). These are the most commonly
used exaltations for these objects. The old values if preferred or other
values can be set with the -YJ0 command switch.

**9. Modified ephemeris:** The Modify Display graphics setting (-Xi
switch) when applied to the graphics ephemeris (-E switch) will make it
so the Part of Fortune (along with the Moon as before) is not displayed.
This setting is meant to prevent the display of fast moving objects
(that can race around the zodiac within a month) without having to
restrict them, and the Part of Fortune (which can now be included in
ephemeris charts) has a fast moving behavior like the Moon.

**10. Previous chart:** The initial contents of the \"previous\" chart
as accessed with \"-i set\" has been changed from the astrological
\"chart\" of version 5.40 of the program to the release of this version
6.00. This chart is now set to the time of the Winter Solstice,
specifically for 8:47:57pm PST (8 hours before GMT) on Monday, December
21, 2015 for Seattle, WA (122W19:59, 47N36:35).

BUG FIXES {#bug-fixes .Section}
=========

Here are problems with version 5.40, all of which have been corrected in
this release:

**1. Alcabitius bug:** Alcabitius houses were computed incorrectly, in
which the cusp positions were off by a few degrees (including the 1st
and 10th, which normally are the same as the Ascendant and Midheaven).

**2. Neo-Porphyry bug:** Neo-Porphyry houses were computed incorrectly
when the sidereal zodiac was active. They would be very messed up, with
houses potentially in the wrong order.

**3. Progression bug:** Solar arc progressed charts (-p0 switch) would
be slightly inaccurate by up to one day, due to bad time difference
calculation. This could be seen by doing a solar arc chart for the exact
same date and time as the birthchart (especially combined with a low
degree per day value) and notice the planet positions incorrectly move.

**4. Gauquelin bug:** In the sidebar of the graphics Gauquelin sector
chart (-M switch), the planet and house positions were wrong. (They
would be offset by a potentially large amount.)

**5. Fixed star bug:** The position of fixed star objects would be
inaccurate when the zodiac offset ayanamsa (-s switch parameter) was
non-zero. They would always be displayed as if the ayanamsa were zero.

**6. Now bug:** Charts for the current moment now would be inaccurate by
up to 24 minutes if the default time zone was a non-integer hour, due to
arc minutes being treated as fractional degrees.

**7. South Node display bug:** When ephemeris files were turned off (\_b
switch) object \#17 (Lilith) would be replaced with the South Node
(because only the Placalc routines knew how to compute the position of
Lilith, and without them Astrolog put the South Node in its place).
However, turning ephemeris files back on (=b switch) later wouldn't
rename object \#17 from "South Node" back to "Lilith". Now that the
South Node has its own unique object index, this will no longer happen.

**8. Ayanamsa accuracy:** Astrolog's values for ayanamsas (as populated
in the Windows "Chart / Settings" dialog) were only accurate to the
nearest arc minute. They have been improved to the nearest arc second.
The offset between the default of Fagan-Bradley and Nirmala Chandra
Lahiri (Robert Hand version) is 0:53\'0" (already accurate to nearest
second), the offset to Krishnamurti is now 0:58'48" (instead of 0:59' as
before), and the offset to B.V. Raman is 2:19\'46" (instead of 2:20').

**9. PostScript crash:** On some Unix versions, creating a PostScript
graphics file (-Xp switch) would crash, due to closing a file handle
twice.

**10. Metafile copy broken:** The "Edit / Copy Chart Picture" menu
command to copy a metafile to the clipboard would fail to do anything in
recent versions of Windows. (The Save Chart Picture command would still
work at least.)

**11. Recall chart broken:** The "Animate / Recall Chart Info" menu
command to replace the current chart with a stored chart would fail to
do anything.

**12. Open Website broken:** The "Help / Documentation / Open Website"
menu command would fail to do anything in recent versions of Windows.

**13. Windows help bug:** The commands on the "Help / Documentation"
submenu that open files would fail to find those files, if the current
directory were other than the Astrolog install directory (such as by
first opening a chart file in a different directory).

**14. Local horizon crash:** The text mode local horizon chart (-Z
switch) would crash if the Sun or the Moon (but not both) were
restricted.

**15. Local horizon bug:** Local horizon charts (-Z switch) would be
slightly inaccurate, in which the longitude and/or latitude of the
location would be off by up to 0.4 degrees, due to arc minutes being
treated as fractional degrees.

**16. Local horizon limitation:** The Nodes and Lilith wouldn't be shown
in the graphic local horizon chart (-Z switch), even if unrestricted.
The Nodes and Lilith have valid longitude and latitude positions, so can
be plotted on the local horizon like any planet.

**17. Astro-graph bug:** Astro-graph charts (-L switch) would be
slightly inaccurate, in which the longitude used would be off by up to
0.4 degrees, due to arc minutes being treated as fractional degrees.

**18. Astro-graph bug:** Astro-graph charts (-L switch) would be
computed incorrectly when the sidereal zodiac was active. The sidereal
offset would be applied, which should not happen since positions are
displayed relative to the local horizon and are therefore independent of
zodiac type.

**19. Astro-graph omission:** Text mode astro-graph charts when
displaying latitude crossings (-L0 switch), would accidentally omit and
not display the northernmost crossing.

**20. Astro-graph bug:** In the graphic astro-graph chart (-L switch),
the dashed equator line would be drawn too far north by 1 degree.

**21. Astro-graph display:** In the graphic astro-graph chart (-L
switch), when displayed in medium or huge character scale, the glyphs
for the Asc and MC at the bottom of the chart would use zoomed versions
of lower resolution glyphs, which would look blocky.

**22. Ephemeris chart bug:** The text mode ephemeris (-E switch), when
doing a non-geocentric chart and when the Sun is restricted, wouldn't
label the first column, which would result in every subsequent column
label being off by one.

**23. Ephemeris chart bug:** The graphic ephemeris chart (-E switch), if
the chart is narrower than 250 pixels or so, would frequently draw
planet lines as if they moved 360 degrees around the zodiac in a single
day.

**24. Grid display omission:** The graphics aspect grid (-g switch)
would leave out aspects if the "Ignore Insignificant House Cusp Aspects"
setting (-YC) were set, which is one scenario in which such aspects are
wanted instead of superfluous. The graphics aspect grid now ignores this
setting and includes all aspects, the same as the text mode aspect grid
already does.

**25. Aspect list bug:** The text mode aspect list chart when displaying
the aspect summary at the end (-a0 switch), would only display zeros in
the summary part when the chart was being interpreted.

**26. Display bug:** Zodiac positions would be rounded up or down to the
nearest minute (or second when Print Nearest Second was active). However
the text color would be based on the actual position, meaning a position
within a half minute/second of the next zodiac sign would have the color
of the current sign but a position in the next sign. Zodiac positions
are no longer rounded up by default, so a position of 12Lib34 means the
actual position is somewhere between 12Lib34:00 and 12Lib34:59.

**27. Time space midpoint glitch:** In the Windows version, selecting
the "Time / Space Midpoint Chart" command would set a mode to replace
chart \#1 with the midpoint of chart \#1 and \#2. That's expected
behavior, however that mode would remain, so any screen update would
update the chart again with the midpoint between the previous midpoint
and chart \#2. In the Windows version, the "Time / Space Midpoint Chart"
command will now compute the midpoint chart, and then get out of
relationship chart mode, so the midpoint chart can be worked with
normally.

**28. Transit bug:** The -tYn \<years\> switch, to do transits for a
given number of years starting with the current year, wouldn't skip over
the \<years\> parameter, and would also parse the parameter as a
separate command switch.

**29. Daylight specification omission:** The -z0 Daylight time switch
would only accept numeric parameters like "0" and "1", and wouldn't
parse non-numeric parameters like "Yes" and "No" (and would also treat
and parse non-numeric parameters as subsequent command switches).

**30. Windows ephemeris:** When computing charts using the Placalc
ephemeris, if a chart were cast for a date that didn't have an ephemeris
file available, multiple Windows error messages would be displayed for
each chart, and potentially numerous errors for tables involving
multiple charts such as transit searches. Each error message would need
to be dismissed manually, which would get annoying quickly. Now only one
error is displayed for each chart until control returns to the user.

**31. Windows display glitch:** When Buffer Redraws was on, and a fixed
size chart was being displayed (such as the aspect/midpoint grid or
astro-graph), then the chart would always be frozen in the upper left
corner of the window, and changing the position of the scrollbars
wouldn't move it.

**32. Windows save glitch:** In Windows open chart dialogs and the
Windows save as text dialog, the extensions dropdown would be
initialized to "All Files" instead of the specific file format in
question. Also in all Windows open and save dialogs, the filename field
would start out empty, and not be selected text containing the default
extension.

**33. Windows dialogs display:** In the most recent versions of Windows,
dialogs are laid out slightly differently, and therefore had display
issues such as controls too close together. All dialogs have been
adjusted to look more polished.

**34. Color omission:** Redefining the standard color palette in the Set
Colors dialog (or the "main" and "rainbow" color lists with the -Yk and
-Yk0 switches) wouldn't change certain parts of certain text charts. For
example, the white and gray header text in the standard listing (-v
switch) wouldn't be affected even if white and gray were redefined to
other colors. Now, every bit of text in every text chart will be
affected by Astrolog's color palette.

COMPILING UPDATES {#compiling-updates .Section}
=================

Finally, here are changes or improvements with respect to version 5.40,
that aren't related to the program's features directly, but rather are
related to compiling the program:

**1. 16 bit Windows dropped:** The source code for Astrolog no longer
supports being compiled for 16 bit Windows. The official Windows
executable only exists as a 32 bit version now. 16 bit Windows is only
required for Windows 3.1 and before, and 16 bit Windows executables are
only even able to run in Windows XP and before, so this platform is
hardly relevant anymore.

**2. Shell archive distribution dropped:** The source code for Astrolog
is no longer distributed in Unix shell archive format. That format was
only required when the primary method of acquiring Astrolog was from
text postings to Usenet newsgroups. Astrolog can still be compiled on
Unix systems just like before, however the source code is released in
the universal .zip archive format. Zip files can be unpacked on most
Unix systems with the "unzip" command, in the same way that the "sh"
command unpacks shell archives.

**3. No Macintosh executable:** This release doesn't come with a
ready-to-run Macintosh executable. I don't have access to a Mac or
compiler for it at this time, so was unable to produce or test a Mac
binary. Astrolog still supports the Mac (including graphics, although
with a command line interface like the X Windows version) just like
before, so anybody with a compiler should be able to generate their own
binary.

**4. C++ sources:** The source code to Astrolog is now C++. All source
code files (including the new Swiss Ephemeris routines) have been
converted from C. This has no visible effect, but makes the sources
cleaner and adding future features easier.

LICENSE {#license .Section}
=======

IMPORTANT NOTICE: Astrolog and all chart display routines and anything
not enumerated below used in this program are Copyright (C) 1991-2015 by
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

O Astrolog 6.00 homepage:
<http://www.magitech.com/~cruiser1/astrolog.htm> O

\* \"Who am I, What am I? As I am, I am not. But as we are, I AM. And to
\*

O you my creation, My Perfect Love is your Perfect Freedom. And I will
be O

\* with you forever and ever, until the End, and then forever more.\" -
GOD \*

O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O\*O
