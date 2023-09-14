![First revision of multi-agent play](media/baseline_policy.gif)

# Credits

This is a extension of [slimevolleygym by hardmaru](https://github.com/hardmaru/slimevolleygym) with addition of multiple agents. 

The aim of this project is to achieve collaborative behaviour between slimes on each team, since the current implementation relies on the same baseline policy for each agent (mirrored across the net).

By: [Thomason Zhou](https://www.thzhou.com) and [Kai Ma](https://k78ma.github.io).

# TODO Experiments:
Environment/rules:
- [ ] Create environment from config file
- [ ] Wider environment / slower slimes to make game harder for single slime
- [ ] Limit team passes/touches (like volleyball max 3)
- [ ] Limit consecutive touches
- [ ] Limit teammate/opponent observations

Policy:
- [ ] Run two with the original policy on each side, then have additional ones be running the new policy, then run new policy on two and retrain the new policy again?
- [ ] We would need to train the second agent on each side at minimum, what are the effects of using the 'single player' trained agent with a newly trained one?
- [ ] Training one team under a single policy or each slime has its own policy?
- [ ] Just let it train naively because everyone knows everyone's position?

Implementation:
- [ ] EvoJAX training speed-up


# Installation

This is a working combination of dependencies for test_state.py. 

- gym                0.19.0
- pyglet             1.5.27
- numpy              1.25.0

To install dependencies, run 

```
pip install -e .
```

or

```
pip install <package_name>==<package_version>
```

To run the game with two agents on each side, type:
```python
python test_state.py
```

## Gym Version Issues

Depending on your installation method (pip), it might be necessary to install gym 0.19.0 manually. If pip is raising errors or installing the wrong version of gym, try [downloading gym 0.19.0 from pypi.org](https://pypi.org/project/gym/#history). 

Then, edit extras_require as shown in setup.py:

```python
extras_require={
    "extras": extras,
}
```

and then run:

```
python setup.py install --user
```

# What's New?

For now, agents have been modified to have different traits when unbalanced_traits is set to true in the Game class. 

Each slime can be controlled manually, using a set of 3 keys:

| Agent                | Unbalanced Mode     | Controls (Jump, Left, Right)|
| -------------------- | ------------------- | --------------------------- |
| agent_left           | speedy_x            | WAD                         |
| agent_left_2         | high_jump, slow_x   | TFH                         |
| agent_right          | speedy_x            | UP, LEFT, RIGHT             |
| agent_right_2        | high_jump, slow_x   | IJL                         |

