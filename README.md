# WIP Fork of Unity ML-Agents Trainers

This fork is used for my master thesis and is used in conjuntion? with git:AIBattleSim.

Current changes:
* updated requirements in setup and this readme lol, but i just started haha

Quote:
The `mlagents` Python package is part of the
[ML-Agents Toolkit](https://github.com/Unity-Technologies/ml-agents). `mlagents`
provides a set of reinforcement and imitation learning algorithms designed to be
used with Unity environments. The algorithms interface with the Python API
provided by the `mlagents_envs` package. See [here](../docs/Python-LLAPI.md) for
more information on `mlagents_envs`.

The algorithms can be accessed using the: `mlagents-learn` access point. See
[here](../docs/Training-ML-Agents.md) for more information on using this
package.

## Setup

1. Create venv: $ python3.9 -m venv venv (I used python 3.9)
2. Activate venv: $ source venv/bin/activate (different commands for each os, i used mac)
3. Verify: $ python >>> import sys; sys.prefix != sys.base_prefix
4. Upgrade pip: $ python -m pip install --upgrade pip
5. Install requirements: $ python setup.py install
6. Add this project to path: $ export PYTHONPATH=/Users/wehrenberger/Coding/Personal/Unity/ml-agents-py-fork/ (the folder where mlagents/ is inside)

Rinse and repeat:
7. Run $ python /trainers/learn.py
8. Fix damn dependency issues, for me usually 1 or 2 missing installs. Weidly enough not deterministic. Use $ python -m pip install 'package'  

Alt: Works suprisingly well if opened with pycharm. It should ask u to create the venv itself and then proceed to install all reqs. Watch out for errors and install missing dependencies on ur own
 
## Watch out for

1. mlagents_env listens to port 5005, check conflicting ports on error
2. If you have to install mlagents_envs on your own use version 0.30.0

...
- ml-agents was installed in the setup maybe or by pycharm, which dont want because this is a fork
- uninstall it, python -m pip uninstall ml-agents fixed the other failed requirements 
- had to install myself: cattrs, torch, mlagents_envs after removing it
- protobuf==3.20.2 works with onnx and we dont get the stupid protobuff error which might kill performance
