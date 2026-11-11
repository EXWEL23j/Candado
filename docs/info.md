<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This project displays a custom bitmap image on a VGA monitor at 640x480.
The hvsync_generator module creates the sync signals and the current pixel
position. The image is stored in bitmap_rom as 4096 bytes, where each byte
holds four pixels of 2 bits each, giving a 128x128 image. The ROM address
is built from the lower bits of the x and y position, so the image repeats
across the whole screen as tiles. The 2 bit value of each pixel goes to
the palette module, which converts it into the RGB color sent to the output.

## How to test

Connect a TinyVGA PMOD to the output pins and connect it to a VGA monitor.
Apply the clock and release reset. The tiled image should appear on the
screen right away.

## External hardware

List external hardware used in your project (e.g. PMOD, LED display, etc), if any
