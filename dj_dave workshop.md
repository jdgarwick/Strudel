**DJ Dave Workshop**

*notes and arps*

plays one per cycle

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

*effects*
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
