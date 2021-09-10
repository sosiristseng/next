# Matplotlib: Sharing the Legend Box in Twin Axes


- Capture line plot objects from both axes.
- Call `legend()` for both(all) line plot objects.

<!--more-->

```julia
x1 = 1:10

import PyPlot as plt

fig, ax1 = plt.subplots()

l1 = ax1.plot(x1, x1)

ax2 = ax1.twinx()
l2= ax2.plot(x1, exp.(x1))

ax1.legend([first(l1), first(l2)], ["x", "exp(x)"])
```

