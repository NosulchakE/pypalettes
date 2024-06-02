# purrpalette

A large (**+2500**) collection of color maps for matplotlib/seaborn.

All available palettes can be found [on the dedicated website](https://josephbarbierdarnal.github.io/purrpalette/)

<br><br>

## Quick start

Once the `cmap` is loaded, you can use it as any other color map in `matplotlib` or `seaborn`.

```python
import matplotlib.pyplot as plt
import seaborn as sns
from purrpalette import PurrPalette
import numpy as np

data = np.random.rand(10, 12)

purr = PurrPalette()
cmap = purr.load_cmap('Anemone')

sns.heatmap(data, cmap=cmap)
plt.show()
```

![heatmap example](images/heatmap.png)

<br><br>

## Installation

```bash
pip install git+https://github.com/JosephBARBIERDARNAL/purrpalette.git
```

<br><br>

## Getting started

- Load the package:

```python
from purrpalette import PurrPalette
purr = PurrPalette()
```

<br>

- Load a color map:

```python
cmap = purr.load_cmap('Darjeeling2')
cmap
```

![Darjeeling2](images/Darjeeling2-qualitative.png)

<br>

- Transform a qualitative color map into a continuous one:

```python
cmap = purr.load_cmap('Darjeeling2', type='continuous')
cmap
```

![Darjeeling2](images/Darjeeling2-continuous.png)

<br>

- Load a random color map:

```python
cmap = purr.load_cmap('random')
cmap
```

![random](images/random.png)

<br>

- Find where a color map comes from:

```python
print(purr.source('bilbao'))
```

`'The R package: {khroma}'`

<br>

- Get hex values of a color map:

```python
print(purr.hex('pupitar'))
```

`['#7098C0FF',
 '#88C0E8FF',
 '#285880FF',
 '#B8E0F8FF',
 '#F8F8F8FF',
 '#404060FF',
 '#A8A8A8FF',
 '#C8C8D0FF',
 '#B04000FF']`

<br>

- Get rgb values of a color map:

```python
print(purr.rgb('AirNomads'))
```

`[(255, 153, 51),
 (194, 72, 65),
 (255, 255, 51),
 (139, 91, 69),
 (135, 175, 209),
 (238, 176, 90),
 (219, 197, 160)]`

<br>

More examples can be found in the [how to use notebook](https://github.com/JosephBARBIERDARNAL/purrpalette/blob/main/how_to_use.ipynb)

<br><br>

## Related projects

`purrpalette` is **highly** inspired from the R package [paletteer](https://github.com/EmilHvitfeldt/paletteer) and the python package [palettable](https://github.com/jiffyclub/palettable).

<br><br>

## How data has been collected

- Sites used
   - https://coolors.co/palettes/trending
   - https://pmassicotte.github.io/paletteer_gallery/

These sites have been scraped with the scripts in `parsers/`. Data is then saved into a `.csv` format with name+palette+source.

Color maps already available in `matplotlib` and `seaborn` have been added to the collection.

Since some color maps have the same name, some specific palettes can be different from the ones expected. If you find a mistake, please open an issue.

The easiest way to find the original source is to use the `source()` method, and I highly suggest you to find your dream color map using the [original site](https://josephbarbierdarnal.github.io/purrpalette/).

<br><br>

## How to add a new palette

More is better: if you know how to add a significant amount of palettes (>30), please do so. PRs are welcome.

TODO: detail the process