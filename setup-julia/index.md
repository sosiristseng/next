# Setup Julia


[Julia](https://julialang.org/) is a general-purpose programming language focused on ease of syntax, composibility, and high performance.

<!--more-->

## Install Julia

Windows: download and run the installer in [the official website](https://julialang.org/downloads/). Or use [juliaup](https://github.com/JuliaLang/juliaup) in Windows store.

MacOS/Linux: install Julia using [jill](https://github.com/abelsiqueira/jill) bash script:

```bash
bash -ci "$(curl -fsSL https://raw.githubusercontent.com/abelsiqueira/jill/master/jill.sh)"
```

Or using its python fork [jill.py](https://github.com/johnnychen94/jill.py) installer.

```bash
# pip is required

[[ -x $(command -v pip) ]] && pip install -U --user jill
[[ -x $(command -v pip3) ]] && pip3 install -U --user jill

~/.local/bin/jill install --confirm
```

## Configurations

### Auto-activate Project.toml

Add `JULIA_PROJECT=@.` to the environment varialbe. For example, in `~/.profile`

```bash
export JULIA_PROJECT=@.
```

### Use all CPU cores by default

Add `JULIA_NUM_THREADS=N` to the environment varialbe.

For example, in `~/.profile`

```bash
export JULIA_NUM_THREADS=$(nproc)
```

Or use alias to run `julia -t N`. For example, in `~/.bashrc`:

```bash
alias julia="julia --threads auto"
```

### Custom Miniconda location

Add the following line to `~/.julia/config/startup.jl`,

```julia
ENV["PYTHON"] = ""  # Use conda to install python packages
ENV["CONDA_JL_HOME"] = "/path/to/conda"
```

or add the following line to `~/.profile`:

```bash
export CONDA_JL_HOME=/path/to/conda/install
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

