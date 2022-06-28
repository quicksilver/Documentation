## Description

The Unit Conversion Module provides a method of converting units such as
distances and volumes from within the Quicksilver interface using the
units command line tool.

## How it works

Some examples of conversions possible with this module are shown below.
1 mile Convert to Units... km 1 floz Convert to Units... cm3 32 ft/sec^2
Convert to Units... m/sec^2 c Convert to Units... mph Warning: the space
between the quantity and the units is required. units(1) is not flexible
enough to handle input without the space. Lame, isn't it?

Usage Use the 'Convert to Units...' action to convert a quantity with
units to use another set of units:

Specify the source unit-spec (quantity with units) via text-entry mode
Choose the Convert To Units... action Specify the target unit-spec via
text-entry mode A unit-spec is either:

a quantity, space and a unit (e.g 10 m) or just a unit (e.g. m) units
can be complex using multiplication, division, and exponents. See the
units(1) man page for details but here is a summary.

units(1) understands most familiar units and constants and their
abbreviations, however to avoid misinterpretation sometimes the
abbreviations aren't obvious. E.g., "g" isn't gram but the acceleration
of gravity constant (gm is gram), and oz and floz are different. See the
file /usr/share/misc/units.lib for everything that units(1) understands.

Miscellaneous Notes Seeing an error? Do you have a space between your
quantity and units? For detailed (but often unhelpful) error messages
see Console.app units(1) doesn't do temperature conversions units(1)
will do currency conversions but the rates are from the early 1990s

## Video

Jump to 3:06 to see a way to add conversions. Tutorial at
[LoveQuicksilver.com](http://www.lovequicksilver.com/post/3974202491/unit-conversion-module).
{{#ev:youtube\|CWuPgTDAhw8}}