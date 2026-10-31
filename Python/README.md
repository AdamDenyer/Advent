# Python
This directory contains Python puzzle solutions in a Nix development shell.

### Setup
1. In the `Python` directory that contains `__main__.py` create a file called `.env`
2. Add the following contents to `.env`
```conf
YEAR = 2015
DAY = 25
RUN_ALL = True
USE_EXAMPLES = False
INPUT_PATH=/local/inputs/directory/
EXAMPLE_DIR=Examples/
SLASH=/
```
3. Replace the values of the settings as required
    - `YEAR` and `DAY` must point to a date with a matching Python file (i.e. `{INPUT_PATH}\{year}\day{day}.py`)
    - `RUN_ALL` determines whether `__main__.py` just runs the current day, or all days in the current year up to and including the current day
    - `USE_EXAMPLES` determines whether to use the example input files or the real ones
    - `INPUT_PATH` must contain the local path to the directory where input files are stored
    - `SLASH` sets which slash is used in filepaths and may need changing depending on the target OS

### Run
The following instructions are specific to the included Nix development shell, so either NixOS or the Nix package manager is required to follow these steps.
Other ways of running Python will still work fine though, and a 'requirements.txt' file is included to improve compatibility.
1. Open a terminal in the directory that contains `shell.nix`
2. Run `nix-shell` to open the development shell (or `nix-shell --pure` if `nix-shell` by itself causes issues by trying to auto-run programs from the parent desktop session)
3. Run Python commands as usual. For example:
    - `python __main__.py` runs the main application
    - `pytest` Runs all test definitions found within the `Python` directory and its subdirectories

### Python Version
The Nix shell in this directory is pinned to a specific nixpkgs commit for reproducibility of builds using the exact versions of Python and the required libraries.
To use newer versions, check for new commits at https://status.nixos.org and replace the commit ID in the URL in `shell.nix` (i.e. `https://github.com/NixOS/nixpkgs/archive/{commit-id}.tar.gz`).