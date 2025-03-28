# The RobinLe C/C++ Development Environment
This repository contains some global code for all my C/C++ repositories.

> [!NOTE]
> At the moment, the configuration is 90% made for Microsoft Visual C++
> project files (`.sln`, `.vcxproj`) of a UNIX-style directory
> structure, see below.
>
> However, I recently started using CMake for new projects. This repo
> will most likely change a lot in the near future.


## Visual Studio Editor Configuration (`.editorconfig` file)

There is `spaces.editorconfig` that uses four spaces as indentation and
`tabs.editordconfig` that uses tabs (`\t`) as indentation.

Copy one of those files as `.editorconfig` in a parent directory of C++
projects to automatically apply the included code formatting settings.


## Git Files (`.gitattributes`,  `.gitignore`)
These are configured for C/C++ and my default (UNIX-style) directory structure and located in the
root directory of my C/C++ repos.


## Environment Variables + Directory Structure
When repositories use one of my libraries, it's usually not via a submodule (as, IMHO, dealing with
those is very troublesome at times), but via an environment variable that points to a directory
containing the header directories (I use symbolic links to my local repository directories), release
`.dll` files and the `.lib` files.

The environment variable in question is named `RobinLeApps`.

See this illustration for the directory structure required by my repositories:
```
%RobinLeApps%
 ├───dll
 │   └─── <release versions of DLLs (.dll, .pdb)>
 ├───include
 │   └─── <include subdirectories, like "rlText">
 ├───lib
 │   ├───Debug
 │   │   └─── <debug versions of static libraries (.lib, .idb, .pdb)>
 │   ├───Release
 │   │   └─── <release versions of static libraries (.lib, .pdb)>
 │   └ <import libraries (.lib, .exp)>
 └ <release versions of executables (.exe, .pdb)>
```