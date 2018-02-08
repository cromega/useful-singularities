# Useful containers

A collection of [Singularity](http://singularity.lbl.gov/) containers for various sys-admin tasks and installin tools I found useful.

## Installing a tool

Just execute `bin/build` and point it to somewhere in the PATH and at a recipe for building. Eg:

```sh
bin/build ~/bin/tf tools/terraform.bs

[...]

tf --version
Terraform v0.11.3
```


