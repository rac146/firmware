This folder contains the top-level makefile:

> One Makefile to rule them all, One Makefile to find them; One ring to bring 
> them all and in the darkness build them.

To build all projects simply run

```make```

This creates build artefacts for all projects under the `build/target` directory.

## clean build

The top-level makefile also supports the `clean` goal. It calls clean on all
submodules before deleting the `build\target` directory.

E.g.

```make clean all```

## Controlling Verbosity

By default the makefile is quiet - the only output is when an .elf file is produced to
show the size of the flash and RAM memory regions. To produce more verbose output, define
the `v` (verbose) variable, like this:

```
make v=1
```

## Building individual modules

Each module can be built on its own by executing the makefile in the module's directory:

```
cd main
make
```

## Specifying the target Product ID

By default, the build system targets the stock Spark Core (Product ID 0). If
your product has been given a different product ID, you should pass this on the
command line to specifically target your product. For example:

```
make SPARK_PRODUCT_ID=2
```

Would build the bootloader and firmware for product ID 2.


