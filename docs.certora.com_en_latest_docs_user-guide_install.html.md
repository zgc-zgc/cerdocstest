[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
      * [Step 1: Prerequisites](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-1-prerequisites)
      * [Step 2: Install the Certora Prover package](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-2-install-the-certora-prover-package)
      * [Installing the beta version (optional)](https://docs.certora.com/en/latest/docs/user-guide/install.html#installing-the-beta-version-optional)
      * [Step 3: Set the personal access key as an environment variable](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-3-set-the-personal-access-key-as-an-environment-variable)
      * [Step 4 (for GitHub users): Configure Syntax Highlighting](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-4-for-github-users-configure-syntax-highlighting)
    * [Installing an EVM compiler and VS Code Extension](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html)
    * [Tutorial and Workshops](https://docs.certora.com/en/latest/docs/user-guide/tutorials.html)
    * [Running the Certora Prover](https://docs.certora.com/en/latest/docs/user-guide/running.html)
    * [Designing Good Specifications](https://docs.certora.com/en/latest/docs/user-guide/properties/index.html)
    * [Producing Positive Examples](https://docs.certora.com/en/latest/docs/user-guide/satisfy.html)
    * [Invariants](https://docs.certora.com/en/latest/docs/user-guide/invariants.html)
    * [Parametric rules](https://docs.certora.com/en/latest/docs/user-guide/parametric.html)
    * [Tracking changes with ghosts and hooks](https://docs.certora.com/en/latest/docs/user-guide/ghosts.html)
    * [Specification Design Patterns](https://docs.certora.com/en/latest/docs/user-guide/patterns/index.html)
    * [Using Opcode Hooks](https://docs.certora.com/en/latest/docs/user-guide/opcodes.html)
    * [Working with Multiple Contracts](https://docs.certora.com/en/latest/docs/user-guide/multicontract/index.html)
    * [Managing Timeouts and Out of Memory Problems](https://docs.certora.com/en/latest/docs/user-guide/out-of-resources/index.html)
    * [Understanding gaps between high and low level code](https://docs.certora.com/en/latest/docs/user-guide/gaps.html)
    * [Checking Specifications](https://docs.certora.com/en/latest/docs/user-guide/checking.html)
    * [CI Configuration](https://docs.certora.com/en/latest/docs/user-guide/ci.html)
    * [Syntax Highlighting on GitHub](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html)
    * [Glossary](https://docs.certora.com/en/latest/docs/user-guide/glossary.html)
  * [The Certora Verification Language](https://docs.certora.com/en/latest/docs/cvl/index.html)
  * [The Certora Prover](https://docs.certora.com/en/latest/docs/prover/index.html)
  * [Sunbeam: Verification for Soroban](https://docs.certora.com/en/latest/docs/sunbeam/index.html)
  * [The Certora Solana Prover](https://docs.certora.com/en/latest/docs/solana/index.html)
  * [Gambit: Mutation Generator for Solidity](https://docs.certora.com/en/latest/docs/gambit/index.html)


Additional information
  * [The Certora Equivalence Checker](https://docs.certora.com/en/latest/docs/equiv-check/index.html)
  * [Certora Technology White Paper](https://docs.certora.com/en/latest/docs/whitepaper/index.html)


  * [Index](https://docs.certora.com/en/latest/genindex.html)


[Certora Prover Documentation](https://docs.certora.com/en/latest/index.html)
  * [](https://docs.certora.com/en/latest/index.html)
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
  * Installation
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/install.md.txt)


# Installation[](https://docs.certora.com/en/latest/docs/user-guide/install.html#installation "Link to this heading")
## Step 1: Prerequisites[](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-1-prerequisites "Link to this heading")
Python3.8.16 or newer
Check your Python3 version by executing the following command on the terminal:
```
python3--version

```
Copy to clipboard
If the version is < 3.8.16, follow the [Python installation guide](https://wiki.python.org/moin/BeginnersGuide/Download) to upgrade.
Java Development Kit (JDK) 11 or newer
Check your Java version by executing the following command on the terminal:
```
java-version

```
Copy to clipboard
If the version is < 11, download and install Java version 11 or later from [Oracle](https://www.oracle.com/java/technologies/downloads/).
Solidity compiler (ideally v0.5 and up)
  * We recommend using [solc-select](https://github.com/crytic/solc-select) to download and switch between Solidity compiler versions.
  * You can also download the Solidity compiler binaries from the [official Solidity repository](https://github.com/ethereum/solidity/releases) on GitHub. It is best to place all the `solc` binaries in the same path.
  * Certora employees can clone the `CVT_Executables` repository suitable for their OS from [GitHub](https://github.com/orgs/Certora/repositories).


## Step 2: Install the Certora Prover package[](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-2-install-the-certora-prover-package "Link to this heading")
Tip
It is always recommended to use a Python virtual environment, such as [venv](https://docs.python.org/3.10/library/venv.html) or [virtualenv](https://virtualenv.pypa.io/en/latest/), when installing a Python package.
Execute the following command at the terminal to install the Prover:
```
pip3installcertora-cli

```
Copy to clipboard
Caution
Note that the terminal may prompt you with a warning that some files, e.g. python3.x, are not included in the `PATH`, and should be added. Add these files to `PATH` to avoid errors.
The following section presents some, but maybe not all, possible warnings that can arise during installation and how to deal with them:
Troubleshooting warnings
macOS
The warning[](https://docs.certora.com/en/latest/docs/user-guide/install.html#id2 "Link to this code")
```
The script certoraRun is installed in /Users/<user name>/Library/Python/3.8/bin
which is not on PATH. Consider adding this directory to PATH.

```
Copy to clipboard
  * Open a terminal and move to the `etc/paths.d` directory from root:
```
cd/etc/paths.d

```
Copy to clipboard
  * Use root privileges to create a file with an informative name such as `PythonForProver`, and open it with your favorite text editor:
```
sudonanoPythonForProver

```
Copy to clipboard
  * Write the specified path from the warning:
```
/specified/path/in/warning

```
Copy to clipboard
  * If needed, more than one path can be added on a single file, just separate the path with a colon (`:`).
  * Quit the terminal to load the new addition to `$PATH`, and reopen to check that the `$PATH` was updated correctly:
```
echo$PATH

```
Copy to clipboard


Linux
The warning[](https://docs.certora.com/en/latest/docs/user-guide/install.html#id3 "Link to this code")
```
The script certoraRun is installed in /home/<user name>/.local/bin
which is not on PATH. Consider adding this directory to PATH.

```
Copy to clipboard
  * Open a terminal and make sure you’re in the home directory:
```
cd~

```
Copy to clipboard
  * open the .profile file with your favorite text editor:
```
nano.profile

```
Copy to clipboard
  * At the bottom of the file, add to `PATH="..."` the specified path from the warning. To add an additional path just separate with a colon (:) :
```
PATH="$PATH:/specified/path/in/warning"

```
Copy to clipboard
  * You can make sure that the file was modified correctly by opening it again with the text editor:
```
nano.profile

```
Copy to clipboard
  * Make sure to apply the changes to the `$PATH` by executing the script:
```
source.profile

```
Copy to clipboard


## Installing the beta version (optional)[](https://docs.certora.com/en/latest/docs/user-guide/install.html#installing-the-beta-version-optional "Link to this heading")
If you wish to install a pre-release version, you can do so by installing `certora-cli-beta` instead of `certora-cli`. We do not recommend having both packages installed simultaneously, so you should remove the `certora-cli` package before installing `certora-cli-beta`:
```
pipuninstallcertora-cli
pipinstallcertora-cli-beta

```
Copy to clipboard
If you wish to easily switch between the beta and the production versions, you can use a [python virtual environment](https://virtualenv.pypa.io/en/latest/):
```
pipinstallvirtualenv
virtualenvcertora-beta
sourcecertora-beta/bin/activate
pip3installcertora-cli-beta

```
Copy to clipboard
You can then switch to the standard CVL release by running `deactivate`, and back to the beta release using `certora-beta/bin/activate`.
## Step 3: Set the personal access key as an environment variable[](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-3-set-the-personal-access-key-as-an-environment-variable "Link to this heading")
The Certora Prover requires a personal access key. You can get a free personal access key by registering on the [Certora website](https://www.certora.com/signup?plan=prover).
Before running the Prover, you should register your access key as a system variable. To do so on macOS or Linux machines, execute the following command on the terminal:
```
exportCERTORAKEY=<personal_access_key>

```
Copy to clipboard
This command sets a temporary variable that will be unset once the terminal is closed. We recommended storing the access key in an environment variable named `CERTORAKEY`. This way, you will no longer need to execute the above command whenever you open a terminal. To set an environment variable permanently, follow the next steps:
macOS
  * Open a terminal and make sure you’re in the home directory:
```
cd~

```
Copy to clipboard
  * Create a file with the name `.zshenv` and open it with your favorite text editor:
```
nano.zshenv

```
Copy to clipboard
  * Write the export command from the beginning of step 3, save and quit (`ctrl+x` on `nano`).
  * You can make sure that the file was created correctly by seeing it listed on the directory or by opening it again with the text editor:
```
ls-a

```
Copy to clipboard
OR
```
nano.zshenv

```
Copy to clipboard
  * Make sure to apply the environment variable you’ve just created by executing the script:
```
source.zshenv

```
Copy to clipboard


When running the Certora Prover in the Visual Studio Code Extension, you may need to restart VSCode or your computer.
Linux
  * Open a terminal and make sure you’re in the home directory:
```
cd~

```
Copy to clipboard
  * open the .profile file with your favorite text editor:
```
nano.profile

```
Copy to clipboard
  * At the bottom of the file, under the `PATH="..."` insert the export command from the beginning of step 3, save and quit (`ctrl+x` on `nano`).
  * You can make sure that the file was modified correctly by opening it again with the text editor:
```
nano.profile

```
Copy to clipboard
  * Make sure to apply the environment variable you’ve just created by executing the script:
```
source.profile

```
Copy to clipboard


## Step 4 (for GitHub users): Configure Syntax Highlighting[](https://docs.certora.com/en/latest/docs/user-guide/install.html#step-4-for-github-users-configure-syntax-highlighting "Link to this heading")
[Follow our guide](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html) to configure syntax highlighting on GitHub for CVL and configuration files.
[ Previous](https://docs.certora.com/en/latest/docs/user-guide/index.html "Certora User’s Guide") [Next ](https://docs.certora.com/en/latest/docs/user-guide/install_evm_compiler.html "Installing an EVM compiler and VS Code Extension")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
