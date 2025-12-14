# Homework-6-Portfolio
## Group Members: Yeye and Anthony
### [Open in Colab](https://colab.research.google.com/drive/1YPoKXQhoBLfMUFLgE_srbMpVlUXWWMOy)



#### Introduction:

For this homework assignment, I wanted to analyze global economic and demographic growth. To do this, I analyzed two datasets from Our World in Data. The two datasets were estimates for annual GDP per capita and population growth over time. The data for GDP per capita over time comes from the World Bank, whilst the population data comes from the United Nations. The combination of the two data sets includes integer values of population and GDP per capita of countries from the mid-20th century (around 1950) through 2023. 

To begin, there were multiple issues with the data that made it slightly difficult to work with. First, the two data sets covered different time ranges. The population set started from 1950, whilst the GDP per capita data set only started from 1990. Due to this, there were instances during programming where one data set would have data for a specific year, and the other would not. There were also situations where there were specific countries that were not present in both data sets (present in one but not the other). This made merging even more difficult. In addition to this, all of the countries that were in the population data set were missing data from 2024. This complicated the merging even further. To go further, each data set used completely different column names that may indicate the same thing. For example, when the data was downloaded and displayed, the countries column in the population dataset was labeled as “Entities.” Finally, the population data values were very large (in the range of millions to billions), which caused scaling issues in my visualizations.

The questions that guided this analysis were:
How does a country's population change over time in relation to its GDP? 
Does a country's population indicate its quality of life/ does high population = high GDP or vice versa?

In order to answer these questions, I merged the two datasets, cleaned the merged data, removed any years that were unusable, and created country-specific visualizations that show both the GDP per capita and population growth over time.


<br><br>

#### Methods:

After downloading the datasets from Our World in Data, I started by cleaning the dataset and making sure that the data was standard and similar across both datasets. The original files that were downloaded contained different column names and formats for the data. To deal with this, the variables in the data sets were renamed so they were the same across the datasets they were set to: Country, Year, Population, and GDP. All additional columns that were not needed in the analysis were removed. The GDP per capita and population datasets were merged using a left join on the Country and Year columns. This created a single joined data set that contained the GDP per capita and population data for each country for that year.

While trying to prepare the data to be analyzed, there were many small issues. The data sets covered different ranges. To be specific, the population of the countries started from 1950, whilst the GDP per capita only started from 1990 onward. This caused around 40 years of data that be removed from the analysis. In addition to those missing 40 years of data, the population data set was missing the data points for 2024, because of this I removed that year entirely as well. Next, some of the countries in both of the datasets had missing data that were isolated throughout the years. In order to combat this, I used linear interpolation for each individual country. This allowed a best estimate to be made of the data while keeping the trend of the data consistent throughout. After the data was cleaned, I filtered the data to only use the eight countries: The Bahamas, India, China, Japan, and Nigeria. 

Finally, in addition to the interpolation and filtering of the data, the population values of certain countries were very large; some of them were in the billions. To combat this, they were divided by 1 million to make them more interpretable on the graphs. The conversion of the GDP per capita of the countries was already converted to USD in the original data, so it remained in USD. For all of the countries, a dual axis line graph was created, which allowed me to show both GDP per capita and population growth on the same figure. This allows for a simple and direct comparison between the countries. The graphical visualizations make up a large portion of the results. The graphs for each country can be seen below, with a brief explanation of the visualization, along with possible reasoning for why the graph looks the way it does.
