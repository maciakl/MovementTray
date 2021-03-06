Luke's Movement Tray Tool
=========================

This tool generates a printable movement tray for war games which
use 20 or 25mm square bases. A good example of such system is
Warhammer Fantasy Battles which uses 20mm and 25mm bases for most of
the infantry models.

In case you were wondering a movement tray is a piece of paper/cardboard
you place under the unit so that the models can be moved as an entire
unit. If you put them directly on the table pushing or aligning them
can be difficult. Movement trays are best made from thick cardboard or
plastic. This tool helps you generate a template you can use to cut
out a tray of the right size. 

The tray is generated as a PDF file that will look approximately like this:

![Sample Output](http://i.imgur.com/xiF3QVp.jpg)

Usage
-----

To generate your tray please provide how many --rows and --cols you
want to have in your unit. Use the --large switch to use the larger
25mm bases (the default is 20mm).

Usage:

    mt.rb --rows 5 --cols 5 --file tray.pdf

The above will generate a 5x5 tray using 20mm bases and save it into
file named tray.pdf in the current directory.

You can also use short command switches:

    mt.rb -r 2 -c 5 -b -f tray.pdf -b cavalry
    
The above will generate a tray using 20x50mm cavalry bases with 2 ranks
and 5 models per rank.

Note: the tray must fit on a single sheer of standard 8x11" letter paper.
There are following limitations with respect to unit size:

    Standard 20mm units:    10 rows x 10 cols
    Large 25mm units:       8 rows x 8 cols
    Monster 40mm units:     4 rows x 4 cols
    Cavalry 25x50mm units:  4 rows x 8 cols

This tool accepts the following command line arguments:

    --rows,     -r <int>:     Number of rows
    --cols,     -c <int>:     Number of collumns
    --file,     -f <string>:  Output file
    --base,     -b:           Base size: standard, large, monster, cavalry
    --version,  -v:           Print version and exit
    --help,     -h:           Show help message
    
The `--rows`, `--cols` and `--file` switches are required. The `--base` 
switch is optional. If ommited it defaults to `standard` 20x20mm bases.

TODO
----

* 20 mm skirmish formation

Dependencies
------------

This tool depends on the following gems:

* [Prawn][p] - for PDF generation
* [Trollop][t] - for command line argument parsing

[p]: http://prawn.majesticseacreature.com
[t]: http://trollop.rubyforge.org/
