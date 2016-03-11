# git-submodule-gizmos
GIT extensions for interacting with submodules.

In order to use these scripts as new git subcommands, they need to be available in your PATH. You can either copy/link the scripts to ```~/bin``` or ```/usr/local/bin``` or configure your environment to include the ```git-submodule-gizmos/bin``` directory:
```export PATH=$PATH:~/git-submodule-gizmos/bin```

# commands
* git subcheckout -> chekout submodules on the specified branch and commit
* ... 

#### git subcheckout
Checks out the branch and commit of the submodule (does not leave you in a detached HEAD). Intended to simplify cloning repositories with many submodules for development.

In order to support this, the branch needs to be recorded in ```.gitmodules```:
```
[submodule "some-submodule"]
	path = some-submodule
	url = git@github.com:somewhere/somerepository.git
	branch = master
```
The command needs to be run in the root of the main repository, recursion is not supported.

```user@machine:~/some-main-repository $ git subcheckout```

Optionally a single submodule can be specified as an argument.

```user@machine:~/some-main-repository $ git subcheckout a_specific_submodule```
