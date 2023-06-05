# Berkeley Data Bootcamp: Project 1

## Folder Contents
- A `Wealth vs Quality of Life.ipynb` Jupyter Notebook file with all of our data management, coding, visualizations, and analysis.
- A `Resources` folder containing all of the CSV files and data utilized in that Notebook file.
- A `Results` folder containing some exported visuals as HVPlot visualizations don't really appear unless the code is run.

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
Due to general inconvenience, throttling limits, and pricing concerns, we have not found an API worth using for the purposes of our project. However, all of the CSV files we used can be found in the `Resources` folder and the sources can be found listed below:
- [IRS Tax Data](https://www.irs.gov/statistics/soi-tax-stats-individual-income-tax-statistics-2020-zip-code-data-soi)
- [ZIP to map coordinates conversion data](https://simplemaps.com/data/us-zips)
- [CDC PLACES Data](https://chronicdata.cdc.gov/500-Cities-Places/PLACES-ZCTA-Data-GIS-Friendly-Format-2022-release/kee5-23sr)
- [State Wage Data](https://www.bls.gov/oes/current/oes_ca.htm)

## Some Code Explanations

*Anything desired explanations not found here can be found within the meticulous annotations and comments of the Notebook file.*

### Individual Income and Energy Data
In the source CSVs for residential electricity rate per kWh, for the column named service_type, Delivery was dropped and Bundled was kept because Bundled signifies an all inclusive rate. Whereas Delivery signifies that consumers are sourcing their electricity from a party other than the utilities and are only paying the utilities a few for using utility instrastructure for getting the electricity to their homes. 

If the same zipcode has multiple utilities (whether Investor-Owened Utilities or Non-Investor-Owned Utilities), the median was taken so that one zipcode only had one electricity rate for data hygiene purposes. 

### State Wage and Crime data
The code reads and manipulates two datasets: "wage_estimates" and "crime_data." 

The "wage_estimates" dataset contains information about wage estimates for various occupations in different states. It creates a summary dataframe called "wage_estimates_summary" with columns "State," "Occupation," "Average hourly wage," "Average annual wage," "Median hourly wage," and "Median annual wage." The "crime_data" dataset contains information about crime statistics in different states. It selects specific columns from the "crime_data" dataset to create a summary dataframe called "crime_summary." The code filters the "crime_summary" dataframe to keep only data for 2020, creating a new dataframe called "crime_data_2020." Then, the code merges the "wage_estimates_summary" and "crime_data_2020" dataframes based on the common "State" column.

Finally, the code creates a scatter plot using the matplotlib library in Python, displaying the relationship between average annual wage and total crimes in 2020. The plot is labeled "Average Annual Wage vs Total Crimes (2020)." A linear regression line is fitted to the data using the numpy library's polyfit function, and the slope and y-intercept are calculated. The correlation coefficient is calculated using the scipy library's pearsonr function, indicating a positive but moderate correlation between the two variables. The plot displays the relationship visually, with the trend line illustrating the direction of the relationship and the correlation coefficient providing a numerical measure of the strength of the correlation.

