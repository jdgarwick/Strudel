**DJ Dave Workshop**

# notes, structures, and arps

<> plays one per cycle

```
setCps(145/60/4)

note("<c3 g3>").sound("supersaw")
```

increase the speed if the hits each cycle

```
note("<c3 g3>").sound("supersaw").fast(2)
```

use "*4" to play it 4 times all within the same cycle

```
note("<c3*4 g3*4>").sound("supersaw").fast(2)
```

use "!4" to play it 4 times before moving to the next thing

```
note("<c3!4 g3!4>").sound("supersaw").fast(2)
```

use "@4" to stretch it 4 cycles before moving to the next thing

```
note("<c3@4 g3@4>").sound("supersaw").fast(2)
```

use "[]" to say 'play these things separately and take up the same amount of time as something else outside the bracket.' kind of fits each item inside to one cycle

```
note("<g5 g#5 a#5 d#5 [g5 g#5] d#5>").sound("supersaw").fast(2)
```

use "[,]" to also give a simultaneous list of things to play, like sounds or notes

```
note("<[c3, g3] c3>").sound("[supersaw, square]").fast(4).room.lpf(500)
```

<> allows you to go between different values. playing the first item the first cycle, and move to the second one after, etc. this will play (c3, g3) at the same time, then play (c3, g3), then back to (c3, g3), and then (a3, g3)

```
note("<[c3, g3] [<c3 a3>, g3]>").sound("[supersaw, square]").fast(4).room.lpf(500)
```

# arps

plays a random list of integers between 0 and 7 (aka indexes at 0) (also how many notes are in music scales)

```
$arp:  n(irand(8))
```

use .scale("") to define the scale to use and .struct("x") to define the basic structure.

```
$arp:  n(irand(8)).scale("c3:minor:pentatonic").struct("x").sound(saw)
```

use .struct("x*4") - the same thing as saying (fast(4)).sound(saw)

```
$arp:  n(irand(8)).scale("c3:minor:pentatonic").struct("x*4").sound(saw)
```

use brackets and a vertical line to give an equal probability of either thing happening:

```
$arp:  n(irand(8)).scale("c3:minor:pentatonic").struct("x*[4|8]").sound(saw)
```

.seg(8) is the same thing as .struct("x*8")

```
$arp:  n(irand(8)).scale("c3:minor:pentatonic").struct("x*8").sound(saw) //.seg(8)
```

use <> within the .irand function to alternate between a few note options to a bunch of note options. First choosing from a small number of notes to then a bunch of notes. Kind of gives a *call-and-response* structure. You can do the same thing with the sounds

```
$arp:  n(irand("<4 12>")).scale("c3:minor:pentatonic").struct("x*<8 16>").sound("<saw supersaw>") //.seg(8)
```


# using samples for percussion

# using samples melodically

# effects


Add decay to adjust the length of the hit. Shorter decay is more "punchy"

```
note("<c3 g3>").sound("supersaw").fast(2).decay(0.1)
```

Add reverb and coarse to make it sound crushed and big

```
note("<c3 g3>").sound("supersaw").fast(2).decay(0.1).room(1).coarse(10)
```

Try echoes? (how many times to repeat, structure of the notes, how much to reduce the sound each time it echoes)

```
note("<c3 g3>").sound("supersaw").fast(2).decay(0.1).room(1).coarse(10).echo(4,0.19,0.6)
```

Let's do that easier with delay... though you don't have as much exact control...

```
note("<c3 g3>").sound("supersaw").fast(2).decay(0.1).room(1).coarse(10).delay(1)
```

Add lpf to only allow lower sounds.. or a hpf for higher sounds

```
note("<c3 g3>").sound("supersaw").fast(2).decay(0.1).room(1).coarse(10).lpf(500)
```

Use .ply to add how many times you want something to repeat. .ply(2) repeats each note twice (or three or four times)

```
note("<c3 g3>").sound("supersaw").fast(2).decay(0.1).room(1).coarse(10).lpf(500).ply(2)
```
