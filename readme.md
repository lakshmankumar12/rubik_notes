# Rubik Notes

# Standard Moves

1. Get white cross
2. Get corner
3. Get edge in 2nd layer.

## Get Yellow Plus

Algo: F U R U' R' F
```
  +---+---+---+         +---+---+---+
  |   | A |   |         |   | C'|   |
  +---+---+---+         +---+---+---+
  | x | x | B |   --->  | x | x | A |
  +---+---+---+         +---+---+---+
  |   | C |   |         |   | B'|   |
  +---+---+---+         +---+---+---+
```

Algo: F R U R' U' F
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
                                    -
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
|  No  |  No Yellow Already  |  Name           |   Orient        |   Next step  |
| ---- | ------------------- | --------------- | --------------- | -------------|
|  1   |  1                  |  Regular fish   |    Std          |         (1)  |
|  2   |  1                  |  Other fish     |    Std          | RgrFsh  (2)  |
|  3   |  0                  |  Double Headlgt | Yellow on side  | RgrFsh  (2)  |
|  4   |  0                  |  Chameleon car  | Yellow on side  | RgrFsh  (2)  |
|  5   |  2                  |  HeadLight      | Hdl in front    | OtrFsh  (3)  |
|  6   |  2                  |  Chameleon      | Yellow in LFT   | OtrFsh  (3)  |
|  7   |  2                  |  Diagnol        | Yellow in LFT   | OthFsh  (3)  |

Basically, its always LFT corner of interest.
* If 1 yellow, then yellow faces up
* If 0 yellow, then yellow is on left side
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


# Getting 2nd layer and white corners in one shot.

## Easy cases

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

# Fridrich

## OLL

|  Case             |  algo                     | Start-pos         |   Reverse             |
| ----------------- | ------------------------- | ----------------- | --------------------- |
| Regular fish      | R  U  R' U  R  U  U  R'   | Yellow up in TFL  |   R U2 R' U' R U' R'  |
| Other   fish      | R' U' R  U' R' U' U' R    | Yellow up in RBL  |   R' U2 R U R' U R    |
| Headlights        | R2 D R' U2 R D' R' U2 R'  | Lights in F side  |   R U2 R D R' U2 R D' R2 |
| Chameleon         | X' R U R' D R U' R' D'    | Like Hdlght, and Yellow face in F | (see diagnol) |
| Diagnals          | X' D R U R' D' R U' R'    | Yellow side at TFL,L side         | (see chameleon) |
| Double headlights | R U R' U R U' R' U R U2 R'| Yellow on sides   |  R U2 R' U' R U R' U' R U' R' |
| Chameleon car     | R U2 R2 U' R2 U' R2 U2 R  | Yellow on sides   |  R' U2 R2 U R2 U R2 U2 R' |
