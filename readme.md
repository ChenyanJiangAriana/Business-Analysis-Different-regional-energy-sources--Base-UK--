# 对于英国各地区能源的商业分析

# Dashboard Design

![image-20221010150647844](CA\readme.assets\image-20221010150647844.png)

![image-20221010150630313](CA\readme.assets\image-20221010150630313.png)

![image-20221010150702731](CA\readme.assets\image-20221010150702731.png)

主要关注的详情：

| **Pages titles**             | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Fuel input                         | **And this page shows how different types of fuel input for power generation change with the year.**  f                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Supply, availability & consumption | **The number of customers changes with the year, and the demand for different electricit use (for example, factories and factory premises, public lighting, household farm premises, etc.) changes with the year in more detail. It is also worth paying attention to the annual supply, imports and losses. This is very helpful for us to better understand the market.**                                                                                                                                                     |
| Generated and supplied             | **It mainly gives more detailed breakdown data of power generation methods than the first column,  including different types of power generation (traditional power generation,  natural power generation and new energy) so that we have a better understanding of the source of power supply. It not only gives data on the mainstream market, but also gives information on other power plants. Finally,  the mainstream and other integrated data are organized, and the conversion efficiency is given on the far right.** |
| Capacity                           | **The electricity is given in England and Wales, including the amount of electricity sold and the  number of consumers. Both the installed capacity and the output mw are also given. At the same time, the maximum load is also a certain reference value.**                                                                                                                                                                                                                                                                   |
| Electricity capacity margin        | **Electricity generating capacity and simultaneous maximum load met for major power producers**                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Electricity prices                 | **By combining analysis of GPA, etc., with power conditions,** **this gives us a  better understanding of electricity bills as they change over the years,  which points to the average sales value of electricity, while using different index reference groups to give us a better intuitive understanding of prices.**                                                                                                                                                                                                 |

Through careful reading and access to the data set, I think the main problem that I want to make depth analysis and research.
	The supply chain composition of the power system, specifically its upstream, midstream and downstream chains. How it works.
	If I am the owner of an electricity supplier what are the main geographical directions and target customers for my future development and how do I want to expand and develop my current base implementation of power generation base stations. What areas need further development for better profitability.
First of all, I think everyone is a user of electricity, that is, a consumer, but I want to jump out of this perspective and think about how to make money and how to develop from the perspective of an electricity system. Although I will not necessarily be exposed to electricity business in the future, but I think business thinking, how to conduct the industrial chain, is still a very interesting issue, especially profitability.
For another factor, I'm standing on a supplier company’s point of view, and I wonder what areas need further development for better profitability.

**通过仔细阅读和查阅资料集，我认为要对主要问题作深入分析和研究。**

数据分析（part 1 使用传统Excel工具进行）
1.电力系统的供应链构成，特别是它的上、中、下游链条。它是如何运作的。
2.如果我是一个电力供应商的老板，我未来发展的主要地理方向和目标客户是什么，我想如何扩大和发展我目前的发电基站的基础实施。哪些领域需要进一步发展以获得更好的盈利。

首先，我认为每个人都是电力的使用者，也就是消费者，但是我想跳出这个角度，从电力系统的角度来思考如何赚钱，如何发展。

虽然我将来不一定会接触电商，但是我觉得商业思维，如何进行产业链，还是一个很有意思的问题，特别是盈利能力。

另外一个因素，我是站在一个供应商公司的角度，我想知道哪些方面需要进一步发展，才能有更好的盈利能力。

[toc]

## \1.  Prepare clean data

After I finished the cleaning dataset course， I used what I had learned to clean up the data. First of all, I keep the original copy of the data I will work on.

1. In the fuel input sheet, for some special years, the data has two rows and I use function average(number1,number2) to fix this data and make it less uncertain in 1987.
2. Also, some title of the column also has some problems, I change them by use the Substitute(B4, “()”,””) function.
3. And in some cell the type is stored in text not in number, even though, it looks like number. I use the knowledge in lab-02. Click the data tab in the toolbar and select the column option.
4. Since I want to know more about market change in customer change in electricity, the information in customer occupation is not in detail. So, use new data from the
5. Add new data into work.

![1CleaningDataset](CA\1CleaningDataset.png)

I wanted to investigate the distribution of customers in the market and to look at the capacity and volume of electricity used by customers in different regions in order to better guide and review the construction of infrastructure. However, although the table Capacity indicates the situation in England and Wales, the data for my research is too sketchy, but I found a hyperlink in the manual pdf and the sheet called Supply, availability & consume. The file name is: "Sub-national electricity consumption statistics: 2005 to 2018". For me, data from too long ago, e.g1920, could not help me, but data from that dataset for 2015-2018 was available. I started with a cleanup operation on the data and used the ideas provided by my teacher to learn the use of excel map pivot table online. For the map icons excel has to do a one-to-one correspondence with countries/regions etc. I therefore used the clean method that I had learned in my teacher's lab class. I used the replace method and used clean(B4) to remove the unwanted spaces.

The **Text to columns function** works very well, I can turn many fields into columns so I can use them directly. The data given in the teacher's original document was relatively easier to work with, but I don't regret using the new data to work on my new learning. The data contains the necessary requisites to turn it into a map and is well organized in terms of different dimensions such as **median, mean and total,** both **domestic** and **non-domestic.**

Use the **sort function** to make data more tidy And I have decided to use those data, which are showed in the screen shot.

![img](CA\sort.png)

In fuel import sheet, there are many Total New Clean Electricity  which includes Nuclear，Natural flow hydro，Wind and solar. In an overview of a chart, we do not need such detail information. So I change it by using the sum function and have got a new column called——Total new Electricity. In the same style I change the total Traditional Electricity include the sum of Coal and Oil.

I choose to draw a line chart in order to show the tendency especially in the comparison of new way to generate electricity and the traditional one.

It is obviously that the main fuel input was traditional fuel like coal and oil before near 2016. But other fuel input overcome the traditional one in near 2016. It shows the architecture of the fuel input is improving for more environment friendly than before.

Thus, the first question that I want to search on is the Power industry chain analysis, profit mode.

![img](CA\1665384124801.jpg)

Later I will make it combine into the Dashborad.

## \2.  Analysis in supply，available and consumption

To the first question to analysis the profile model:

Then go to the second tap: Supply, availability & consumption.

As you can tell from the headings of the table, the composition of available, I was interested in the trend of their composition as a percentage already changing with the year. After giving due consideration to the type of chart that would be appropriate, I think **it would make more sense to use a pie chart to show the percentages at a glance, and a line chart for the change over the years.**

### 1）Firstly, Supply

`**Firstly, Supply** :From the table we can find the E (Electricity available) = B (Electricity supplied (net)) +C (Purchase from other producers) +D (Net import)`

which means the supplier need to import or purchase the electricity from other purchase in the early years. In the long run, I will use the year from the begin even though, data not that accurate in so early year, but want to see the trend in supplying.

However, since the “Data for all generating companies are only available from 1986 onwards”, I will only choose the near year data **after 1986** to ensure correct data and **up-to-date** information are used to help understand and make useful analysis.

From the pie chart generated, we can see that the corresponding values for the components of supply in 1986 show that the main components of the supply chain are still produced by the manufacturers themselves, with a pure import volume of 0.55 TWh in 1986. However, there is still a significant amount of electricity supplied that is lost during transmission. Therefore, I need to do further research on the transmission process, the losses in grid consumption, and I will look at its trend in the line graph. This will be analysed in the available graphs.

### **2）Secondly**, available:

`G (Total) = E (Electricity available) – F (Losses in transmission etc)`

![2.2](\CA\2.2.jpg)

After discovering the pattern in order to have a more accurate and tighter coupling of the data, I replaced it with a formula that links the relationship of the relevant data.

Also, after considering the authenticity of the data documented in detail and how helpful it is to my topic, I believe that data after 1986 is relatively close to the current time period and, in all respects, is supported by appropriate data.

![Pie2](CA\Pie2.jpg)

This pie chart is in the same series as the pie chart for SUPPLY and shows the distribution of available, with domestic use being the largest in 1986, followed closely by industrial use and finally others. There are some differences in the share, but overall, the distribution is quite even. The latter graph is a pie chart for the most recent year, 2019, and you can see that the share of both domestic and industrial has declined, resulting in other becoming second. When creating the dashboard, I will combine the pie charts with a slicer of time to make it easier to read and compare at the same time.

![image-20221010145345160](CA\readme.assets\image-20221010145345160.png)

To see the link between available and supply, and the trend over time, I drew a line graph. As can be seen, all five figures in the legend are positively correlated with net supply, with all five values being at their highest around 2004, and then fluctuating slightly downwards, but still higher overall than the starting point.

### 3）Thirdly, consumption:

**Thirdly, consumption**: In consumption part the main consumptions are from those parts : Public lighting, Traction, Factories and other industrial premises, Shop offices, and other commercial premises and Domestic and farm premises.

![image-20221010145522868](CA\readme.assets\image-20221010145522868.png)

The Stacked chart showed as below, I put the total as 100% to show the occupation of these parts in consumption. By using the stacked chart we can know the main consumption is from the Factories and other industrial premises, in 1923.

 ![image-20221010145531866](CA\readme.assets\image-20221010145531866.png)

It should be an overview in trend by use the timeline, thus, the pivot table changed to show the trend in consumption. As we can see the occupation in domestic and farm premises become much higher than before. And the public lighting and traction kept reducing at that time period.

After those analysis, I can clearly see the basic process in electricity supply, available and consumption process. The consumption in Domestic and farm need more attention, since the trend of this former chart shows that Domestic and farm will be expected to have higher occupation in further. In the former analysis, I can judge the conclusion that the main source of electricity supply is still generated by our own production, relying on other companies to bring in is basically no longer the case. While imports are also growing relatively steadily with the total demand. The main source of electricity supply is relatively stable, which is a good thing for the source of the supply chain. However, for the power loss during transmission. It has always been maintained at a relatively flat position and also rises with the mains supply.

Again, when it comes to usability, the percentage of usability items fluctuates up and down with the year, but relatively speaking, it is between 30% and 40%.

In the consumption segment, the stacked chart allows us to see the structure and share of consumption, which is useful for understanding the composition of supply chain consumption, etc. Through the analysis of the charts, I have basically achieved a better understanding and analysis of the composition of the power supply sources, availability and consumption of the power industry, and a better understanding of the sources of power and the areas where the power is sold. Later I will add a year slicer to help complete the dynamic slicer generation.

## \3.  Generated and Supplied

At the end of the study on supply, availability and consumption, I thought it was necessary to analyze sales further, so in the third original table generated and supplied, I saw a lot of relevant data on mainstream energy providers and other energy providers. Based on the logic and the values, I was able to confirm the relationship between the following data and, as before, use the formulaic method of subtracting the value of generated electricity from the value lost in the work to obtain the value of the total. The same approach will be used for other relevant data, as illustrated in the diagram below.

From the table I can tell that the data in columns B to M are about mainstream e-commerce companies, and in columns O to T are about other non-mainstream companies. Finally columns V to AD are the sum of the former two. Among them we can see some relationships**:**

$$
D=SUM(E+F+G+H+I+J+K)
$$

$$
M=D-L
$$

![image-20221010145714859](CA\readme.assets\image-20221010145714859.png)

So, using the data given, I carried out a line graph study of the total amount and share of all electricity producers in generating electricity by different means.

![image-20221010145732627](CA\readme.assets\image-20221010145732627.png)

It can be seen that the total number of generated has been decreasing over time. However, the figures for non-thermal renewables show an upward trend. As can be seen, there is a general trend towards a decrease in generated over time, with more attempts to use nuclear power to generate electricity, but the share is still not competitive with the mainstream. If I were a supplier, this chart would be helpful and predictive of future choices.

![image-20221010145749858](CA\readme.assets\image-20221010145749858.png)

A look at the choice of mainstream suppliers in terms of how they generate power and the corresponding power produced shows that the general trend is similar to the overall general trend.

$$
AH(Implied Efficiency) = AD(Electricity supplied (net)/GWh)/AG(Fuel input for electricity generation/GWh)
$$

![image-20221010145835022](CA\readme.assets\image-20221010145835022.png)

![image-20221010145846307](CA\readme.assets\image-20221010145846307.png)

Use **F = B / A**, The conversion rate per mtoe can be seen to have remained at 11,630 GWh, but in recent years, particularly from 2015-2019, the figures have risen, albeit limited, to show the increase in conversion rates and the breakthroughs in the technology level of the plants now.

![image-20221010145908205](CA\readme.assets\image-20221010145908205.png)

![image-20221010145916808](CA\readme.assets\image-20221010145916808.png)

The image of implied efficiency over time, shown below, shows that the proportion of conversions is gradually increasing and therefore means that the supply of electricity is increasing year on year as a proportion of generated, so that the supply is regulated according to the rise in electricity consumption in the market.

![image-20221010145933992](CA\readme.assets\image-20221010145933992.png)

![image-20221010145943560](CA\readme.assets\image-20221010145943560.png)

## \4.  Capacity and Electricity capacity margin

![image-20221010150021795](CA\readme.assets\image-20221010150021795.png)

Calculate the correlation coefficient, using the data in Electricity capacity margin, then, choose the data about GW Total Declared Net Capacity in UK and GW Simultaneous maximum load met, UK. Using the function:

$$
CORREL(array1,array2)
$$

The data is measured by year, from 1975 to 2019, but I think use 5 year such as 1970-1975 to measure is also very meaningful.

![image-20221010150059538](CA\readme.assets\image-20221010150059538.png)

Then I set the cell format, to make the data neater.

![image-20221010150145795](CA\readme.assets\image-20221010150145795.png)

![image-20221010150159220](CA\readme.assets\image-20221010150159220.png)

After this finish I also calculate the CC for year from 1970-2019. The margin of electricity is closely related to the actual value given, and the State has measured the margin in terms of a range of factors, including the productivity of the electricity.

The number of consumers is very important for analysis the profit in this industry. As time going on the amount of customer is showing a climbed trend in those year. The line for number of consumers gives us a math style of feeling in the increasing and we can see the trend of his growth and even make certain estimates for the future.

![image-20221010150216522](CA\readme.assets\image-20221010150216522.png)

## \5.  Location area of customers and Total sales

By analyzing the above we can learn that customer growth is certain, then electricity consumption will rise, so where it makes sense to build more infrastructure and do more promotion is a vital part of the future direction of the power company.

Well, I think a map pivot table would give a better picture of the number of customers in different directions and locations and would be more intuitive. I have therefore chosen to analyze the geography of customers in England, Scotland and Wales.

![image-20221010150316933](CA\readme.assets\image-20221010150316933.png)

After some calculations of the kilowatt hours consumed per capita, the average total kilowatt hour consumption calculated in the graph shows a relatively high consumption in the north, which can be found by the shades of color. Setting up base stations in areas of concentrated electricity consumption is not only closer to the consuming population, but also saves us from power losses in long-distance transmission.

But for specific quantities we had no way to see the data from the graph, so I recreated the bar chart to show the variance visually. You can see that England is still the geographic area with the most users consuming kWh, meanwhile, Scotland consumes slightly more than Wales, but not much compared to England locally.

![image-20221010150335807](CA\readme.assets\image-20221010150335807.png)

From the graph, it can be found that non-domestic use is still higher than domestic use, regardless of the region. Therefore, in terms of negotiating cooperation, suppliers should still cooperate more with non-domestic manufacturers and companies, and can communicate with them more often to grab a reasonable market share.

To show their proportions I have used a pie chart to show this.

![image-20221010150352457](CA\readme.assets\image-20221010150352457.png)

To conclude the analysis of the national map of England, I think it necessary to draw a separate map of Scotland and Wales to look at, as follows:

### 1)Scotland

![image-20221010150419615](CA\readme.assets\image-20221010150419615.png)

We can see that in the northern part of the country, users consume more electricity on average, however, the western part is relatively small.

### \2) Wales

![image-20221010150443907](CA\readme.assets\image-20221010150443907.png)

The map of Wales shows that in many areas there is relatively less variation than in the UK and Scotland, which is good news in terms of quick and easy site selection.

![image-20221010150503050](CA\readme.assets\image-20221010150503050.png)

To conclude the analysis of customer electricity consumption, we still need to consider the issue of the population base of users, as the total number of people, once living standards have increased, will be a better guide than the total consumption available.

![image-20221010150519817](CA\readme.assets\image-20221010150519817.png)

The bar chart therefore gives the sales by number of customers for each of the different regions. As you can see, in the slicer I will also use two slicers, time and place, together to complete a dynamic presentation of the changes.

![image-20221010150547278](CA\readme.assets\image-20221010150547278.png)

## \6. Dashboard Design

![image-20221010150630313](CA\readme.assets\image-20221010150630313.png)

![image-20221010150702731](CA\readme.assets\image-20221010150702731.png)

## \7.  Conclusion

Through the above research, for the first issue of my research, that is, the understanding of the supply chain of the power industry, and the analysis of the components, I can draw the following conclusions: the power industry in the upstream production part: there is still a large number of traditional energy sources to produce electricity, but with the development of the times, wind energy, water energy and other clean energy will have a more significant development in the future. In the midstream part: get the output of electricity, there is a part such as transmission in the loss is inevitably occurring loss, but with the market demand changes, the overall three major areas of domestic, industrial, other stable proportion, continued viability of the rise. Finally for the downstream part, that is, the consumption part, the growth of the user volume and time shows a positive correlation, the proportion of electricity for domestic use is gradually rising, and is not negligible.

For the second issue, which is in the analysis of the geographical location of the customer base as an entrepreneur selecting a site, I believe that it should be actively promoted in places where the map shows darker colors, where the total number of customers using electricity is larger. In order to compete with peers for an equal amount of customer resources.

The margin of electricity given by the UK government is important through the verification of correlation. Not only is the future industrial structure to be continuously optimised, but the further expansion of the infrastructure in combination with the analysed geographical distribution of customers is also proven to be a reasonable measure in terms of the continuously growing electricity consumption.
