# Berkeley Data Bootcamp: Project 1

## Folder Contents
- TODO HERE

### Installation/Prerequisites
- Make sure you can run Python. The development environment we used was set-up with:
```
conda create -n dev python=3.10 anaconda -y
```
#### Imported Modules
- Installing via the conda command given should give you access to all of the script's modules locally. However, if you don't have them, be sure to grab yourself the following libraries:
  - [Pandas](https://pandas.pydata.org/docs/getting_started/install.html), [NumPy](https://numpy.org/install/), [SciPy](https://scipy.org/install/), and [MatPlotLib](https://matplotlib.org/stable/users/installing/index.html) for your basic dataframe and statistical manipulation.
  - [Requests](https://requests.readthedocs.io/en/latest/), [hvPlot](https://hvplot.holoviz.org/getting_started/installation.html), and [HoloViews](https://holoviews.org/install.html) for all the geographical visualization and API-related work to be done.
  - OPTIONAL: [Sodapy](https://pypi.org/project/sodapy/) is needed for the medical data we access *if* you choose to access their data through their API. It seems that an API key is NOT necessary here. Due to throttling limits, we'll be using the good ol' fashioned way of making dataframes from CSV data we download.
#### API Keys
- You'll also need to get **TODO API Keys**:
  - TODO
- Assuming that you don't want to change any of the code, you'll then need to create a python file called `config.py` and assign your keys TODO in this format:
```python
TODO_key = "a1b2c3d4e5f6g7h8i9"
```

#### notes
- ideally, we have data that has a dedicated ZIPCODE column (easier to merge)
- a STATE column is kept in the shorterdf file for easier visualization purposes as we can just use pandas to filter for a state or two and see what things look like on a smaller scale

#### sources so far
- [money data](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics-2020-zip-code-data-soi)
- [zip conversion](https://simplemaps.com/data/us-zips)
- [health data](https://chronicdata.cdc.gov/500-Cities-Places/PLACES-ZCTA-Data-GIS-Friendly-Format-2022-release/kee5-23sr)
	- note: zcta != zip, but most of the time they're close enough for them to be interexchangeable. also, they are estimates (rigorous, but estimates nonetheless) made through the CDC PLACES project's specific methodologies.
	- [data defs here](https://www.cdc.gov/places/measure-definitions/)
- [ssa data](https://www.ssa.gov/policy/docs/statcomps/oasdi_zip/2020/index.html)