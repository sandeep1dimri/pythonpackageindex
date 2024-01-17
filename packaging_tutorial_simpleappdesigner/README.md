# packaging_tutorial

[![PyPI - Version](https://img.shields.io/pypi/v/packaging-tutorial.svg)](https://pypi.org/project/packaging-tutorial)
[![PyPI - Python Version](https://img.shields.io/pypi/pyversions/packaging-tutorial.svg)](https://pypi.org/project/packaging-tutorial)

-----

**Table of Contents**

- [Installation](#installation)
- [License](#license)
- [Steps](#Steps)

## Installation

```console
pip install packaging-tutorial-simpleappdesigner
```

## License

`packaging-tutorial` is distributed under the terms of the [MIT](https://spdx.org/licenses/MIT.html) license.

## Steps

1. install hatch `pip install hatch`.

2. Create file config.toml , to config name.

3. create sample project - `hatch --config config.toml new packaging_tutorial_simpleappdesigner`

4. Open pyproject.toml and change name = “packaging_tutorial_simpleappdesigner”

5. install `python -m pip install --upgrade build`

6. Add following to toml file in case missing:
[tool.hatch.build.targets.wheel]
packages = [“src/packaging_tutorial_simpleappdesigner"]

7. build the distribution  `python -m build`

8. Register at - https://test.pypi.org/, go to https://test.pypi.org/manage/account/, navigate to API tokens(2fa need to be enabled to get API token) ￼

9. Install twin - `python -m pip install --upgrade twine`

10. publish package to testpypi - `python -m twine upload --repository testpypi dist/*` , user enter  __token__ and password - enter api token from prior step(s).

11. Once successful - `pip install -i https://test.pypi.org/simple/ packaging_tutorial_simpleappdesigner`

Note: I had few trouble - had to redo step 7 , 9 and 10 few times(4), and when redoing need to elevate the version in __about__.py

12. Once 11 is successful, `python -m twine upload dist/*` - provide username =_token__ and password and api token created from https://pypi.org or 
`python -m twine upload dist/* --config-file pypirc` where username and password is in pypirc file.
