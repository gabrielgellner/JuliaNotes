# Workflow for Personal Packages

## Making a new package
## Generate the UUID numbers
```
using Pkg
Pkg.METADATA_compatible_uuid("<name of package>")
```

## Adding a new dependency to an existing `dev` package
First you need to use the command line to go into the dev package folder. Then start julia
and do the following:
```
]
pkg> activate .
(<project name>) pkg> add <Dependency>
pkg> activate
pkg> resolve
```

## Add dependency to local package
Using the command line navigate to the package direction, start julia and do:
```
]
pkg> activate .
(<project name>) pkg> add "path to local package" # can also you dev if you are working on the dependency locally
pkg> activate # go to the top level environment (the default julia environment)
pkg> resolve
```
