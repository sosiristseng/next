# Setup Julia


[Julia](https://julialang.org/) is a general-purpose programming language focused on ease of syntax, composibility, and high performance.

<!--more-->

## Install Julia

### Windows

- Download and run the installer in [the official website](https://julialang.org/downloads/).
- [juliaup](https://github.com/JuliaLang/juliaup) in the Windows store.
- [juliawin](https://github.com/heetbeet/juliawin) Julia bundled with VSCode, Pluto, Conda & PyCall.

### MacOS/Linux

- Download and run the binary in [the official website](https://julialang.org/downloads/).
- [jill](https://github.com/abelsiqueira/jill) installer:

```bash
bash -ci "$(curl -fsSL https://raw.githubusercontent.com/abelsiqueira/jill/master/jill.sh)"
```

- [jill.py](https://github.com/johnnychen94/jill.py) installer. It requires Python.

```bash
python -m pip install -U --user jill

~/.local/bin/jill install --confirm
```

## Configurations after insta;;

### Auto-activate Project.toml

Set environment variable `JULIA_PROJECT=@.` to let Julia automatically load the closest `Project.toml` and activates the environment.

```bash
export JULIA_PROJECT=@.
```

### Use all CPU cores by default

Set environment varialbe `JULIA_NUM_THREADS=N`.

For example, in `~/.profile`

```bash
export JULIA_NUM_THREADS=$(nproc)
```

Or use alias:

```bash
alias julia="julia --threads auto"
```

### Custom conda location

Add the following lines to `~/.julia/config/startup.jl`,

```julia
ENV["PYTHON"] = ""  # Use conda to install python packages
ENV["CONDA_JL_HOME"] = "/path/to/conda"
```

or set the following environment variables (Not recommended, they may mess up your system)

```bash
export PYTHON=""
export CONDA_JL_HOME="/path/to/conda/install"
```

### Autoload Revise.jl

Add the following lines to `~/.julia/config/startup.jl`

```julia
try
    using Revise
catch e
    @warn "Error initializing Revise" exception=(e, catch_backtrace())
end
```

For `IJulia` (Jupyter Notebook), add the following lines to `~.julia/config/startup_ijulia.jl`

```julia
try
    @eval using Revise
catch e
    @warn "Error initializing Revise" exception=(e, catch_backtrace())
end
```

