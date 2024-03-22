[![Actions Status](https://github.com/tbrowder/PDF-GraphicsUtils/actions/workflows/linux.yml/badge.svg)](https://github.com/tbrowder/PDF-GraphicsUtils/actions) [![Actions Status](https://github.com/tbrowder/PDF-GraphicsUtils/actions/workflows/macos.yml/badge.svg)](https://github.com/tbrowder/PDF-GraphicsUtils/actions) [![Actions Status](https://github.com/tbrowder/PDF-GraphicsUtils/actions/workflows/windows.yml/badge.svg)](https://github.com/tbrowder/PDF-GraphicsUtils/actions)

NAME
====

**PDF::GraphicsUtils** - Provides classes and routines for manipulating PDF page objects.

SYNOPSIS
========

```raku
use PDF::Lite;
use PDF::GraphicsUtils;
my PDF:Lite $pdf .= new;
my $page = $pdf.add-page;
my $g = Graphics.new: :$page;
# draw a circle on the page with values in PS points
my ($x, $y, $radius) = 200, 200, 30;
$g.circle: :$x, :$y, :$radius; 
# use other units of length for another circle
$g.circle: :x<2in>, :y<3in>, :radius<0.5in>; 
$pdf.save-as: "mypdf.pdf";
# View the pdf file and see two circles
```

DESCRIPTION
===========

**PDF::GraphicsUtils** is a large collection of graphics objects with the ability to use various units to place them on the page as well as to describe their shape. See a complete list of graphics methods at **GRAPHICS-METHODS**.

Units available:

### Length

If a number is entered without a suffix, the number is treated as a value in PS (PostScript) points (72 per inch). A unit may be specified with a one- or two-letter suffix as shown in the following table.

<table class="pod-table">
<thead><tr>
<th>Unit</th> <th>Suffix</th>
</tr></thead>
<tbody>
<tr> <td>PostScript</td> <td>ps</td> </tr> <tr> <td>millimeters</td> <td>mm</td> </tr> <tr> <td>centimeters</td> <td>cm</td> </tr> <tr> <td>inches</td> <td>in</td> </tr> <tr> <td>feet</td> <td>ft</td> </tr> <tr> <td>meters</td> <td>m</td> </tr> <tr> <td>yards</td> <td>y</td> </tr>
</tbody>
</table>

### Angle

If a number is entered without a suffix, the number is treated as a value in degrees. A unit may be specified with a three-letter suffix as shown in the following table.

<table class="pod-table">
<thead><tr>
<th>Unit</th> <th>Suffix</th>
</tr></thead>
<tbody>
<tr> <td>degrees</td> <td>deg</td> </tr> <tr> <td>radians</td> <td>rad</td> </tr>
</tbody>
</table>

AUTHOR
======

Tom Browder <tbrowder@acm.org>

COPYRIGHT AND LICENSE
=====================

© 2024 Tom Browder

This library is free software; you may redistribute it or modify it under the Artistic License 2.0.

