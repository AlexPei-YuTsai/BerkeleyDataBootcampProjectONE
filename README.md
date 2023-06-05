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

### Individual Income and Energy Data
In the source CSVs for residential electricity rate per kWh, for the column named service_type, Delivery was dropped and Bundled was kept because Bundled signifies an all inclusive rate. Whereas Delivery signifies that consumers are sourcing their electricity from a party other than the utilities and are only paying the utilities a few for using utility instrastructure for getting the electricity to their homes. 

If the same zipcode has multiple utilities (whether Investor-Owened Utilities or Non-Investor-Owned Utilities), the median was taken so that one zipcode only had one electricity rate for data hygiene purposes. 

### State Wage and Crime data
The code reads and manipulates two datasets: "wage_estimates" and "crime_data." The "wage_estimates" dataset contains information about wage estimates for various occupations in different states. It creates a summary dataframe called "wage_estimates_summary" with columns "State," "Occupation," "Average hourly wage," "Average annual wage," "Median hourly wage," and "Median annual wage." The "crime_data" dataset contains information about crime statistics in different states. It selects specific columns from the "crime_data" dataset to create a summary dataframe called "crime_summary." The code filters the "crime_summary" dataframe to keep only data for 2020, creating a new dataframe called "crime_data_2020." Then, the code merges the "wage_estimates_summary" and "crime_data_2020" dataframes based on the common "State" column.
Finally, the code creates a scatter plot using the matplotlib library in Python, displaying the relationship between average annual wage and total crimes in 2020. The plot is labeled "Average Annual Wage vs Total Crimes (2020)." A linear regression line is fitted to the data using the numpy library's polyfit function, and the slope and y-intercept are calculated. The correlation coefficient is calculated using the scipy library's pearsonr function, indicating a positive but moderate correlation between the two variables. The plot displays the relationship visually, with the trend line illustrating the direction of the relationship and the correlation coefficient providing a numerical measure of the strength of the correlation.


#### sources so far
- [money data](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics-2020-zip-code-data-soi)
- [zip conversion](https://simplemaps.com/data/us-zips)
- [health data](https://chronicdata.cdc.gov/500-Cities-Places/PLACES-ZCTA-Data-GIS-Friendly-Format-2022-release/kee5-23sr)
	- note: zcta != zip, but most of the time they're close enough for them to be interexchangeable. also, they are estimates (rigorous, but estimates nonetheless) made through the CDC PLACES project's specific methodologies.
	- [data defs here](https://www.cdc.gov/places/measure-definitions/)
- [ssa data](https://www.ssa.gov/policy/docs/statcomps/oasdi_zip/2020/index.html)
- [State Wage](https://www.bls.gov/oes/current/oes_ca.htm)

