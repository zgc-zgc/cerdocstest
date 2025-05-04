[ Certora Prover Documentation ![Logo](https://docs.certora.com/en/latest/_static/Certora_Logo_Black.svg) ](https://docs.certora.com/en/latest/index.html)
Contents
  * [Certora User’s Guide](https://docs.certora.com/en/latest/docs/user-guide/index.html)
    * [Installation](https://docs.certora.com/en/latest/docs/user-guide/install.html)
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
      * [Before and After Comparison](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#before-and-after-comparison)
        * [.spec files](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#spec-files)
        * [.conf files](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#conf-files)
      * [Steps](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#steps)
      * [Explanation](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#explanation)
      * [Troubleshooting](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#troubleshooting)
        * [Step 1 - Verify Local Language Detection](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#step-1-verify-local-language-detection)
        * [Step 2 - Verify GitHub Server Update](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#step-2-verify-github-server-update)
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
  * Syntax Highlighting on GitHub
  * [ View page source](https://docs.certora.com/en/latest/_sources/docs/user-guide/github_highlighting.md.txt)


# Syntax Highlighting on GitHub[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#syntax-highlighting-on-github "Link to this heading")
This guide explains how to improve syntax highlighting in your GitHub repository for Certora Prover [configuration](https://docs.certora.com/en/latest/docs/prover/cli/conf-file-api.html#conf-files) and [specification](https://docs.certora.com/en/latest/docs/cvl/index.html#cvl-language) files.
## Before and After Comparison[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#before-and-after-comparison "Link to this heading")
### .spec files[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#spec-files "Link to this heading")
A `.spec` file without highlighting will appear on GitHub (in dark mode) as:
![conf before highlighting](https://docs.certora.com/en/latest/_images/spec_without_highlighting.png)
After following the instructions on this guide it will look like:
![spec after highlighting](https://docs.certora.com/en/latest/_images/spec_with_highlighting.png)
### .conf files[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#conf-files "Link to this heading")
A `.conf` file without highlighting will appear on GitHub (in dark mode) as:
![conf before highlighting](https://docs.certora.com/en/latest/_images/conf_before_highlighting.png)
After following the instructions on this guide it will look like:
![conf after highlighting](https://docs.certora.com/en/latest/_images/highlighted_conf.png)
## Steps[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#steps "Link to this heading")
  1. Create a `.gitattributes` file in the root directory of your repository if it doesn’t exist.
  2. Append the following lines to the end of the `.gitattributes` file:


```
*.spec linguist-language=Solidity
*.conf linguist-detectable
*.conf linguist-language=JSON5

```
Copy to clipboard
  1. Commit and push the changes to your repository.
  2. Wait for GitHub to process the updates (this may take up to 24 hours).


## Explanation[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#explanation "Link to this heading")
The `.gitattributes` file instructs GitHub’s Linguist to classify `.spec` and `.conf` files with appropriate syntax highlighting:
`.conf` files are [JSON5](https://json5.org/) files with a different extension. Assigning them to JSON5 enables proper syntax highlighting.
`.spec` files use [CVL](https://docs.certora.com/en/latest/docs/cvl/index.html#cvl-language), which is currently unsupported by GitHub. However, since CVL shares significant syntax with Solidity, applying Solidity highlighting significantly improves readability compared to GitHub’s default.
## Troubleshooting[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#troubleshooting "Link to this heading")
### Step 1 - Verify Local Language Detection[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#step-1-verify-local-language-detection "Link to this heading")
To ensure `.gitattributes` was updated correctly, run the following command in your Git repository:
```
git check-attr linguist-language -- **/*.spec **/*.conf

```
Copy to clipboard
You should see output similar to:
```
path/to/file.spec: linguist-language: Solidity
path/to/file.conf: linguist-language: JSON5

```
Copy to clipboard
If the output shows `unspecified`, the `.gitattributes` file may be missing or incorrectly placed (it must be in the root directory of the repository).
```
CLIFlags/solc_via_ir.conf: linguist-language: unspecified

```
Copy to clipboard
### Step 2 - Verify GitHub Server Update[](https://docs.certora.com/en/latest/docs/user-guide/github_highlighting.html#step-2-verify-github-server-update "Link to this heading")
Run the following API query to confirm GitHub’s Linguist has updated the classification: `https://api.github.com/repos/YOUR-ORG/YOUR-REPO/languages` A successful update should return output similar to:
```
{
 "Solidity": 21038,
 "JSON5": 443
 ...
}

```
Copy to clipboard
If the response is an empty JSON (`{}`), ensure that:
  * The `.gitattributes` changes were pushed.
  * There are no conflicting `.gitattributes` rules that override the new settings.


[ Previous](https://docs.certora.com/en/latest/docs/user-guide/ci.html "CI Configuration") [Next ](https://docs.certora.com/en/latest/docs/user-guide/glossary.html "Glossary")
© Copyright 2025, Certora, Inc.
Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx_rtd_theme) provided by [Read the Docs](https://readthedocs.org). 
