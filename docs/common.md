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

# Array of Array Operations
A very common idiom is to build up an array by pushing a new row (or column) like:
```
x = rand(3)
push!(out, x)
```
Which will result in a `Vector{Vector{Float64}}` which can be awkward to remedy this a
weird way is to:
```
Array(hcat(out...)')
```
which will make a matrix of the results (given that all the sub arrays are the same size).

In the future julia will have a better way, if you want something that is generic you can
use RecurrsiveArrayTools.jl
