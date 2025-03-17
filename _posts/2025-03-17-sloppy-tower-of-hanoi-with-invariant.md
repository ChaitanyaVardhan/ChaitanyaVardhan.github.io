I got lost playing Towers of Hanoi with more than 3 discs—4 or 5 and gave up solving manually. But, a manual solution although sloppy is possible if the player maintains an invariant: The disc above is strictly smaller to the disc below for each tower. In this way, Hanoi seems related to the Convex Hull problem: If you have 2 small hulls you can get a bigger hull by merging those 2. If you have 2 small valid towers you can get a bigger tower. All that is needed is that an invariant is maintaited in every move.

#### The Setup
- **Discs**: D1 < D2 < D3 < D4 < D5 (smallest to largest).
- **Start State**:
  - Peg 1: [D2, D4] (top to bottom)
  - Peg 2: [D1, D3, D5]
  - Peg 3: []
- **Rule**: Always stack so the disc above is smaller than the disc below (e.g., D2 on D4, not D4 on D2).
- **Goal**: Get all discs to Peg 3 as [D1, D2, D3, D4, D5], sloppy moves allowed.

## The Sloppy Solve
Starting from [D2, D4] | [D1, D3, D5] | [], I moved discs randomly but legally. Here’s the path (each triplet is Peg 1 | Peg 2 | Peg 3):

`[d2d4] | [d1d3d5] | []`

`[d4] | [d1d3d5] | [d2]`

`[d4] | [d3d5] | [d1d2]`

`[d3d4] | [d5] | [d1d2]`

`[d1d3d4] | [d5] | [d2]`

`[d1d3d4] | [d2d5] | []`

`[d3d4] | [d2d5] | [d1]`

`[d2d3d4] | [d5] | [d1]`

`[d1d2d3d4] | [] | [d5]`

`[d2d3d4] | [] | [d1d5]`

`[d3d4] | [d2] | [d1d5]`

`[d3d4] | [d1d2] | [d5]`

`[d4] | [d1d2] | [d3d5]`

`[d4] | [d2] | [d1d3d5]` 

`[d1d4] | [d2] | [d3d5]`

`[d1d4] | [] | [d2d3d5]`

`[d4] | [d1] | [d2d3d5]`

`[d4] | [] | [d1d2d3d5]`

`[d1d4] | [] | [d2d3d5]`

`[d1d4] | [d2] | [d3d5]`

`[d4] | [d1d2] | [d3d5]`

`[d3d4] | [d1d2] | [d5]`

`[d1d3d4] | [d2] | [d5]`

`[d1d3d4] | [] | [d2d5]`

`[d3d4] | [d1] | [d2d5]`

`[d3d4] | [] | [d1d2d5]`

`[d4] | [d3] | [d1d2d5]`

`[d1d4] | [d3] | [d2d5]`

`[d1d4] | [d2d3] | [d5]`

`[d4] | [d1d2d3] | [d5]`

`[] | [d1d2d3] | [d4d5]`

`[d1] | [d2d3] | [d4d5]`

`[d1] | [d3] | [d2d4d5]`

`[] | [d1d3] | [d2d4d5]`

`[d2] | [d1d3] | [d4d5]`

`[d1d2] | [d3] | [d4d5]`

`[d1d2] | [] | [d3d4d5]`

`[d2] | [d1] | [d3d4d5]`

`[] | [d1] | [d2d3d4d5]`

`[] | [] | [d1d2d3d4d5]`

37 moves—way over 31—but it worked! Done manually. D1 bounced around like a pinball, yet the invariant held: no D4 on D3, no D2 on D1. Every state was valid, and I hit the goal.

## Why It Works
Hanoi’s state space is forgiving—if you start legal and stay legal, you can reach any legal end. The monks in that Indian temple legend? I’d take over their 64-disc gig and bumble to the end—world saved, messily.
