:toc:

# Rubik Notes

# References

|  Link         | Explains          |
|-------------- | ----------------- |
| Best listing of all algo-steps                                                                                    | https://ruwix.com/the-rubiks-cube/algorithm/                                                                  |
| Basic steps                                                                                                       | http://lghttp.60951.nexcesscdn.net/80487FB/Downloads/resources/downloads/Rubiks_3x3_Solution_Guide1.pdf       |
| Alternate beginner method where yellow cross is set right, w/o doing yellow face and corners are permuted rightly | http://en.lerubikscube.com/how-to-solve-rubiks-cube/#Step_5_in_how_to_solve_the_Rubiks_cube_edges_permutation |
| Fridrich's first 2 layer explained best                                                                           | https://ruwix.com/the-rubiks-cube/advanced-cfop-fridrich/first-two-layers-f2l/                                |
| Fridrich's 2-Step OLL explained best.                                                                             | http://loki.ist.unomaha.edu/~jtrimm/project/ollpll.html                                                       |
| Fridrich's 2-Step PLL explained best                                                                              | https://play.google.com/store/apps/details?id=com.appstar.souvik_biswas.cube                                  |

# Standard Moves

1. Get white cross
2. Get corner
3. Get edge in 2nd layer.

## Get Yellow Cross

Algo: F U R U' R' F'
```
  +---+---+---+         +---+---+---+
  |   | A |   |         |   | C'|   |
  +---+---+---+         +---+---+---+
  | x | x | B |   --->  | x | x | A |
  +---+---+---+         +---+---+---+
  |   | C |   |         |   | B'|   |
  +---+---+---+         +---+---+---+
```

Algo: F R U R' U' F'
```
  +---+---+---+         +---+---+---+
  |   | B |   |         |   | A |   |
  +---+---+---+         +---+---+---+
  | x | x | A |   --->  | x | x | C'|
  +---+---+---+         +---+---+---+
  |   | C |   |         |   | B'|   |
  +---+---+---+         +---+---+---+
```

Thus, If you have:
```
  +---+---+---+
  |   | x |   | Use FUR-URF
  +---+---+---+
  | x | x |   |
  +---+---+---+
  |   |   |   |
  +---+---+---+

  +---+---+---+
  |   |   |   | Use FRU-URF
  +---+---+---+
  | x | x | x |
  +---+---+---+
  |   |   |   |
  +---+---+---+

  +---+---+---+
  |   |   |   | Use any of one, and the other one.
  +---+---+---+
  |   | x |   |
  +---+---+---+
  |   |   |   |
  +---+---+---+

No other possibility exists.
```

## Get yellow face

Algo: R U R' U R U U R'
```
    b       b                 r       f
  +---+---+---+             +---+---+---+
l | P | a | Q | r         R | f | b | S | l  * Edges undergo anti-clock shift except edge-c
  +---+---+---+             +---+---+---+    * Corners S&Q, P&R are swapped.
  | d | x | b |    -->      | a | x | d |    * S goes undisturbed w.r.t yellow face
  +---+---+---+             +---+---+---+    * Note the R-f, Q-r, P-b come on top.
l | S | c | R | r         b | r | c | b | P
  +---+---+---+             +---+---+---+
    f       f                 Q       l
```

Possible options:

```
  Regular fish.          Other Fish               Headlight
    -                               -
  +---+---+---+           +---+---+---+           +---+---+---+
  |   | x |   | |         | x | x |   |           | x | x | x |
  +---+---+---+           +---+---+---+           +---+---+---+
  | x | x | x |           | x | x | x |           | x | x | x |
  +---+---+---+           +---+---+---+           +---+---+---+
  | x | x |   |           |   | x |   | |         |   | x |   |
  +---+---+---+           +---+---+---+           +---+---+---+
            -               -                       -       -

  chameleon               Diagnols                Double Headlights
                                    -
  +---+---+---+           +---+---+---+           +---+---+---+
  | x | x | x |           | x | x |   |         | |   | x |   | |
  +---+---+---+           +---+---+---+           +---+---+---+
  | x | x | x |           | x | x | x |           | x | x | x |
  +---+---+---+           +---+---+---+           +---+---+---+
| |   | x |   | |       | |   | x | x |         | |   | x |   | |
  +---+---+---+           +---+---+---+           +---+---+---+


  Chameleon car
            -
  +---+---+---+
| |   | x |   |
  +---+---+---+
  | x | x | x |
  +---+---+---+
| |   | x |   |
  +---+---+---+
            -
```

So, if you have

|  No  |  No Yellow Already  |  Name           |   Orient        |   Next step  | Times to execute |
| ---- | ------------------- | --------------- | --------------- | -------------| ---------------- |
|  1   |  1                  |  Regular fish   |    Std          |              |   1              |
|  2   |  1                  |  Other fish     |    Std          | RgrFsh       |   2              |
|  3   |  0                  |  Double Headlgt | Yellow on side  | RgrFsh       |   2              |
|  4   |  0                  |  Chameleon car  | Yellow on side  | RgrFsh       |   2              |
|  5   |  2                  |  HeadLight      | Hdl in front    | OtrFsh       |   3              |
|  6   |  2                  |  Chameleon      | Yellow in LFU   | OtrFsh       |   3              |
|  7   |  2                  |  Diagnol        | Yellow in LFU   | OthFsh       |   3              |

Basically, its always LFU corner of interest.
* If 1 yellow, then yellow faces up
* If 0 yellow, then yellow is on left side (remember headlight on side, that's the case for Fridrich too)
* If 2 yellow, then yellow is facing you

## Get Yellow Corners right

* Align existing 2 matched corners. And F is the opp side.
* Otherwise, 2 diagnol corners will be matching. Then do it 2 times

### Algo
R' F R' B B R F' R' B B R R U'
### Menomic
* Radio-frequency, R' to begin with.
* R' B B R (the R' matches first R)
* F'       (this is opp to the R'-F you begin with)
* R' B B R
* R U' (this you will easily realize as you do)

## Get Yellow Edges right

### Algo
F F U L R' F F L' R U F F
### Mnemonic
* F-full, rolling on the floor laughing, ruff
* Basically, 2 F's and the U is in the direction of adjustment.
* L/R towards you first. and Against you next.
* The last U is easily visible.

# The other standard move.

* Same as regular until yellow cross (FRU-RUF)
* Now instead of targeting yellow-face, make sure the yellow edges are rightly in place with their color
    * you either have it all aligned or 2 adjacents ones are okay and other two aren't. No other possibility.
    * Keep the 2 aligned on R and B sides and do R-U-R'-U-R-U2-R'
    * This will align all yellow edges
* Now make sure all yellow corners are in place (but oriented anyway)
    * you either have it all aligned Or (one in place, and other 3 unaligned). No other possibility
    * You will have to do U R U' L' U R' U' L.
    * It will switch the 3. You have to do it one or two times
        ```
          +---+---+---+         +---+---+---+
          | A | . | B |         | B | . | C |
          +---+---+---+         +---+---+---+
          | . | . | . |   --->  | . | . | . |
          +---+---+---+         +---+---+---+
          | C | . | G |         | A | . | G |
          +---+---+---+         +---+---+---+
        ```
* Now Orient the yellow corners Correctly with yellow coming to top.
    * Algo: R U R' U R U2 R' L' U' L U' L' U2 L.
    * Note that the 2nd half is a mirror image of first half, which is the std step.
        ```
            B                     C
          +---+---+---+         +---+---+---+
        C | A | . | . |       A | B | . | . |
          +---+---+---+         +---+---+---+
          | . | . | . |   --->  | . | . | . |
          +---+---+---+         +---+---+---+
        Q | P | . | . |       P | R | . | . |
          +---+---+---+         +---+---+---+
            R                     Q
        ```
    * It will orient the left 2 corners. If your yellows are on F&B, you are done in one step.
    * Otherwise you will have to do this utmost 3 times.

# Fridrich

## white cross.

### 1st edge.

Assume its to come to F-D position

* Its in bottom layer
    * if its already properly aligned in bot layer - just rotate (1)
    * if its not aligned, skip this color
* Its in middle layer
    * Its in F-R or F-L, rightly aligned. Just rotate (1)
    * Its in F-R or F-L, not rightly aligned. Rotate to R-D/L-D and bring it to F-D (2)
    * Its in B-R or B-L, aligned to come to R/L. Bring to R-D/L-D and roate (2)
    * Its in B-R or B-L, aligned to come to B-D. Bring to B-D and roate (2)
* Its in top layer
    * White showing up. Rotate to F-U and bring to F-D. (2)
    * White on side, and its on R-F/L-F. Bring to F-R/F-L and rotate to F-D (2)
    * White on side, and its on F-U/B-U. Bring to R-F/L-F, rotate to F-R/F-L and rotate to F-D (3)

### 2nd edge

Assume F-D is in place.

#### You picked R-D color(L-D also is just image inverse)

* Its on Top layer
    * White on top. Just rotate to R-U and then to R-D (2)
    * White not on top. Rotate to U-B (basically opp face of F-D that is in place).
             Then to B-R and to R-D. (3)
* Middle layer
    * Its on B-R/F-R ready to come to R-D. Just rotate (1)
    * Its on B-R/F-R incorrectly aligned.
        * THe trick is to rotate D/D' in prep to take in B-R/F-R. get it in and restore D. (3)
    * Its on B-L.
        * Depening on alignment, bring to B-R, R-D (2) or
                                 U-B, U-R, R-D (3)
    * Its on F-L.
        * Depending on alignment, bring to U-L, U-R, R-D (3)
                                           B-L, U-B, U-R, R-D (4)
* Bot layer
    * Its on R-D wrongly aligned. Bring to B-R, B-U, R-U, R-D (4)
    * Its on B-D, L-D with white on botom. Bring to B-U/L-U, then to R-U, R-D (3)
    * Its on B-D, with white facing Back. Bring to B-R, R-D (2)
    * Its on L-D, white facing left. Bring to B-L, U-B, U-R, R-D (4)

So
* (1) B-R/F-R, white facing B/F.
* (2)
    * white on top,
    * B-L/B-D, white facing Back
* (3)
    * Lots
* (4)
    * R-D itself unaligned. You will have to pick it. As nothing else will disturb it.
    * F-L, facing L, let it wait
    * L-D, facing L, let it wait

#### You picked B-D color

* Its on Top layer
    * White on top. Just rotate to B-U and then to B-D (2)
    * White not on top. Bring to either R-U/L-U, then to R-B/L-B and to B-D. (3)
* Middle layer
    * Its on B-R/F-R ready to come to R-D. Just rotate (1)
    * Its on B-R/F-R incorrectly aligned.
        * THe trick is to rotate D/D' in prep to take in B-R/F-R. get it in and restore D. (3)
    * Its on B-L.
        * Depening on alignment, bring to B-R, R-D (2) or
                                 U-B, U-R, R-D (3)
    * Its on F-L.
        * Depending on alignment, bring to U-L, U-R, R-D (3)
                                           B-L, U-B, U-R, R-D (4)
* Bot layer


## Getting 2nd layer and white corners in one shot.

### Easy cases

```
      Simple Roll-over from F               Simple Roll-over from R

              R
        /---/---/---/                             /---/---/---/
       /   / F /   /|                            /   /   /   /|
      /---/---/---/ |                           /---/---/---/ |
     /   /   /   /| |                        F / R /   /   /| |
    /---/---/---/ |/|                         /---/---/---/ |/|
   /   /   / R /| | |                        /   /   / F /| | |
  +---+---+---| |/|/|                       +---+---+---| |/|/|
  |   |   |   |W|R| |                       |   |   |   |R|R| |
  |   |   | F |/|/| |                       |   |   | W |/|/| |
  +---+---+---| |R|/                        +---+---+---| |R|/
  |   | F |   |/| /                         |   | F |   |/| /
  +---+---+---| |/                          +---+---+---| |/
  |   | F |   | /                           |   | F |   | /
  +---+---+---|/                            +---+---+---|/

         R U R'                                 F' U' F

     Touching-Touching for F                 Touching-Touching for R

                                                             W
        /---/---/---/                             /---/---/---/
       /   /   /   /|                            /   /   / R /|
      /---/---/---/ |                           /---/---/---/ |
     /   /   /   /| |                          /   /   / R /|F|
    /---/---/---/ |/|                         /---/---/---/ |/|
   / F / F /   /| | |                        /   /   /   /|F| |
  +---+---+---| |/|/|                       +---+---+---| |/|/|
W |   |   |   | |R| |                       |   |   |   | |R| |
  | R | R |   |/|/| |                       |   |   |   |/|/| |
  +---+---+---| |R|/                        +---+---+---| |R|/
  |   | F |   |/| /                         |   | F |   |/| /
  +---+---+---| |/                          +---+---+---| |/
  |   | F |   | /                           |   | F |   | /
  +---+---+---|/                            +---+---+---|/
        R U' R'                                  F' U  F
```

### other cases

* Case of having both corner and edge on top layer.
    * The corner's top color matches the edge's top color
        * If they are touching-touching the right way, its the easy case.
        * If they are not touching-touching
            * Bring the corner first atop its corner position.
            * Move the corner to the side opp to the color on top.
            * Put corner down. Orient the edge so that you get the touching-touching position.
        * If they are touching-touching the wrong way:
            * Make the corner come to the top color's side. The edge is hence on the
                non-involved side.
            * Put corner down. Move edge 180. (You can also do just 90. But this maintains
                symm-with the white-on-top-case)
            * Bring corner back up. Now move corner 180 to other side. Put it down.
            * Bring edge to its desired position for touching-touching.
    * Corner's top is opposite to Edge's.
        * You target simple roll-over.
        * You can have either of
            * edge in right place - the simple rollover.
            * edge not touching
            * edge touching on either side
        * Start with cornet atop its position
        * In all of the above, put corner-down. Aligh edge to its right spot.
            * In edge not touching, you can choose to put corner down in any side.
            * In touching touching case, you will have to push in on the side where
              edge is touching, so that it goes out of way when you put corner down.
            * In all 3 cases, you will have to just move the edge 90-degress.
    * White on top
        * Align edge with its side.
            * Corner not-touching or corner touching and is in target-location.
                * Rotate edge away.
                * For corner-not-touching, bring corner on top of edge.
                    * you will have touch-touching case now.
                * For corner-touching/at-target-loc case, move corner 180.
                    * you will have simple rollover case.
            * Corner touching and is at the away side.
                * You can't rotate edge away, as that puts corner down.
                * Bring corner 180* to other side. Edge will goto non-involed side.
                * Put corner down. Move edge 180. Bring corner up
                * You are now in the non-touching case. Rotate edge away
                * Bring white 180* on top of edge. Restore.
                * You are in touching-touching case.
* If edge is on top and corner is in bottom layer.
    * Try to shoot for easy-case as you move up.
        * If white is down, it will never come up. So shoot for diff color
          to come on top and hence a simple rollover.
        * if white is on side, you can shoot for white to be on top. Just keep
          the edge on a non-touching way so that you can shoot for a simple
          touching-touching later.
          (Actually, if u can manage it you can shoot for touching-touching
           or simple-rollover directly, but its possible and not possible.
           So the time taken to check and decide is same as doing an extra
           step)
* If edge is in middle:
    * corner is on top - again try to get into one of the easy cases.
    * corner is down, take up another corner and come to this last. Chances are
      it will be gone away. Your worst case, is when this is the last corner
      and it is not aligned. Just bring it up and work on it.

Summary for white and edge both on top cases
* Diff color - 1 straightforward(simple rollover). Other 3 all easy. Shoot for simple-rollover
* Same color - Remember: Corner goes down.
*              1 straightforward(touching-touching).
               2 (both aren't touching) one-step away. Shoot for touching-touching
               1 (touching the wrong away). two-step away. Corner down on both sides.
* White top  - Remember: Aligh edge and move it away (2-step case starts other way, but
                         second-steps is this)
               2 straightforward (one step away) - Shoot for touching-touching
               1 straightforward (one step away) - touching-touching. shoot for rollover
               1 two-steps away. Shoot for touching touching.
               

## OLL

| Case              | algo                       | Start-pos                         | Reverse                      |
| ----------------- | -------------------------  | -----------------                 | ---------------------        |
| Regular fish      | R  U  R' U  R  U  U  R'    | Yellow up in TFL                  | R U2 R' U' R U' R'           |
| Other   fish      | R' U' R  U' R' U' U' R     | Yellow up in TBL                  | R' U2 R U R' U R             |
| Headlights        | R2 D R' U2 R D' R' U2 R'   | Lights in F side                  | R U2 R D R' U2 R D' R2       |
| Chameleon         | X' R U R' D R U' R' D'     | Like Hdlght, and Yellow face in F | (see diagnol)                |
| Diagnals          | X' D R U R' D' R U' R'     | Yellow side at TFL,L side         | (see chameleon)              |
| Double headlights | R U R' U R U' R' U R U2 R' | Yellow on sides                   | R U2 R' U' R U R' U' R U' R' |
| Chameleon car     | R U2 R2 U' R2 U' R2 U2 R   | Lights on sides                   | R' U2 R2 U R2 U R2 U2 R'     |

### Mnemonics

* Regular Fish : regular!
* Other   Fish : R direction start with towards you, instead of against you, and its U' instead of U
* Chameleon/Diagnol: Diagnol starts with D. Its RUR' - D - RU'R' - D'
* Double Hdl:
    * Total of 6 Rs
    * It goes same as regular until R-U-R'-U-R
    * Then instead of UU-R' as in regular, you have U'-R' (this finishes until regular), and one extra round U-R-U2-R'
  ```
    R  U
    R' U
    R  U'
    R' U
    R  U2
    R'
  ```
* Hdl:
    * 5 R-activities.
    * First is R2 and R' starts from 2nd. Also note R' at end
    * D is first. This is the only one to have D among last 3. And, there is no single U/U', when D is there.
    * D/U2 alternate
  ```
    R2 D
    R'   U2
    R  D'
    R'   U2
    R'
  ```
* Chameleon Car:
    * 5 R-activites. U' all the way. U'2 first and last U's in between.
    * There is no R' and U at all.
    * Remember symmetry - 3 R2 sandwiched between R. 2 U' sandwiched between U2.
        * The U2 is outer, and R2 is inner.
  ```
    R  U2
    R2 U'
    R2 U'
    R2 U2
    R
  ```

## PLL

### Corners

```

  +---+---+---+
  | A |   | B |
  +---+---+---+
  |   |   |   |
  +---+---+---+
  | C |   | D |
  +---+---+---+
```
* Swap C & D : R' F R' B B R F' R' B B R R
    * Historically, i remember is as radio-freq, RBBR, F', RBBR
    ```
            R'
        F   R'  B
                B
            R
        F'  R'  B
                B
            R
            R           <-- Visible
    ```
* Swap A & D : F R U' R' U' R U R' F' R U R' U' R' F R F'
    ```
                 F   0f
         R   U'      1
         R'  U'      2
         R   U       3u
         R'      F'  4f
         R   U       5u
         R'  U'      6
         R'      F   7f
         R       F'  8f
    ```
    * Dont forget its R'R in the End!
    * Start with F, then you have 4 pair's of R-R'. The first 3 are R-R', last is R'-R.
    * Its U'-U', U-F', U-U', F-F' for the pairs.

### Edges

```

  +---+---+---+
  |   | F |   |
  +---+---+---+
  | E |   | G |
  +---+---+---+
  |   | H |   |
  +---+---+---+
```
* Cycle E->G->H:  M M U' M U U M' U' M M
* Cycle E->H->G:  M M U  M U U M' U  M M
    * Mnemonic: Mu-mUm'-uM
    * cap for M2, U2, M2
    * {Mu, uM}'s u dir is opp to how you want.
* Swap F<->H, E<->G: M M U M M U      U M M U M M
    * Mnemonic: Mu-Mu-uM-uM
* Swap E<->F, G<->H: M M U M M U M' U U M M U U M'
    * Mnemonic: Mu-Mu m'u uM-Um'
    * {1-Mu, 2-Mu, 3-uM} same as opp. there is mu' in between and Um' for 4th.

# 5x5

http://rubik.rthost.org/5x5x5_disparity_algorithms.htm

1. Get the 3x3 faces.
    * First white
    * Then yellow
    * Then blue
    * Then red
2. The last 2 should be done for the plus first.
    * Plus right.
        * Keep the target cross pieces on right side in F and U faces.
        * Algo: Rr' F' Ll' Rr U Rr U' Ll Rr'
            * Mneomic: Its only Rr/Ll/F/U.
            * R-F-L, R-U-R, U-L-R
            * tow-inv-awy, away-reg-away, inv-tow-tow
        * Intuitive understanding of this algo
            * Pull down U-color to F-face. (R-towards)
            * Save the F-color that came down on FU position by doing a F'
            * Restore the pull. You gave away one F-color to U now!
            * Push up F-face on Left side. You are giving one more F-color to U.
            * Now do a U on top, so that your F-colors are on middle line.
            * Push R-side up. Now the tgt-U-color comes to U-face.
            * Do a U' so that this U comes to middle line and the 2 F-colors are on sides
            * Restore both sides! Voila.
    * Corners right
        * Rr U Rr' U Rr U U Rr'
        * Mnemonic: The standard algo. Yippee
3. Now get edges right.
    * Swap 2 edges: Algo: Ll' U2 Ll' U2 F2 Ll' F2 Rr U2 Rr' U2 (Ll')2
        * Intuitive/Mnemonic:
            * You are starting on UL side (F&B)                       FUR-1, BUR-2
            * Ll' to find out.
            * U2 moves it form UR to UL-side(F&B)              So its FUL-2, BUL-1
            * Ll'(away) move from UL to BL-side(U&D)              its BUL-2, BDL-1
            * U2 brings 2 alone to FUR(both are diag opp)             FUR-2, BDL-1
            * F2 brings 2 to DL side (F&B)                            FDL-2, BDL-1
            * Ll' brings both on FL side (U&D)                        FUL-2, FDL-1
            * F2 moves from FL to FR side(U&D)                        FUR-1, FDR-2
            * Rr moves from FR to UR side(F&B)                        BUR-1, FUR-2 (swapped at this point)
            * U2 moves from UR to UL side(F&B)                        FUL-1, BUL-2
            * Rr' to find out
            * U2 moves from UL to UR side(F&B)                        FUR-2, BUR-1
            * Ll'2 to find out.
        * Kind of its:
                * Ll' away
            * R to L
            * L to B
            * split one so that its diag opp.
            * again join them on DL-line
            * D to F
            * L to R
            * R to U
            * R to L
                * Rr' (towards)
            * L to R
                * Ll2
        * Front to back
            * FUR-1, BUR-2    1 in front, 2 in back
            * FUL-2, BUL-1    2 in front, 1 in back
            * BUL-2, BDL-1    2 on top,   1 in back-bot
            * FUR-2, BDL-1
            * FDL-2, BDL-1    2 in front, 1 in back
            * FUL-2, FDL-1    2 on top,   1 in bot
            * FUR-1, FDR-2    1 on top,   2 in bot
            * BUR-1, FUR-2    1 in back,   2 in front
            * FUL-1, BUL-2
            * FUR-2, BUR-1
    * Flip one edge: Rr2 B2 U2 Ll U2 Rr' U2 Rr U2 F2 Rr F2 Ll' B2 Rr2
