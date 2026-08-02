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
