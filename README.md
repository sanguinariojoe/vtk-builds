# vtk-builds

Automatic builds of [VTK](https://vtk.org) built with
[github actions](https://github.com/features/actions), for several
architectures:

|        SO           |   Arch    |
| :-----------------: | :-------: |
|  windows-latest     |  x86_64   |
|  macOS-latest       |  arm64    |
|  macOS-latest-large |  x86_64   |
|  manylinux2014      |  x86_64   |
|  manylinux2014      |  i686\*   |
|  manylinux2014      |  aarch64  |
|  manylinux2014      |  ppc64le  |
|  manylinux2014      |  s390x    |

\* i686 architecture will be deprecated on a future release.

## Why do I need this?

### Stand-alone distributable packages

First, you can find the static libraries among the
[released files](https://github.com/sanguinariojoe/vtk-builds/releases), so
you can produce CI/CD pipelines to automagically build standalone packages.

### Python wheels

Suppose that you have a C/C++ library which links to [VTK](https://vtk.org),
and it has a Python wrapper. Then I am afraid building the Python wheels it is
not an easy path...

However, you can use
[these releases](https://github.com/sanguinariojoe/vtk-builds/releases) inside
[cibuildwheel](https://cibuildwheel.readthedocs.io/en/stable/), so you can
link against a certain [VTK](https://vtk.org) version.

Because [manylinux2014](https://github.com/pypa/manylinux) is used, pip >= 19.3
as well as python 3.7.8+, 3.8.4+ or >= 3.9 is required.

## Some examples

[MoorDyn](https://github.com/sanguinariojoe/MoorDyn/blob/v2/.github/workflows/build-test.yml)

### Do you have another package using this?

Nice! You can let us know either
[reporting an issue](https://github.com/sanguinariojoe/vtk-builds/issues) or
submitting a [Pull Request](https://github.com/sanguinariojoe/vtk-builds/pulls)
