# Homework-6-Portfolio
## Group Members: Yeye and Anthony
### [Open in Colab](https://colab.research.google.com/drive/1YPoKXQhoBLfMUFLgE_srbMpVlUXWWMOy)

#### Introduction:

For this homework assignment, I wanted to analyze global economic and demographic growth. To do this, I analyzed two datasets from Our World in Data. The two datasets were estimates for annual GDP per capita and population growth over time. The data for GDP per capita over time comes from the World Bank, whilst the population data comes from the United Nations. The combination of the two data sets includes integer values of population and GDP per capita of countries from the mid-20th century (around 1950) through 2023. 

To begin, there were multiple issues with the data that made it slightly difficult to work with. First, the two data sets covered different time ranges. The population set started from 1950, whilst the GDP per capita data set only started from 1990. Due to this, there were instances during programming where one data set would have data for a specific year, and the other would not. There were also situations where there were specific countries that were not present in both data sets (present in one but not the other). This made merging even more difficult. In addition to this, all of the countries that were in the population data set were missing data from 2024. This complicated the merging even further. To go further, each data set used completely different column names that may indicate the same thing. For example, when the data was downloaded and displayed, the countries column in the population dataset was labeled as “Entities.” Finally, the population data values were very large (in the range of millions to billions), which caused scaling issues in my visualizations.

The questions that guided this analysis were:  
- How does a country's population change over time in relation to its GDP?  
- Does a country's population indicate its quality of life / does high population = high GDP or vice versa?

In order to answer these questions, I merged the two datasets, cleaned the merged data, removed any years that were unusable, and created country-specific visualizations that show both the GDP per capita and population growth over time.

---

#### Methods:

After downloading the datasets from Our World in Data, I started by cleaning the dataset and making sure that the data was standard and similar across both datasets. The original files that were downloaded contained different column names and formats for the data. To deal with this, the variables in the data sets were renamed so they were the same across the datasets: `Country`, `Year`, `Population`, and `GDP`. All additional columns that were not needed in the analysis were removed. The GDP per capita and population datasets were merged using a left join on the `Country` and `Year` columns. This created a single joined data set that contained the GDP per capita and population data for each country for that year.

While trying to prepare the data to be analyzed, there were many small issues. The data sets covered different ranges. The population of the countries started from 1950, whilst the GDP per capita only started from 1990 onward. This caused around 40 years of data that had to be removed from the analysis. In addition to those missing 40 years of data, the population data set was missing the data points for 2024, so I removed that year entirely as well. Next, some of the countries in both datasets had missing data isolated throughout the years. To combat this, I used linear interpolation for each individual country. This allowed a best estimate to be made of the data while keeping the trend of the data consistent throughout. After the data was cleaned, I filtered the data to only use the following countries: The Bahamas, India, China, Japan, and Nigeria. 

Finally, in addition to the interpolation and filtering of the data, the population values of certain countries were very large; some of them were in the billions. To combat this, they were divided by 1 million to make them more interpretable on the graphs. The conversion of the GDP per capita of the countries was already in USD in the original data, so it remained in USD. For all of the countries, a dual-axis line graph was created, which allowed me to show both GDP per capita and population growth on the same figure. This allows for a simple and direct comparison between the countries. The graphical visualizations make up a large portion of the results. The graphs for each country can be seen below, with a brief explanation of the visualization, along with possible reasoning for why the graph looks the way it does.

---

### Results:

#### The Bahamas
<iframe src="Bahamas_Graph.html" width="100%" height="600" style="border:none;"></iframe>

This visualization shows the correlation between GDP per capita and population growth for The Bahamas. As you can see, there has been a steady increase in population growth since 1990. However, you can see significant dips in the GDP per capita over time. On the left of the visualization, you can see a constant decrease / negative GDP per capita growth rate between 1990 and 1993. This could be due to the US recession that was taking place around that time. The Bahamas gets the majority of its finances from tourism from the US. The lack of travel due to the recession could be a factor for the dip. Another significant dip in the GDP can be seen in 2020. This could be due to the COVID-19 outbreak. This halted travel, which majorly affected the country's GDP per capita which could be the cause of the sharp dip. However, even with these dips, you can see a steady positive correlation between the population and the GDP per capita growth rate. 

---

#### India
<iframe src="India_Graph.html" width="100%" height="600" style="border:none;"></iframe>

India shows a graph with a steady growth rate from 1990 to 2023, with an already high population of over 1 billion people. Even though the population is extremely high, the GDP is steadily increasing, but is still significantly lower than the other countries in this analysis. Between 1990 and 2023, the GDP per capita has only risen around 6500 to 7000 US dollars. The only significant dip in the GDP was in 2020; this could be due to the COVID-19 pandemic, similar to the other countries. The low GDP could be attributed to the country’s excessively large population. Too many people, not enough resources. Even with a lower GDP per capita overall, we can still see a strong positive correlation between the country’s population and GDP per capita.

---

#### China
<iframe src="China_Graph.html" width="100%" height="600" style="border:none;"></iframe>

In China, you can also see a strong correlation between the country’s population and GDP per capita. However, unlike other countries, China has no significant dips in population or GDP per capita. China has a large population of over 1.4 billion people, and its GDP per capita went from around 3000 US dollars to around 23000 US dollars. This graph shows a steady positive correlation between the two variables, with no significant dips in either data set. This helps form the correlation between population and GDP per capita.

---

#### Japan
<iframe src="Japan_Graph.html" width="100%" height="600" style="border:none;"></iframe>

In this visualization, you can see large fluctuations in the two data sets. The population and GDP per capita both start off positively correlated. Then, as time went on and around 2006-2007, the population and GDP per capita began to decrease. After the initial drop, the GDP per capita began to increase and recover; however, the population continued to decrease to this day. One possible explanation for this is that the fertility rate in Japan is extremely low. Not many people are born in the country, and its residents are rapidly aging and living longer. Even though this visualization goes against the idea of this analysis, it's necessary to get a broader picture of the correlation between population growth and GDP per capita.

---
### Conclusion:
<br><br>
From the results of this analysis, we can conclude that there is generally a positive correlation between the population size and GDP per capita over time. In the majority of the countries that I used for this analysis, an increase in the population is usually followed by an increase in the country's GDP and vice versa. This tells us that as a country grows in population, its economic output per person grows. This answers my first question, “How does a country's population change over time in relation to its GDP?” The trend suggests that they both grow in the same direction, even though the growth rate changes within each country. 

The population and GDP per capita both increase with each other; however, when the question “Does a country’s population indicate its quality of life, or does a high population imply a high GDP (or vice versa)?” is asked, the answer becomes more complicated. Even though we can confidently say that a country’s population and GDP per capita both rise together, GDP per capita is only one measure of the economic wellbeing of the country, not its residents’ quality of life. A large population does not equal high living standards, nor does the rapid growth of the population mean that the country is performing strongly economically. There are many other factors to take into consideration, like health conditions, social services, education levels, and overall economic structure. In relation to this, while population growth may correlate with rising GDP, it shouldn’t be seen as its main factor or indicator of quality of life, and vice versa.

There are numerous limitations to the interpretation of this analysis. The two data sets had different ranges, which forced me to erase a good portion of the data. I had to disregard all the data before 1990 and all of the 2024 population values. There was also data missing in the datasets, which required me to use linear interpolation; because of this, many fluctuations in population or economic history may have gone unnoticed or masked. In addition to this, GDP per capita and total population are limiting variables. They don't account for things like inequality, wealth, and other indicators of social standing. Finally, some of the countries had differences and inconsistencies in the data, which affect the overall accuracy of the results in the analysis.

Future studies and research should have a larger range and scope of the population and economic variables in order to get a more accurate and complete understanding of the data. Things like the Human Development Index, Life Expectancy, and the Average Income of a country could help and give more context to the changes in GDP of countries. In the future, I could have used more countries to expand the data set in order to reveal more trends that may not have been prevalent in a small data set. In the future, I could also do more statistical analysis to determine whether population growth leads to GDP growth or if GDP growth leads to population growth. Also studying fertility, age, and migration would also give us a behind the scenes look at the changes in population growth.

To conclude, while the analysis shows a strong correlation between population growth and GDP, it also shows us that economic growth and quality of life require more than just a country's population size.


