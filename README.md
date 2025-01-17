# Setup

Simply install the plugin in your environment. Until a version is published to PyPI, use:
```
pip install git+https://github.com/b12consulting/hydra_paired_sweeper.git
```

# Usage

Using this sweeper in Hydra multirun mode will sweep over multiple parameters in parallel,
such as a python `zip` would:

```
python your_app.py hydra/sweeper=paired --multirun
```

With the new configuration format, you can specify the sweep as:

```yaml
hydra:
  sweeper:
    params:
      - paramA: 10
        paramB: 2
      - paramA: 50
        paramB: 3
```

Will create two runs, one with `paramA=10 paramB=2` and the other with `paramA=50 paramB=3`.
