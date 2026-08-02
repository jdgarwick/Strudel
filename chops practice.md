**practice chops**

```
// @title vocal chops learn
setcps(145/60/4)
setScale("f:phrygian")

S$kick: s("sbd!4").duck("2:3:4:5:6").duckdepth(0.75).duckatt(0.25)

S$SNARE: s("sd:1").struct("- x").fast(2).postgain(1.2)

S$chops2: s("samples_2:0").slice(16, "3").clip(1).fast(4)
  .delay(0.25)._punchcard().o(2)

S$chops1: s("samples_2:3").slice(16, "13").clip(1).fast(4)
  .delay(0.25).striate(4)._punchcard().o(3)

$chops3: s("samples_2:1").slice(16, "3 4").clip(1).fast(4).sometimes(ply(2))
  .delay(0.25).jux(rev).gain(slider(1))._punchcard().o(4)

S$BASS: n("<0 5 3 2 0 1 3 8>*16".sub(12)).sc().s("supersaw")
  .acidenv(slider(0.947))
  .diode("1").glide("[.01 .03]").dly(0.25).lpd(.9).lpq(2).decay(0.05)
  .postgain(1.1).pan(rand).o(5)

S$BASS2: n("<0 5 3 2 0 1 3 8>*16".sub(12)).sc().s("sawtooth")
  .acidenv(slider(0.928))
  .diode("1").glide("[.01 .03]").dly(0.25).lpd(.9).lpq(2).decay(0.08)
  .postgain(1.1).pan(rand).o(6)

S$BASS3: n("<0 5 3 2 0 1 3 8>*16".sub(12)).sc().s("sawtooth")
  .acidenv(slider(0.928))
  .diode("1").glide("[.01 .03]").dly(0.25).lpd(.9).lpq(2).decay(0.08)
  .postgain(1.1).pan(rand).o(7)
```


