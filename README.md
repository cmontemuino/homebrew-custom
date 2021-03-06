# homebrew-custom

Custom homebrew formulas not available at homebrew-core.

## Available Formulae

* `open-mpi`: Open MPI 4.0.5
* `open-mpi@4.03`: Open MPI 4.0.4
* `open-mpi@4.03`: Open MPI 4.0.3
* `open-mpi@4.02`: Open MPI 4.0.2
* `open-mpi@4.01`: Open MPI 4.0.1
* `open-mpi@4.0`: Open MPI 4.0.0
* `open-mpi@3.1`: Open MPI 3.1.3
* `open-mpi@3.0`: Open MPI 3.0.1

## Installation

To install the latest formula version:

```shell script
brew tap cmontemuino/custom
brew install cmontemuino/custom/FORMULA
```

To get a custom version:

```shell script
brew install cmontemuino/custom/FORMULA@theVersion
```

Please bear in mind that `theVersion` should be what you find after the `@` symbol in the **Available Formulae** section.

## Upgrading

To upgrade the latest version you just need to issue:

```shell script
brew update
brew upgrade cmontemuino/custom/FORMULA
```

## Note about open-mpi version 4.0.3

There's a bug in the OpenMPI 4.0.3 (see [here](https://github.com/open-mpi/ompi/issues/7516)). If you're using such version,
then you will need to do the following:

```shell script
export PMIX_MCA_gds=hash
```

## Note about open-mpi versioned Formulae

All versioned formulae are keg_only (i.e., formula is not symlinked into /usr/local). Therefore you might need to do the following:

If you need to have open-mpi@theVersion first in your PATH run:

```bash
  echo 'export PATH="/usr/local/opt/open-mpi@theVersion/bin:$PATH"' >> ~/.bash_profile
```

For compilers to find open-mpi@theVersion you may need to set:

```shell script
  export LDFLAGS="-L/usr/local/opt/open-mpi@theVersion/lib"
  export CPPFLAGS="-I/usr/local/opt/open-mpi@theVersion/include"
```

For pkg-config to find FORMULA@theVersion you may need to set:

```shell script
  export PKG_CONFIG_PATH="/usr/local/opt/open-mpi@theVersion/lib/pkgconfig"
```

### Software Based Performance Counters

It is possible to activate the [Software Based Performance Counters][spc](SPC) starting from version 3.1.3.
You just need to append the `--with-spc` modifier when installing the formula.

C++ bindings are deprecated since version 3.0, but you can enable them by appending the `with-cxx-bindings` modifier.

[spc]: https://github.com/davideberius/ompi/wiki/How-to-Use-Software-Based-Performance-Counters-(SPCs)-in-Open-MPI
