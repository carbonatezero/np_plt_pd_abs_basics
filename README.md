# np_plt_pd_abs_basics
Daily used Numpy Matplotlib Pandas SHORT references

The absolute basics.

## Matplotlib

https://matplotlib.org/stable/tutorials/introductory/usage.html

Shortest example:

```
import matplotlib.pyplot as plt  

fig, ax = plt.subplots() 
ax.plot(a,b)
```

- Figure
  - `fig = plt.figure()` empty figure with no "Axes" (pyplot-style)
  - `fig, ax = plt.subplots()` a figure with a single "Axes" (OO-style)
  - `fig, ax = plt.subplots(2,2)` a figure with a 2x2 grids of "Axes"
- Axes "The Axes class and its member functions are the primary entry point to working with the OO interface."

- For each Axes graphing method, there is a corresponding function in the `matplotlib.pyplot` module that performs that plot on the "current" axes.
- Change parts of a figure  
  - `ax.set_title()`
  - `ax.legend()`
  - `ax.set_xlabel()`, `ax.set_ylabel()`
  - `ax.set_yscale('log')`
  - [`ax.tick_params(**kwargs)`](https://matplotlib.org/stable/api/_as_gen/matplotlib.axes.Axes.tick_params.html) `kwargs={'labelsize':14}`

- Write a helper function with recommended signature:
```
  def my_plotter(ax, data1, data2, param_dict):
      out = ax.plot(data1, data2, **param_dict)
      return out
```

- Prefer the OO-style!
