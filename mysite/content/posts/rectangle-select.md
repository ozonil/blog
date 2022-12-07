---
title: "Rectangle Select"
date: 2022-12-05T16:51:18-05:00
tags: [programming, emacs]
---

Rectangle select is awesome. Here's how you use it.

`C-x SPC` to toggle the start mark. Move your cursor around to select the second point of the rectangle. Now that you have a rectangular area selected, you can perform operations you want.

```asm
1	.proc main
2	  LDX PPUSTATUS
3	  LDX #$3f
4	  STX PPUADDR
5	  LDX #$00
6	  STX PPUADDR
7	
8	copy_palettes:
9	  LDA palettes,x
10	  STA PPUDATA
11	  INX
12	  CPX #$20  ; 32 colors total
13	  BNE copy_palettes
```
Here's some 6502 code that I copied off a [website](https://famicom.party). Now, the line numbers are annoying. What do I do about it?

1. First do a rectangle select of the lines and the blank places.
2. Just delete the selected area with `C-x r d`

```asm
.proc main                    
  LDX PPUSTATUS               
  LDX #$3f                    
  STX PPUADDR                 
  LDX #$00                    
  STX PPUADDR                 
                              
copy_palettes:                
  LDA palettes,x              
  STA PPUDATA                 
  INX                         
  CPX #$20  ; 32 colors total 
  BNE copy_palettes
```

Your result!

Find more info in the [GNU emacs manual](https://www.gnu.org/software/emacs/manual/html_node/emacs/Rectangles.html).