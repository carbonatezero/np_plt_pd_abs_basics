# A short reference for Numpy, Matplotlib and Pandas



## NumPy
https://numpy.org/doc/stable/user/quickstart.html

Check the Jupyter notebook: https://github.com/carbonatezero/np_plt_pd_abs_basics/blob/main/quick_starts_numpy.ipynb

## Matplotlib

https://matplotlib.org/stable/tutorials/introductory/usage.html

Shortest example:

```
import matplotlib.pyplot as plt  

fig, ax = plt.subplots() 
ax.plot(a,b) # a and b are NumPy arrays
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

- Inputs to plotting functions: Convert everything (e.g. pandas.DataFrame) to `numpy.array` objects prior to plotting.

- Prefer the OO-style!


## Pandas

https://pandas.pydata.org/docs/getting_started/intro_tutorials/index.html

### Two primary data structures: 
  - Series (1-dim); container of scalar
  - DataFrame(2-dim); container of Series

### Built on top of NumPy

### Read and write tabular data

### How to Select a subset of a DataFrame
  - slect specific column
    - `df["Age"]` (returns a "Series")
    - `df[["Age"]]` (returns a "DataFrame")
  - filter specific rows
    - `df[df["Age"]>35]` (`df["Age"]>35` returns a pd Series of boolean values)
  - select specific rows *and* columns
    - `df.loc[df["Age"]>35, "Name"]`
    - `df.iloc[9:25, 2:5]`
