//--------------------------------
//-------------------------------- BREAKBEATS

_$: s('breaks')
  .slow(2).fit() // slows number of cycles and fits them to 2 cycles
.scrub("0.5!1") // scrub from x and repeat y number of times

// common jungle beat 1 

_$: s('breaks')
  .slow(2).fit() 
.scrub("<0@5 0@3>*8") // hold 5 eighth notes, start at the beginning for 3 eighth notes

// common jungle beat 2

_$: s('breaks')
  .slow(2).fit()
  .n(2) // lets you pick the break you want to use
.scrub("<0@3 0@5>*8") // hold 3 eighth notes, start at the beginning for 5 eighth notes

// common jungle beat 2

_$: s('breaks')
  .slow(2).fit()
  .n("<1 0 1 0>") // alternate break patterns
.scrub("<0@3 0@5>*8") // hold 3 eighth notes, start at the beginning for 5 eighth notes
.almostNever(x => x.ply("2|4").fast(4).rib(98,1)) // sometimes play it succinctly, but constrained
              
// random generation

$: s('breaks')
  .slow(2).fit() 
  .n("<0>") // break pattern
.scrub(irand(16).div(16) // evenly sliced chunks
      .seg(8)).rib(28,1) // eighth note segments
      .almostNever( x => x.ply(2|4))
  .o(2)
