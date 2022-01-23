# Crypto Arbitrage Analysis

This analysis considers arbitrage opportunities for Bitcoin between two exchanges: Bitstamp and Coinbase. **Arbitrage** is the simultaneous purchase and sale of the same asset in different markets in order to profit from tiny differences in the asset's listed price. For example, if Bitstamp is trading higher than Coinbase, one would simultaneously buy the asset on the lower priced exchange (Coinbase) and sell the asset on the higher priced exchange (Bitstamp). 

For this analysis, data from January 1, 2018 to March 31, 2018 for both Bitstamp and Coinbase will be used to identify these arbitrage opportunities and the availability of these opportunities as time progresses. The purpose of this analysis is to demonstrate how to code and visualize these arbitrage opportunities and to identify any patterns or trends over time. 

---

## Technologies
This project uses Jupyter Notebook (within [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/)) and the standard Python 3.8 libraries. In addition, this project requires the following libraries and/or dependencies:

* [Pandas](https://pandas.pydata.org/) - a software library designed for open source data analysis and manipulation

* [Pathlib](https://docs.python.org/3/library/pathlib.html) - a Python module which provides an object API for working with files and directories

* [matplotlib](https://matplotlib.org/) - a cross-platform, data visualization and graphical plotting library for Python and its numerical extension NumPy


---
## Methods

In order to complete a thorough analysis, three main steps were followed:
* Step 1: Collect the data - The data from the `bitstamp.csv` and `coinbase.csv` files was imported using the `read_csv` function and the `Path` module.

* Step 2: Prepare the data - All of the missing (NaN) values were replaced or dropped, all of the data was converted to the `float` type, and any duplicated values were dropped.

* Step 3: Analyze the data - The `Close` column that cointained the closing price data was chosen. A bigger picture of the data was obtained by looking at summary statistics and plotting a couple month-long periods of data. A more focused analysis of the data was obtained by selecting three specific dates (one earlier, one in the middle, and one later in the time period). The arbitrage profits for each of these three days were calculated and compared. Summary statistics and data plots were also used to help with the focused analysis.  

*To follow along and see more in-depth comments, please review the `crypto_arbitrage.ipynb` Jupyter Notebook file.

---
## Findings 

### Hypothesis
The hypothesis was that the number of arbitrage opportunities would decrease as time progressed. This was the hypothesis because as more people take advantage of the arbitrage opportunities and as the Bitcoin exchange gets better, there are less discrepancies between the prices across different exchanges. 

### Big Picture Analysis
Based on the bigger picture summary statistics and visualizations (i.e., comparison of the entire month of January to the entire month of March), the degree of spread got smaller (less spread out) as time progressed. Bitstamp and coinbase moved closer together as there is less blue color (bitstamp) peaking out from the yellow color (coinbase) as time progressed. In January, the coinbase standard deviation (SD) was 1947 and bitstamp SD was 1926 (1947-1926 = 21). In March, the bitstamp SD was 1275 and the coinbase SD was 1273 (1275-1273 = 2). Therefore, 21 is much greater than 2, so they were more spread from each other in January compared to March. 

Look at the plots of the closing prices for the month of January compared to the month of March and see how the degree of spread got smaller as time progressed:
![January Closing Prices](/Users/catherinecroft/Desktop/January Prices.png)
![March Closing Prices](/Users/catherinecroft/Desktop/March Prices.png)

### Focused Analysis
Based on the more focused analysis of three individual dates (one from early, middle, and late in the data period), the assumption made based on the bigger picture data was confirmed. After reviewing the profit information across each date from the three different time periods, I identified a trend that there were a lot more arbitrage opportunities in the beginning and less in the end. Looking at the data, you could have made 379,304.87 dollars in one day in January compared to 2286.62 dollars in one day in February and compared to 875.05 dollars in March. When choosing the dates, I tried to pick a date where the most arbitrage opportunities were avialable so that it would be a fair comparison. In addition, when looking at the standard deviations (SD) for the profit per trade for each date, the SD was highest in January (65.88), decreasing in February (48.99), and lowest in March (15.98). As more people were taking advantage of the cryptocurrency arbitrage opportunities, it became more normalized. The prices grew closer and closer together and fewer opportunities were present as time progressed. 

Here are the summary statistics that show that the standard deviation decreased from the early to late date and that the number of profitable trades decreased as well:
![Early, Middle, and Late Profit per Trade](/Users/catherinecroft/Desktop/summary statistics - profitable trades.png)

Here is the sum of the potential profits for the early, middle, and late dates:
![Sum of profits](/Users/catherinecroft/Desktop/Sum of Profits.png)

Here are the graphs of the cumulative profits. As the graph shows, the early date has steady, positive profits that accumulate to over 300,000 dollars. The middle date has three spikes where it increases, but it is leveling off a lot more than the early date and it only reaches to just over 2,000 dollars. The late date has one larger increase in the beginning of the plot, but then it levels off and only almost reaches to 900 dollars.
![Early Cumulative Profits](/Users/catherinecroft/Desktop/Early Cumulative.png)
![Middle Cumulative Profits](/Users/catherinecroft/Desktop/Middle Cumulative.png)
![Late Cumulative Profits](/Users/catherinecroft/Desktop/Late Cumulative.png)

---
## Contributors
Catherine Croft

Email: catherinecroft1014@gmail.com

LinkedIn: [catherine-croft](https://www.linkedin.com/in/catherine-croft-4715481aa/)

---

## License

MIT





