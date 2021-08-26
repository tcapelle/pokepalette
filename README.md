# pokepalette
> A simple pokemon color sampler


This is based on [CDWimmer/PokePalette](https://github.com/CDWimmer/PokePalette)

## Install

```bash
pip install pokepalette
```

## How to use

```python
import numpy as np
import matplotlib.pyplot as plt

import pokepalette
```

There is a handy `SimpleNamespace` with all the pokemons and their colours available:

```python
pokepalette.PokemonColours.pikachu
```




    ['#f5e551',
     '#f5bc1f',
     '#000000',
     '#9b5100',
     '#dd9300',
     '#613007',
     '#404049',
     '#282828',
     '#fef5a3',
     '#c41f17',
     '#e55940',
     '#fefefe',
     '#727282']



```python
pikachu_cmap = pokepalette.get_colormap('pikachu')
pikachu_cmap
```




<div style="vertical-align: middle;"><strong>from_list</strong> </div><div class="cmap"><img alt="from_list colormap" title="from_list" style="border: 1px solid #555;" src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAABACAYAAABsv8+/AAAAGHRFWHRUaXRsZQBmcm9tX2xpc3QgY29sb3JtYXBDL89FAAAAHnRFWHREZXNjcmlwdGlvbgBmcm9tX2xpc3QgY29sb3JtYXABtCnOAAAAMHRFWHRBdXRob3IATWF0cGxvdGxpYiB2My40LjEsIGh0dHBzOi8vbWF0cGxvdGxpYi5vcmeZO9WOAAAAMnRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHYzLjQuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZ7edSqkAAAGOSURBVHic7dahTYNRAIXRHwwCg0UiYQRkwwLdpa62WxAkayBxIEE2CJIugIYJXiWvyXfOBDdXfWc/3+vf5ZR9vs9eMHT58DV7wtDjevaC41ar2QvGdk8XsycM7a9O+LhlWQ6H/ewJQx9v29kThl7vNrMnHHVzfzt7wtD188vsCUObzW72hKPOZw8AAP6fAACAIAEAAEECAACCBAAABAkAAAgSAAAQJAAAIEgAAECQAACAIAEAAEECAACCBAAABAkAAAgSAAAQJAAAIEgAAECQAACAIAEAAEECAACCBAAABAkAAAgSAAAQJAAAIEgAAECQAACAIAEAAEECAACCBAAABAkAAAgSAAAQJAAAIEgAAECQAACAIAEAAEECAACCBAAABAkAAAgSAAAQJAAAIEgAAECQAACAIAEAAEECAACCBAAABAkAAAgSAAAQJAAAIEgAAECQAACAIAEAAEECAACCBAAABAkAAAgSAAAQJAAAIEgAAECQAACAIAEAAEECAACCBAAABAkAAAgSAAAQ9Ac84BPlrGzsiQAAAABJRU5ErkJggg=="></div><div style="vertical-align: middle; max-width: 514px; display: flex; justify-content: space-between;"><div style="float: left;"><div title="#f5e551ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #f5e551ff;"></div> under</div><div style="margin: 0 auto; display: inline-block;">bad <div title="#00000000" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #00000000;"></div></div><div style="float: right;">over <div title="#727282ff" style="display: inline-block; width: 1em; height: 1em; margin: 0; vertical-align: middle; border: 1px solid #555; background-color: #727282ff;"></div></div>



You can plot passing the `pikachu` colors directly

```python
# Pie chart, where the slices will be ordered and plotted counter-clockwise:
labels = 'Frogs', 'Hogs', 'Dogs', 'Logs'
sizes = [15, 30, 45, 10]
explode = (0, 0.1, 0, 0)  # only "explode" the 2nd slice (i.e. 'Hogs')

fig1, ax1 = plt.subplots()
ax1.pie(sizes, colors=pokepalette.PokemonColours.pikachu, explode=explode, labels=labels, autopct='%1.1f%%',
        shadow=True, startangle=90)
ax1.axis('equal')  # Equal aspect ratio ensures that pie is drawn as a circle.

plt.show()
```


![png](docs/images/output_9_0.png)


or passing the corresponding matplotlib's colormap

```python
plt.rcParams["figure.figsize"] = [7.50, 3.50]
plt.rcParams["figure.autolayout"] = True

N = 50
x = np.random.randn(N)
y = np.random.randn(N)

plt.scatter(x, y, c=x, cmap=pikachu_cmap)

plt.show()
```


![png](docs/images/output_11_0.png)

