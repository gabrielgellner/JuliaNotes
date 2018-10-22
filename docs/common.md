# File locations
In Juno the first project will be the starting path, which can be check with `pwd()` at the
REPL.

Do make more path agnostic locations you can use the built in macro `@__DIR__` which will
give the file path for the directory that contains the file that the above macro is
evaluated from. So you could do things like:
```
normpath(joinpath(@__DIR__, "../output/test.out"))
```
to get the location of a folder `output` one directory up from the folder that encloses
the evaluated file and add a `test.out` file  to that path.
