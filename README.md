# labscript suite installer

A script to install the labscript suite onto a system.

([view on Bitbucket](https://bitbucket.org/labscript_suite/installer))

## usage:
    python setup.py (install | uninstall | build [--keep-hg] | clean)

## `install`
Copies the bundled labscript suite packages and directories to a chosen install
directory, adds them to Python's search path, and creates application shortcuts.
        
## `uninstall [<path>]`
The installer copies itself into the install directory as well, and can be used
to later uninstall the labscript suite. Removes labscript directories from Python's
search path, removes application shortcuts and deletes the contents of the install
directory, except for the userlib directory and non-default config files.
        
## `build [--keep-hg]`
Clones the labscript repositories from btbucket, deletes .hg* files, and bundles
everything into a zip file along with setup.py itself.
Which revisions are used can be set in setup.py, but defaults to
`max(branch(default) and tag())`
which means the most recent tagged revision in the default branch. Since we use tags
for version numbers only, this will use the latest stable release of each package.
The `--keep-hg` option does not remove repository information before bundling packages
into the output zip files. This means the resulting install will contain mercurial
repositories - this could be useful for developers.

## `clean`
Removed the build directory, if any.