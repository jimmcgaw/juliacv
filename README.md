# Julia Programming Project

Interested in using Julia for Computer Vision. I've been playing with this in Python, but I've had a sinking feeling I would evntually run into performance issues. :P

Herein I stumble through creating and structuring a project, managing dependencies, and all of the other goodies. This is a "kitchen sink" repo where I install bunch of Julia libraries 
and play with them individually.

I'm on Mac OS X.

This README.md is notes and links from scattered Internet posts and documentation for my future reference.

## Install Julia 

```
curl -fsSL https://install.julialang.org | sh
```

## Running Hello World

```
julia --project="." src/hello.jl
```

or just:

```
make hello
```

## Set up Project 

Nice post about [how to create and structure a Julia project](https://ufechner7.github.io/2022/08/16/julia-projects.html).

```
mkdir juliacv/
cd juliacv
mkdir src/
```

Opens the REPL:

```
julia --project="."
```

Alias:

```
make shell
```

In the REPL:

```
using Pkg
Pkg.add("CSV")
Pkg.add("DataFrames")
Pkg.add("Plots")
Pkg.add("LinearAlgebra")
```

You can also install a package by trying to import it, and following the "should I just install that?" prompt that comes up.

```
using LinearAlgebra
```

Confirm install by entering package manager mode (PMM):

```
]
```

And then typing:

```
st
```

## Update Compat section of `Project.toml`.

There has to be a better way of doing this, but in PMM mode:

```
compat
```

## Install all dependencies

In CMM, I believe you do this to install all the listed dependencies:

```
activate .
```

```
instantiate
```

## Get bugfixes for installed packages

In PMM mode:

```
up
```

and update each package with the major and minor result of `st`. Also set the version of Julia you are using.

## Jupyter Notebook Kernel

Jupyter Notebook kernel:

```
Pkg.add("IJulia")
```

and just install `jupyter` with `pip`.

## OpenCV

[Getting started with Julia and OpenCV](https://docs.opencv.org/4.x/d8/da4/tutorial_julia.html)

Adding OpenCV bindings:

```
Pkg.add("OpenCV")
Pkg.add("CxxWrap")
```

## Machine Learning with Flux

[Flux for Deeping Learning in Julia](https://fluxml.ai/)

```
using Flux
```

[Flux Docs](https://fluxml.ai/Flux.jl/stable/)

[freeCodeCamp post on doing ML with Julia](https://www.freecodecamp.org/news/machine-learning-using-julia/).

## Computer Vision with Flux

```
using Metalhead
```

[Metalhead Docs](https://fluxml.ai/Metalhead.jl/dev/tutorials/quickstart/)

## Github Workflow Configuration

[Described for CompatHelper package here](https://juliaregistries.github.io/CompatHelper.jl/dev/#GitHub)

