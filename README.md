# vtk-builds

Automatic builds of [VTK](https://vtk.org) built with
[github actions](https://github.com/features/actions), for several
architectures:

|        SO        |   Arch    |
| :--------------: | :-------: |
|  windows-latest  |  x86_64   |
|  macOS-latest    |  x86_64   |
|  ubuntu-22.04    |  x86_64   |
|  ubuntu-22.04    |  arm-v7   |
|  ubuntu-22.04    |  aarch64  |
|  ubuntu-22.04    |  s390x    |
|  ubuntu-22.04    |  ppc64le  |

## Why do I need this?

### Stand-alone distributable packages

First, you can find the static libraries among the
[released files](https://github.com/sanguinariojoe/vtk-builds/releases), so
you can produce CI/CD pipelines to automagically build standalone packages.

### Pythin wheels

Suppose that you have a C/C++ library which links to [VTK](https://vtk.org),
and it has a Python wrapper. Then I am afraid building the Python wheels it is
not an easy path...

However, you can use
[these releases](https://github.com/sanguinariojoe/vtk-builds/releases) inside
[cibuildwheel](https://cibuildwheel.readthedocs.io/en/stable/), so you can
link against a certain [VTK](https://vtk.org) version, adding such a version
of the [VTK Python package](https://pypi.org/project/vtk/#history) as a
dependency.
Finally, in your Python wrapper just do

```
import vtk
```

before start using the VTK-related functions, so the libraries are loaded.

## Some examples

[MoorDyn](https://github.com/sanguinariojoe/MoorDyn/blob/v2/.github/workflows/build-test.yml)

### Do you have another package using this?

Nice! You can let us know either
[reporting an issue](https://github.com/sanguinariojoe/vtk-builds/issues) or
submitting a [Pull Request](https://github.com/sanguinariojoe/vtk-builds/pulls)
