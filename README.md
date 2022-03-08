# CIND820-Capstone-Project

Katie Schilling

**Step 1**
Pre-processing.
Both data sets required some form of pre-processing, or data clean up, whether it be cleaning up the column names, or narrowing down the dataset itself.
With Vital Events data, i only needed to take steps to clean up the visual, as well as clean up the date format so that I had a proper date column to work with for my 
time series analysis.

With the Covid data set, there was a lot more pre-processing required.  The dataset has a lot of variables, includes numbers for all provinces as well as Canada as a whole.
Since the vital events data is based on all of Canada on a monthly basis, the rows i wanted to use from teh covid dataset is the ones for all of Canada.
The pre-processing and cleanup stage was a little time consuming on this one, in my journey to align both data sets to the same time frame.  This required both splitting the data
for each month into its own dataframe, running cleanup on each one, and merging them back together with just a sole single number for each month.

Both datasets omce cleaned were then exported for use in the EDA, as well as for my insitial results and code.

**Step 2**

EDA for both datasets to better understand the data.
Once pre-processing was done this was a fairly simple step to take.  I used a created Basic EDA function to view initial results, as well as an EDA we report to look a
little further.  Due to the unforseen nature of the results, the is an expectation that the results would be right-skewed.

EDA for vital events was also quite simple.  All features were well balanced, and showed a consistantcy.

**Step 3**

Running Analysis on the 2 data sets

Once both cleaned files are exported, in a new R Markdown, I imported both files, and merged the 2 files together, and then run a few pre-processing tasks to ensure
the combined data is clean and ready to work with.   Covid cases with N/A were converted to 0, to avoid removing a large chunk of the data due to incomplete tuples, and also to 
allow for the introduction of the numbers over time.  With causality, It's important to have previous data, even if data is 0, to see if there is a direct causality when the covid
positive cases started.  Once done, any rows with N/A were removed from the final data set to avoid errors in the analysis.
Additionally the data is also normalized, since the numbers had very large variations.


**Time Series Analysis**

For this section, I was looking at the analysis of the time series itself.  What patterns, trends and insights could be gained from the data.
Initial results for all variables show a fairly steady, repeating pattern, with slight variations on the either upward or downswing, with the exception of the large spike
with the introduction of Covid cases

**Granger Causality Test**
Running this test, with all variations, showed no direct causality for the majority of the variables, however when running the test using Covid and Deaths, the null hypothesis
in this case can be rejected as the p-value is below 0.05
Overall, there does not seem to be any strong correlations between the variables.

**Linear test**
comparing each variable against all others to create linerar models

Initial results do show that there was a direct impact to the variables with the introduction of the public health crisis that we are in, when comparing predicted values vs actual values
