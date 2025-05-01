# r/AmITheTat Strategy (Round 2)

## Overview
**r/AmITheTat** is a competitive Iterated Prisoner's Dilemma strategy designed for Part 2 of the tournament. It balances early cooperation with unforgiving exploitation. The strategy mirrors the opponent’s behavior unless they defect, in which case they are permanently avoided.

## Behavior
- Cooperates on the first move with every opponent.
- Mimics the opponent’s previous move as long as they cooperate.
- If the opponent defects even once, the algorithm will begin defecting and search for a more cooperative opponent.
- Always defects on the final move of the interaction.
- Selects the next opponent based on cooperation rate and whether they have ever defected.

## Technical Compliance
- Stateless: no global variables or external memory.
- Pure function using only provided inputs (`opponent_id`, `my_history`, `opponents_history`).
- Conforms to all tournament constraints regarding memory, runtime, and opponent limits.

## Function Signature

```
def strategy_round_2(opponent_id: int, my_history: dict[int, list[int]], opponents_history: dict[int, list[int]]) -> tuple[int, int]:
```

## Return Value
A tuple:
- `move`: 1 for cooperate, 0 for defect.
- `next_opponent`: the ID of the next opponent to challenge.

## Style
Unforgiving, tactical, and optimized to farm maximum points while minimizing exposure to betrayal. Once trust is broken, it never returns.