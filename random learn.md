**Random Learn Notes**

Global Window Variable

```
//--------------------------------
//--------------------------------
window.DX = (donk=0.8) => {  // global window variable assigned to the dx variable
 donk = reify(donk) // tells strudel to interpret donk as a pattern 
  return s("sine").fm(donk.mul(6)).fmdec(.2)
}

$BASS: n("<0 1 3 0 4 8 7 9>*8").scale("g1:phrygian")
.set(DX("<.5 .3 .3 .6>*16"))
 
_$: s("sbd!4") 
```

Switch Angel Song

```
setCpm(160/4)
const volume = slider(0.5)
all(x => x.mul(postgain(volume)))

$LEAD: n("<0 <6 6 8 9> 0 2 4>*16".seg(16).rib(15,2).sub(2))
  .scale("f:minor").delay(.5).gain(1.3)
  .s("pulse").pwrate(2).pan(rand)

$CHORDS: n("<6 3 7 6>/2").chord("<F-7>/2").voicing().trans(-12).room(1)
.sound("sine")

$HAT: s("white!16").dec(tri.fast(4).range(0.05,.1))

$SNARES: s("sd!8").n(irand(16).seg(8)).hpf(500)
  .rib(5,.5).bank('mc303')
  .dec(.2).delay(rand)
  .delaytime(rand.fast(3))
```
