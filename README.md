# Module 5 Challenge - Financial Planning Forecaster

This project is my evaluation and forecasting of an example portfolio with crypto, stocks, and bonds to see if the assets would currently be enough for an emergency fund or would grow enough to be a stable retirement fund. I make use of the Free Crypo API and Alpaca Trade API to get recent prices of select crypto, stocks, and bonds to calculate the current value of the portfolio, then use historical data in Monte Carlo simulations to forecast the 95% confidence interval of what the portfolio may look like in 10 and 30 years. 

**Data used**
1. "Current" prices of BTC and ETH. Current meaning whenever the notebook is ran, which for this project is around 11/09/22
2. Closing price data of SPY and AGG from 11/09/2019-11/09/2022

The emergency fund evaluation first uses the Free Crypto API to grab the current prices of BTC and ETH, then uses the Alpaca Trade API to grab the current closing prices of SPY and AGG to see if the portfolio currently has enough in value to have an emergency fund (based on 3 times the monthly income value).

![Using Alpaca Trade API to calculate current SPY and AGG holdings value](/Images/spy_agg_prices.png)

The retirement fund evaluation uses 3 years worth of SPY and AGG daily return calculations to then use the mean and standard deviation to simulate 10 and 30 years of trading in 500 sample Monte Carlo simulations. 

![Line plot of Monte Carlo simulation for 30 years](/Images/monte_carlo_sim.png)

Then, using the generated probability distribution, I calculate the upper and lower bounds of the portfolio returns with the 95% confidence interval.

![Calculations of the upper and lower bounds for a 95% confidence interval, using 3 years of SPY and AGG prices](/Images/confidence_interval.png)

---

## Technologies

This is a Python 3.7 project ran using a JupyterLab in a conda dev environment. 

The following dependencies are used: 
1. [Jupyter](https://jupyter.org/) - Running code 
2. [Conda](https://github.com/conda/conda) (4.13.0) - Dev environment
3. [Pandas](https://github.com/pandas-dev/pandas) (1.3.5) - Data analysis
4. [Matplotlib](https://github.com/matplotlib/matplotlib) (3.5.1) - Data visualization
5. [Numpy](https://numpy.org/) (1.21.5) - Data calculations + Pandas support
6. [Alpaca Trade API](https://alpaca.markets/) (2.3.0) - Grab recent closing prices for select stocks


---

## Installation Guide

If you would like to run the program in JupyterLab, install the [Anaconda](https://www.anaconda.com/products/distribution) distribution and run `jupyter lab` in a conda dev environment.

To install the Alpaca Trade API, run `pip install alpaca-trade-api` in a conda dev environment. 

---

## Usage

The Jupyter notebook [financial_planning_tools.ipynb](/financial_planning_tools.ipynb) will provide all steps of the data collection, preparation, and analysis. Data visualizations are shown inline and accompanying analysis responses are provided.

The included [MCForecastTools.py](/MCForecastTools.py) file includes the code specifically to run the Monte Carlo simulations.

---

## Contributors

[Ethan Silvas](https://github.com/ethansilvas)

---

## License

This project uses the [GNU General Public License](https://choosealicense.com/licenses/gpl-3.0/)
