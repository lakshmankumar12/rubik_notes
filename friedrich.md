# F2L algo

# Summary table

Both are in place, both to flip               | Algo (270 corner)  | algo: F U F U'  ..  L' U L .. F2
Both are in place, edge ok, corner flip       | RuRuRuuR           | F2 U2, and then R-U-R'-U-R-U2-R
Both are in place, edge flip, corner ok       | fur-fru            | fur-fru..  F2-U2-R' F2-R-U2 F'-U-F
Edge in place, white-on-side, edge ok/not-ok  | W.Down             | [U] (white on f-face). F(white-down), U/U', F' (touching/rollover)
Edge in place, white top, edge-aligned        | FUL/behind-forward | [U2] F'-U-L'  U' L-U'-F
Edge in place, white top, edge-not aligned    | TT already         | Touching-touching already .. F'-U-F R-U2-R'
Corner in place, aligned                      | Orig Slow          | [U] R U' R' (tt at this point) U' F' U F
Corner in place, white-facing, edge on F-side | Intuitive (rollov) | F'-U'-F (rollover) U-F'-U'-F (do the rollover)
Corner in place, white-facing, edge on R-side | TT with the R2 move| R-U' (touching-touching) R2(bring-to-F-face) F-R-F'(restore-R)



Link: http://www.ws.binghamton.edu/fridrich/Mike/middle.html

Different types:

* Edge is in place.
    * White oriented way-1
    * White oriented way-2 (The page shows only one way)

# Both pieces are in place. Only to flip them.

## edge in place. White corner-piece to correct.

Yellow on top. One face is F, other is R. Here white should be on R-side.
    * Algo: F2 U2 F U F' U F U2 F
    * Note that this is F2,U2,and then R-U-R'-U-R-U2-R', but done on F, and the last is R and not R'
    * So, do a F2 U2. This will get the corner-to-adjust + a good-middle + a good-corner(or yet to focus corner) on top.
        * Now keep the good-edge at L-side/good-corner at LF and start the R-U-... algo.

If white is on F-side, simply, keep this corner of interest as your F and L-side.
    * So, do a F2 U2.
    * Now keep the good-edge at R-side/good-corner at RF and start L-U'... algo


## white corner-piece in place. Only edge to correct.

Keep the edge-to-fix at F-R. White bott/Yellow-top as usual.
    * Algo: F2 U2 R' F2 R U2 F U' F
    * how it works:
        * Here is a pic of the F-face (XX-dontcare, DD-dontdisturb, FL-flip, CC - center anyway)
                XX  XX  XX
                DD  CC  FL
                DD  DD  DD
        * It is an operation on F,R,U only. If you see, there is a symmetry for all the 4 DD-pieces.
          Only the FL gets flipped. The DC's ofcouse get jumbled up.
        * You have to memorize the order.
            * Remember - F2 U2 R' - F2 R U2   (fur-fru, with r-towards first and f2,u2)
            * After that its straightfoward anyway. It will be touching-touching good case - so F' U F.

## flip both white and edge piece.

Edge to fix is at F-R. White on corner is on right side.
    * Algo: F' U F' U' L' U L F2
    * how it works:
        * Here is a pic of the F-face and U-face. (DD is also WW - the not-to-disturb ones)
            XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  DD   XX  XX  DD   FF  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  XX  XX   FF  XX  XX   FF  XX  XX   XX  XX  DD   XX  XX  DD   FF  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  FF  WW   WW  XX  XX   XX  DD  DD   XX  FF  XX   FF  FF  XX   XX  DD  DD   WW  DD  DD   XX  XX  XX
            ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ----------
            XX  XX  XX   XX  RR  RR   FF  XX  XX   XX  FF  FF   XX  RR  XX   RR  RR  XX   XX  FF  FF   FF  FF  FF   XX  XX  XX
            FF  FF  RR   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF   FF  FF  FL
            FF  FF  RR   XX  FF  FF   XX  FF  FF   FF  XX  XX   FF  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   FF  FF  FL
            Start           F'            U            F'           U'          L'            U           L            F2
        * You can observe the flipping happening with practice.

If W is facing you, then simply keep the corner/edge to fix on the L-side and mirror the algo
    * Algo: F U' F U R U' R' F2

Not sure if WW on right, and facing side has FF instead of RR of corner-piece, is a possibility.

# Edge in place. Corner piece to be brought down

## edge rightly aligned

### White faces side

* white is one side, other side is aligned.
    * Algo:        [U] F' U F U2 F' U F
    * Move the white, so that its on the f-face on top.
    * Put white down, slide edge one step further
    * Bring white up, you have the same-color touching-touching case.

* Not clear if its a possibility at all to have white on side and the other side not of the same color.

### White faces top

* White on top, edge is already aligned.
    * When white kept on top, the colors aren't aligned.
    * Algo: [U2] F' U  L' U' L  U' F
        * Inverse: F' U La U Lt U' F U2
    * How it works?
        * Just keep doing it and see the flow!
                                                              ^FF-RR
            XX  XX  XX   WW  XX  XX   WW  XX  XX   XX  XX  WW   XX  XX  WW   WW  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  WW   XX  XX  XX   XX  RR  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  RR  RR   XX  XX  XX
            ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ----------
            XX  XX  RR   XX  XX  XX   XX  FF  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   WW  XX  XX   XX  FF  FF   XX  XX  XX
            FF  FF  FF   FF  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF
            FF  FF  XX   FF  FF  XX   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF
              Start         [U2]           F'          U           L'(away)      U'        L(towards)      U'          F voila!
        * The idea is to put the corner below to the edge intead of above it as its at the start.
        * For this, we bring the edge on to the B-face from F-face via (F'-U-Laway).
        * Now we bring the corner atop it - so that its now behind edge. (U')
        * Restore (Ltowards-U'-F)





    * I guess if whte is on top and colors are aligned, you are good to go for touching-touching case.

## Edge not alighned.

### white faces side
* White on top, edge is not aligned.
    * Algo:      [U] F' U' F U' R U R'
        * Inverse:  R U' R' U F' U F
    * Move the white, so that its on the f-face on top.
    * Put white down, slide edge one step away
    * Bring white up, you have the simple rollover case.

* Not clear if its a possibility at all to have white on side and the other side is aligned.

### White faces top

* Algo:      F' U F R U2 R'
    * Inverse: R U2 R' F' U' F
* This is just touching-touching.
* Flip it to get out of way (F' U). Restore front face (F)
* Just do R-U2-R' (Tip:Dont waste time by doing U-R-U-R')

* Not clear if its a possibility at all to have white on side and its touching-touching bad.

# Corner in place. Edge to be brought down.

## Corner correctly placed.

* This is actually the slow-algorithm. (Where you finish white-corners first)

* Algo:  [U] R U' R' U' F' U F
    * Inverse:  F' U' F U R U R'

* Move the middle piece on the other side to where it should come. [remember :) ]
* Bring white on top with the R-operation (or L)
* The middle piece comes to F-face (also pushing the corner and de-orienting it)
* Revert the R(or-L) operation. This now makes it touching-touching
* Move it back in same dir as how you made the middle piece coe to F. So the touching-touching is on R(or-L) now.
* F-U'-F to place it back. This should be obvious

## corner incorrect

### when edge is aligned to its color, white is on side.

Note flip, and keep white as your F face.

O.Algo: F D' F2 R F R'
Algo:   R U' R2 F R F'
    Inverse: F R' F' R2 U R'
            XX  XX  XX   XX  XX  XX   XX  XX  WW   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  FF   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  XX  WW   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX
            ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ----------
            XX  XX  XX   XX  XX  RR   XX  XX  XX   XX  XX  XX   FF  FF  XX   FF  FF  XX   XX  XX  XX
            FF  FF  XX   FF  FF  XX   FF  FF  XX   FF  FF  FF   FF  FF  XX   FF  FF  XX   FF  FF  FF
            FF  FF  WW   FF  FF  XX   FF  FF  XX   FF  FF  FF   FF  FF  XX   FF  FF  XX   FF  FF  FF
              Start          R             U'          R2          F             R            F'
                                                   (at this point
                                                   F face is good,
                                                   but R face is
                                                   wrong)
    * R-U' gets its touching-touching.
    * R2   brings it aligned on F-face
    * F-R-F' restores the R-face.


### when edge is aligned to its color, white is on F:w

Keep white on F-side

O.Algo: R' D' R D R' D' R
Algo:   F' U' F U F' U' F
    Inverse: F' U F U' F' U F

* F'-U'-F makes it rollover-ready.
* U onto position
* F'-U'-F rollever.

