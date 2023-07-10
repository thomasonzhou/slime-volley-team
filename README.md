![First revision of multi-agent play](media/baseline_policy.gif)

This is a working combination of dependencies for test_state.py

- gym                0.19.0
- pyglet             1.5.27
- numpy              1.25.0

To run the game with two agents on each side, type:
```python
python test_state.py
```

For now, agents have been modified to have different traits when unbalanced_traits is set to true in the Game class. 

Each slime can be controlled manually, using a set of 3 keys:

| Agent                | Unbalanced Mode     | Controls (Jump, Left, Right)|
| -------------------- | ------------------- | --------------------------- |
| agent_left           | speedy_x            | WAD                         |
| agent_left_2         | high_jump, slow_x   | TFH                         |
| agent_right          | speedy_x            | UP, LEFT, RIGHT             |
| agent_right_2        | high_jump, slow_x   | IJL                         |

