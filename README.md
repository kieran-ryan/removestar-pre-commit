# removestar-pre-commit

[![image](https://badge.fury.io/py/removestar.svg)](https://pypi.org/project/removestar/)
[![image](https://img.shields.io/pypi/l/removestar)](https://pypi.python.org/pypi/removestar)
[![image](https://img.shields.io/pypi/pyversions/removestar.svg)](https://pypi.python.org/pypi/pyprojectsort)
[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/kieran-ryan/removestar-pre-commit/main.svg)](https://results.pre-commit.ci/latest/github/kieran-ryan/removestar-pre-commit/main)

A [pre-commit](https://pre-commit.com/) hook for [removestar](https://github.com/asmeurer/removestar).

Distributed as a standalone repository to enable installing `removestar` via prebuilt wheels from
[PyPI](https://pypi.org/project/removestar/).

### Using removestar with [pre-commit](https://pre-commit.com)

Add this to your `.pre-commit-config.yaml`:

```yaml
- repo: https://github.com/kieran-ryan/removestar-pre-commit
  rev: 1.3.1
  hooks:
    - id: removestar
      args: [-i, <source_code_dir>]
```

To run the hook on Jupyter Notebooks too:

```yaml
- repo: https://github.com/kieran-ryan/removestar-pre-commit
  rev: 1.3.1
  hooks:
    - id: removestar
      args: [-i, <source_code_dir>]
      types_or: [python, pyi, jupyter]
```

Removestar's pre-commit hook should be placed after other formatting tools, such as Black and isort,
_unless_ you enable autofix, in which case, removestar's pre-commit hook should run _before_ Black, isort,
and other formatting tools, as removestar's autofix behaviour can output code changes that require
reformatting.

## License

`removestar-pre-commit` is licensed under the [MIT License](https://opensource.org/licenses/MIT).
