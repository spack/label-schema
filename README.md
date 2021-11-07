# Spack Label Schema

If you are building a container with spack, it can be useful to apply different
labels to it so that spack packages, compilers, and other interesting attributes
can be programatically accessible. The following repository defines a simple schema
for labels, and likely we will follow up with a pull request to spack to add
this generation programatically to `spack containerize`.

🚧️ **under development** 🚧️

## Schema

For each spack object, (e.g., a package or compiler) representation can be done
on the level of a single entity, or multiple entities for each container. For example, 
the [autamus](https://autamus.io) builds have multiple packages per container, but 
they intend to provide one "main" package and so the single label could be appropriate.

| Spack Object | Context |Labels | Description | Example |
|-------|-------------|-------------|-------------------|-------------|
| Package Name | Single Package |`org.spack.package.name` | The name of a package | zlib |
| Package Version | Single Package |`org.spack.package.version` | The version of a package | 1.2.11 |
| Packages | Multiple Packages | `org.spack.packages` | A list of packages | zlib@1.2.11,zlib@1.2.8 |
| Compiler Name | Single Compiler | `org.spack.compiler.name` | The main compiler for spack | gcc |
| Compiler Version | Single Compiler | `org.spack.compiler.version` | The main compiler version for spack | 9.5.0 |
| Compilers | Multipel Compilers | `org.spack.compilers` | A list of compilers available for spack | gcc@9.5.0,gcc@7.5.0 |
