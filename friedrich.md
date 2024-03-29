# F2L algo

# Summary table

| Situation                                     | Mnenomic            | Algo                                                               |
| --------------                                | -----------------   | ----                                                               |
| Both are in place, both to flip               | Algo (270 corner)   | algo: F U F U'  ..  L' U L .. F2  (white should be on side)        |
| Both are in place, edge ok, corner flip       | RuRuRuuR            | F2 U2, and then R-U-R'-U-R-U2-R   (white should be on side)        |
| Both are in place, edge flip, corner ok       | fur-fru             | fur-fru..  F2-U2-R' F2-R-U2 F'-U-F                                 |
| Edge in place, white-on-side, edge ok/not-ok  | W.Down              | [U] (white on f-face). F(white-down), U/U', F' (touching/rollover) |
| Edge in place, white top, edge-aligned        | FUL/behind-forward  | [U2] F'-U-L'  U' L-U'-F                                            |
| Edge in place, white top, edge-not aligned    | TT already          | Touching-touching already .. F'-U-F R-U2-R'                        |
| Corner in place, aligned                      | Orig Slow           | [U] R U' R' (tt at this point) U' F' U F                           |
| Corner in place, white-facing, edge on F-side | Intuitive (rollov)  | F'-U'-F (rollover) U-F'-U'-F (do the rollover)                     |
| Corner in place, white-facing, edge on R-side | TT with the R2 move | R-U' (touching-touching) R2(bring-to-F-face) F-R-F'(restore-R)     |

Note:
* When both are in place, white is on side as you start
* When only one is in place, white is on F, when you start

Another way to categorize

| Situation                                  | Mnenomic            |
| --------------                             | -----------------   |
| Both needs fix                             |                     |
| ..Both are in position                     | Algo (270 corner)   | M
| ..Corner in position                       | (middle piece down) |
| ....White facing, edge aligned on F        | Target rollover     | E
| ....White facing, edge aligned on R        | The R2 algo         | E
| ..Edge in position                         |                     |
| ....White Top                              | TT already          | E
| ....White facing                           | W.down, Rollover    | E
| Edge is perfect                            |                     |
| ..Corner is in position                    | RuRuRuuR            | H
| ..Corner on top. White on top              | FUL/behind-forward  | E
| ..Corner on top. White facing              | W.down, TT          | H
| Corner is perfect                          |                     |
| ..Edge in its position                     | fur-fru, F'-U-F     | E
| ..Edge on top                              | slow algo           | M



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
            ```
            XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  DD   XX  XX  DD   FF  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  XX  XX   FF  XX  XX   FF  XX  XX   XX  XX  DD   XX  XX  DD   FF  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  FF  WW   WW  XX  XX   XX  DD  DD   XX  FF  XX   FF  FF  XX   XX  DD  DD   WW  DD  DD   XX  XX  XX
            ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ----------
            XX  XX  XX   XX  RR  RR   FF  XX  XX   XX  FF  FF   XX  RR  XX   RR  RR  XX   XX  FF  FF   FF  FF  FF   XX  XX  XX
            FF  FF  RR   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF   FF  FF  FL
            FF  FF  RR   XX  FF  FF   XX  FF  FF   FF  XX  XX   FF  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   FF  FF  FL
            Start           F'            U            F'           U'          L'            U           L            F2

            ```
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
            ```
                                                              ^FF-RR
            XX  XX  XX   WW  XX  XX   WW  XX  XX   XX  XX  WW   XX  XX  WW   WW  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  WW   XX  XX  XX   XX  RR  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  RR  RR   XX  XX  XX
            ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ----------
            XX  XX  RR   XX  XX  XX   XX  FF  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   WW  XX  XX   XX  FF  FF   XX  XX  XX
            FF  FF  FF   FF  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF
            FF  FF  XX   FF  FF  XX   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF
              Start         [U2]           F'          U           L'(away)      U'        L(towards)      U'          F voila!
            ```
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
            ```
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
            ```
    * R-U' gets its touching-touching.
    * R2   brings it aligned on F-face
    * F-R-F' restores the R-face.


### when edge is aligned to its color, white is on F

Keep white on F-side

O.Algo: R' D' R D R' D' R
Algo:   F' U' F U F' U' F
    Inverse: F' U F U' F' U F

* F'-U'-F makes it rollover-ready.
* U onto position
* F'-U'-F rollever.


Note:
* When both are in place, white is on side as you start
* When only one is in place, white is on F, when you start

Another way to categorize

| Situation                                  | Mnenomic            |
| --------------                             | -----------------   |
| Both needs fix                             |                     |
| ..Both are in position                     | Algo (270 corner)   | M
| ..Corner in position                       | (middle piece down) |
| ....White facing, edge aligned on F        | Target rollover     | E
| ....White facing, edge aligned on R        | The R2 algo         | E
| ..Edge in position                         |                     |
| ....White Top                              | TT already          | E
| ....White facing                           | W.down, Rollover    | E
| Edge is perfect                            |                     |
| ..Corner is in position                    | RuRuRuuR            | H
| ..Corner on top. White on top              | FUL/behind-forward  | E
| ..Corner on top. White facing              | W.down, TT          | H
| Corner is perfect                          |                     |
| ..Edge in its position                     | fur-fru, F'-U-F     | E
| ..Edge on top                              | slow algo           | M



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
            ```
            XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  DD   XX  XX  DD   FF  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  XX  XX   FF  XX  XX   FF  XX  XX   XX  XX  DD   XX  XX  DD   FF  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  FF  WW   WW  XX  XX   XX  DD  DD   XX  FF  XX   FF  FF  XX   XX  DD  DD   WW  DD  DD   XX  XX  XX
            ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ----------
            XX  XX  XX   XX  RR  RR   FF  XX  XX   XX  FF  FF   XX  RR  XX   RR  RR  XX   XX  FF  FF   FF  FF  FF   XX  XX  XX
            FF  FF  RR   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF   FF  FF  FL
            FF  FF  RR   XX  FF  FF   XX  FF  FF   FF  XX  XX   FF  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   FF  FF  FL
            Start           F'            U            F'           U'          L'            U           L            F2
            ```
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
            ```
                                                              ^FF-RR
            XX  XX  XX   WW  XX  XX   WW  XX  XX   XX  XX  WW   XX  XX  WW   WW  XX  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  XX  XX   XX  XX  XX
            XX  XX  WW   XX  XX  XX   XX  RR  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   RR  XX  XX   XX  RR  RR   XX  XX  XX
            ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ---------- » ----------
            XX  XX  RR   XX  XX  XX   XX  FF  XX   XX  XX  XX   XX  XX  XX   XX  XX  XX   WW  XX  XX   XX  FF  FF   XX  XX  XX
            FF  FF  FF   FF  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF
            FF  FF  XX   FF  FF  XX   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   XX  FF  FF   FF  FF  FF
              Start         [U2]           F'          U           L'(away)      U'        L(towards)      U'          F voila!
            ```
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
            ```
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
            ```
    * R-U' gets its touching-touching.
    * R2   brings it aligned on F-face
    * F-R-F' restores the R-face.


### when edge is aligned to its color, white is on F

Keep white on F-side

O.Algo: R' D' R D R' D' R
Algo:   F' U' F U F' U' F
    Inverse: F' U F U' F' U F

* F'-U'-F makes it rollover-ready.
* U onto position
* F'-U'-F rollever.

# Lost orientation algos

Link: http://www.ws.binghamton.edu/fridrich/Mike/permute.html

## Only edges to position

U: (1/9)
```
    +---+---+---+      +---+---+---+
    |   |   |   |      |   |   |   |
    +---+---+---+      +---+---+---+
    | B |Fx | C |  »   | A |Fx | B |
    +---+---+---+      +---+---+---+
    |   | A |   |      |   | C |   |
    +---+---+---+      +---+---+---+
```

Regular Mu-mUm-uM (or) Mu'-mUm- u'M

Z: (1/36)
```
    +---+---+---+      +---+---+---+
    |   | B |   |      |   | A |   |
    +---+---+---+      +---+---+---+
    | A |Fx | D |  »   | B |Fx | C |
    +---+---+---+      +---+---+---+
    |   | C |   |      |   | D |   |
    +---+---+---+      +---+---+---+
```

Regaular:  Mu-Mu-m'-UMU-m'-U

H: (1/72)
```
    +---+---+---+      +---+---+---+
    |   | B |   |      |   | A |   |
    +---+---+---+      +---+---+---+
    | D |Fx | C |  »   | C |Fx | D |
    +---+---+---+      +---+---+---+
    |   | A |   |      |   | B |   |
    +---+---+---+      +---+---+---+
```

Regular:  Mu-MUM-uM

## Only corners to postion

A: (1/9)
```
    +---+---+---+      +---+---+---+
    | B |   | C |      | A |   | B |
    +---+---+---+      +---+---+---+
    |   |Fx |   |  »   |   |Fx |   |
    +---+---+---+      +---+---+---+
    |   |   | A |      |   |   | C |
    +---+---+---+      +---+---+---+
```

Bingo: R' F R' B B R F R' B B R2
Note:
* Fixed in LF corner. Rotates clockwise -  The one in RF goes up diagnoally
* This is exactly same as G as well.
Mirror algo:
* Keep fixed in R corner

Algo:  L F' L B B L' F L B B L'2


E: (1/36)
```
    +---+---+---+      +---+---+---+
    | B |   | A |      | A |   | B |
    +---+---+---+      +---+---+---+
    |   |Fx |   |  »   |   |Fx |   |
    +---+---+---+      +---+---+---+
    | D |   | C |      | C |   | D |
    +---+---+---+      +---+---+---+
```

Algo: F R'F'L F R  F'L²B'R B L B'R'B

    F  R'
    F'    L
    F  R
    F'    L² B'
       R     B
          L  B'
       R'    B

* Mnemnic:
    * Symmetric movement - pretty much symmetric algo.
    * F (left to right),  right-towards
    * F (right to left),  left-towards
    * F (left to right),  right-away
    * F (right to left),  left-2-times,  back-left-to-right
    *                     right-away,    back-right-to-left
    *                     left-towards,  back-left-to-right
    *                     right-towards, back-right-to-left
    * F & B alternate,
    * R is outer-inner,
    * L is just one direction.
    * Both F & B start with right to left.
    * R starts with towards (to remember)
    * L is always towards

## Both edges and corners

### both 2

#### middle into corner line

T: (1/18)
```
    +---+---+---+      +---+---+---+
    | D |   |   |      | A |   |   |
    +---+---+---+      +---+---+---+
    | C |Fx | B |  »   | B |Fx | C |
    +---+---+---+      +---+---+---+
    | A |   |   |      | D |   |   |
    +---+---+---+      +---+---+---+
```

L²D F²D'L²B²D'R²D B² U'

    L2 D  F2
       D'
    L2       B2
       D'       R2
       D     B2
    U'

Mnemonic:
    Long Drive to France and Denmark
    Lost Bracelet
    Dont Recall
    Double Box
    Uncovered

* Note the orientation of T. Its on L side.
* All of L2, F2, R2, B2 are double.
* D is single, and follows D-D'-D'-D pattern


J: (1/9)
```
    +---+---+---+      +---+---+---+
    |   |   | D |      |   |   | A |
    +---+---+---+      +---+---+---+
    |   |Fx | C |  »   |   |Fx | B |
    +---+---+---+      +---+---+---+
    |   | B | A |      |   | C | D |
    +---+---+---+      +---+---+---+
```

B2 L  U L'B²R D'R D R²

    B2 L  U
       L'
    B2      R  D'
            R  D
            R2

Mnemonic:
    Big Leopard under Log             U-is in the meeting point of L (Both L&Utowards)
    Brown Rabbit Dunks                D-is same dir as U. (R is always away)
    Round Diamond Richochets          D-now opp.

* B is double.
* L is towards/away (L-L')
* D is towards/away (D-D')
* R is always away
* One U is towards.

#### parallel

F: (1/18)
```
    +---+---+---+      +---+---+---+
    | C | D |   |      | A | B |   |
    +---+---+---+      +---+---+---+
    |   |Fx |   |  »   |   |Fx |   |
    +---+---+---+      +---+---+---+
    | A | B |   |      | C | D |   |
    +---+---+---+      +---+---+---+
```

B L'F U²B'R B'F²D²F²R'B F' U2

    B  L' F  U2              back lit fit versa         towards-away-away-double
    B'          R            bend right                 away-away
    B'    F2       D2        black  face  dazzles       away-double-double
          F2    R'                  frigid ring         double-towards
    B     F' U2              bring  forth               towards-towards-double

* first half mostly away (except for begging B) - 5/7.
* The 3 doubles split the halfs
* Second half is towards

 (14,17,14,5) L²F'L D²R'B R D²L B L F L'B'
 (13,18,12,6) (U3)R'L F²L D'R F²L'U R²L'B²R²
 (13,17,12,6) (U2)B L'F U²B'R B'F²D²F²R'B F'
 (16,16,16,4) (U1)F R U'B U F'B'U B U'F R'F'R B'R'

V: (1/18)

```
    +---+---+---+      +---+---+---+
    |   |   | C |      |   |   | A |
    +---+---+---+      +---+---+---+
    |   |Fx | D |  »   |   |Fx | B |
    +---+---+---+      +---+---+---+
    | A | B |   |      | C | D |   |
    +---+---+---+      +---+---+---+
```

F'U F'U'R'D R'D'R²F'R'F R F

    F' U
    F' U'  R'  D
           R'  D'
           R2
    F'     R'
    F      R
    F

F' U F' U'
R' D R' D'
R2
F' R'
F  R F

* No Ls. Its just F-R (The main action sides) and U and D.
* F' and R' have a pattern and rhyme with U and D. (both u/d are u-u', d-d')
    * Mnemomic: "File Usefully for Urself, Read documents rightly doctor"
* R2 stops the rhyme.
* F' R' F R F

#### Cutting through

Y: (1/18)

```
    +---+---+---+      +---+---+---+
    | D | C |   |      | A | B |   |
    +---+---+---+      +---+---+---+
    | B |Fx |   |  »   | C |Fx |   |
    +---+---+---+      +---+---+---+
    |   |   | A |      |   |   | D |
    +---+---+---+      +---+---+---+
```

Bingo: F R  U'
         R' U'
         R  U
         R' F'
         R  U
         R' U'
         R' F
         R  F'
No need for mirror. Its just the same


N: (1/36)

```
    +---+---+---+      +---+---+---+
    |   | D | C |      |   | A | B |
    +---+---+---+      +---+---+---+
    |   |Fx |   |  »   |   |Fx |   |
    +---+---+---+      +---+---+---+
    | B | A |   |      | C | D |   |
    +---+---+---+      +---+---+---+
```
                                 Mirror
L D'B L'D²R F' R'D²L²B'L'D L'    L  D' B  L' D² R  F' R' D² L² B' L' D  L'
                                 R' D  B' R  D2 L' F  L  D2 R2 B  R  D' R

    L   D'  B                    R' D  B'
    L'  D2     R  F'             R  D2    L' F
               R'                         L
        D2                          D2
    L2      B'                   R2    B
    L'  D                        R  D'
    L'                           R


L D' B L' D2 - Long day But Love Donuts  -  towards, towards, towards away    double
R F'   R' D2 - Right for Royal   Drive      away     towards,         towards double
L2 B'        - Lets  Buy                    double   away
L' D L'      - Long  Double Laces           away     away  away

* first half is mostly towards, second half is all away.
* Long day starts towards
* Love-Right is away in first half

#### Disjoint

R: (1/9)
```
    +---+---+---+      +---+---+---+
    | B |   | A |      | A |   | B |
    +---+---+---+      +---+---+---+
    |   |Fx | D |  »   |   |Fx | C |
    +---+---+---+      +---+---+---+
    |   | C |   |      |   | D |   |
    +---+---+---+      +---+---+---+
```

F L U L'F L U'F U F U'F'L'F²

  F L U
    L'
  F L U'
  F   U
  F   U'
  F'
    L'
  F2

Flu-lasts-Flew
Fakir-until-Fall
Uganda-faces-Light-Freeze
* F is always towards except faces/freeze, whihc are away/double.
* L/U both start with towards. its both L-L'-L-L' and U-U'-U-U'.

### both 3

G: (2/9)                                     G: mirror:

```
   +---+---+---+      +---+---+---+             +---+---+---+      +---+---+---+
   | B | Y | C |      | A | X | B |             | A | Z | B |      | A | X | B |
   +---+---+---+      +---+---+---+             +---+---+---+      +---+---+---+
   | Z |Fx | X |  »   | Y |Fx | Z |             | X |Fx | Y |  »   | Y |Fx | Z |
   +---+---+---+      +---+---+---+             +---+---+---+      +---+---+---+
   |Fx |Fx | A |      |Fx |Fx | C |             | B |Fx |Fx |      | C |Fx |Fx |
   +---+---+---+      +---+---+---+             +---+---+---+      +---+---+---+
```

   F U F' L2 D' B U' B' U B' D L2               F' U' F R2 D B' U B U' B D' R2
Inverting:
   L2 D' B U' B U  B' D L2 F U' F'

To-ingrain:                                  To-ingrain:
Keep fixed on the fixed side:                Keep fixed on the fixed side:
    F-away                                       F-away
        U-towards                                    U-towards
        F-restore                                    F-restore
    L2-(Fx side)                                 L2-(Fx side)
    D-towards                                    D-towards
    B-towards                                    B-towards
        U-away                                       U-away
        B-opp (away)                                 B-opp
        U-opp (towards)                              U-opp
        B-opp (away)                                 B-opp
    D-opp     (away)                             D-opp
    L2                                           L2

away,towards,restore      ATR
double                    D
towards                   T
towards-away-opp-opp-opp  TAOOO (ATA)
restore (away)            A
double                    D

Mnemonic: at&t           , digital-tech-talk, aata, ad
          works on: FUF (ATT),
                    LDB (DTT)
                    UBUB (AATA)
                    DL   (AD)

Inverting:
   L2 D' B U' B U B' D L2 F U' F'

    L2 - Double Fx Side 
    D' - towards
    B  - towards
    U' - away
    B  - towards
    U  - towards
    B' - away
    D  - away
    L2 - double
    F  - away
    U' - away
    F' - towards

DTTA, TT, AAD, AAT

Drink That Tumbler of Alchohol, 
Think Tank
All Atoms  Discharged
All Air    Transformed
Works on:     LDBU  (DTTA)
              BU    (TT)
              BDL   (AAD)
              FUF   (AAT)


## Summary

legend:
» rotation other (Just replace U-U' or start algo reversed.)
* mirror   other
↔ symmetric algo - just one.

* U», Z↔, H↔  - Edge only stuff, the Mu algos.

* A*          - Corner only - triple turn, R'F-R'BBR algo.
* E↔          - Corner only - symmetric. Symmetric algo.

* G»*         - 3-corner/edge - AT&T,DigitalTechTalk,Ad.  DrintThatTumblerofAlchohol-ThinkTank-AllAtomDischarge-AllAirTransformed

* T↔          - Corner/Edge touching in. LongDriveToFranceDenmark
* J*          - Corner/Edge touching in. BigLeopardUnderLog

* R*          - Disjoint.  Flu..Fakir

* Y↔          - Cut across - F-RURU algo
* N*          - Cut across - Long-day-but-love-donuts

* V↔          - Parallel.  File usefully for urself
* F↔          - Parallel.  Back lit fit versa

# Yellow-face collateral damages


| Case              | Corners Damage            | Edge Damage          |
| ----------------- | ---------------           | -----------          |
| Regular fish      | opps exch                 | F-fixed, 3-anti-clck |
| Other   fish      | opps exch                 | F-fixed, 3-clk       |
| Chameleon car     | opp-exch                  | R-fixed, 3-anti-clk  |
| Chameleon         | BR-fix. other-3 clockwise | no-change            |
| Diagnals          | BR-fix. other-3 anti-clk  | no-change            |
| Headlights        | BR-fix. other-3 clockwise | no-change            |
| Double headlights | no change                 | F-fixed, 3-clk       | Only case of choice.
