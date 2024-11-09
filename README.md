# The pivot-submodule-git-dir utility

Fix problems derived from the Git submodules' ".git" directory not being the real Git repository directory.

<https://gitlab.com/brlin/pivot-submodule-git-dir>  
[![The GitLab CI pipeline status badge of the project's `main` branch](https://gitlab.com/brlin/pivot-submodule-git-dir/badges/main/pipeline.svg?ignore_skipped=true "Click here to check out the comprehensive status of the GitLab CI pipelines")](https://gitlab.com/brlin/pivot-submodule-git-dir/-/pipelines) [![GitHub Actions workflow status badge](https://github.com/brlin-tw/pivot-submodule-git-dir/actions/workflows/check-potential-problems.yml/badge.svg "GitHub Actions workflow status")](https://github.com/brlin-tw/pivot-submodule-git-dir/actions/workflows/check-potential-problems.yml) [![pre-commit enabled badge](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white "This project uses pre-commit to check potential problems")](https://pre-commit.com/) [![REUSE Specification compliance badge](https://api.reuse.software/badge/gitlab.com/brlin/pivot-submodule-git-dir "This project complies to the REUSE specification to decrease software licensing costs")](https://api.reuse.software/info/gitlab.com/brlin/pivot-submodule-git-dir)

## The problem

Git submodules can't be easily mounted into a VM or container without breaking the Git functionality within the VM or container.

## The workaround

The utility program provided by this solution swaps the actual Git repository directory of the submodule back to the ".git" directory entry of the submodule worktree, while maintaining a symbolic link from the original location to maintain functionality of basic Git operations(commit/log).

## Limitation

Note that as Git itself isn't aware of the change the submodule will become broken when path-related changes are made to the submodule, we expect the user to aware of this limitation and interact with it accordingly.

## Installatioon

Follow the following instructions to install the product:

1. Download the release archive of the product from [the Releases page](https://gitlab.com/brlin/pivot-submodule-git-dir/-/releases).
1. Extract the release archive using your preferred archive manipulation application/program.
1. Install [the pivot-submodule-git-dir program](pivot-submodule-git-dir) to the .local/bin sub-directory of your home directory, ensure the installed program has executable Unix file permission set.
1. Ensure the "${HOME}/.local/bin" directory is in your command search PATHs.

## Usage

Follow the following instructions to use the product:

1. Launch your preferred text terminal.
1. Change the working directory to the submodule worktree directory you wish to operate on.
1. Run the following command to start the operation:

    ```bash
    pivot-submodule-git-dir
    ```

## Licensing

Unless otherwise noted(individual file's header/[REUSE.toml](REUSE.toml)), this product is licensed under [the 3.0 version of the GNU Affero General Public License](https://www.gnu.org/licenses/agpl-3.0.en.html), or any of its more recent versions of your preference.

This work complies to [the REUSE Specification](https://reuse.software/spec/), refer to the [REUSE - Make licensing easy for everyone](https://reuse.software/) website for info regarding the licensing of this product.
