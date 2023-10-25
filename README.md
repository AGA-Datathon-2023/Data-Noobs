# Data-Noobs

# **Team Members**

- Elina Paraschou, MS Analytics at American University, +1 (901) 728-8543
- Kritika Goyal, MS Analytics at American University, +1 (202) 790-2039
- Nabila Nishat Raisa,  MS Analytics at American University, +1 (202) 699-4162
- Aatsend Lkhagvadorj, MS Analytics at American University, +976 8908 9440

# **Topic**

Allocation of public invenstments within New York State with a focus on minority/women programs and small businesses.

# **Abstract**

In today's competitive market, equal distribution of public funds among industries, programs, and regions is vital to make well-informed decisions that promote economic growth and optimizes resource allocation. This analysis examines the impact of federal funding within New York state with a focus on small businesses and minority/related programs in the state, using the Database of Economic Incentives from data.gov. A multiple OLS regression analysis was performed to assess how public awards are influenced by regions, programs, industries, and disbursements to date. Hypothesis testing was conducted to diver deeper into the effects of public funding on minority/women related programs and small businesses. Our research shows a concerning trend. In both the case of minority/women programs and small businesses, the allocation of funds falls below the desired threshold. Specifically, for every additional dollar invested in small businesses, there is a decrease of $16,050 in agriculture. Women and people of color make up a significant of portion of the agriculture industry in New York. Additionally, for every dollar allocated in minority/women related programs, there is an increase of $7,154 in agriculture, which indicates the unique challenges women face in the labor market. This analysis shows the disparities in the distribution of public funds and highlights the need for more equitable resource allocation. Achieving a fair balance across these sectors is vital for promoting economic diversity, supporting minority and women programs. Addressing these disparities in funding allocation is important to foster social equity in New York state. 

# **Documentation**

We used Excel to clean the data, recode our variables, and create summary tables with key metrics for our quantitative and qualitative variables. We used R for our statistical analysis and visualizations. 

# **Data Extracting**

We used the “Database of Economic Incentives” from data.gov. It shows resources for businesses and programs seeking public and private funding. We focus on the funds the Department of State receives and allocates in different programs within New York State. We also looked at industry and occupation data from the Department of Labor within New York State.

**Industry & Occupation Data:** https://dol.ny.gov/occupational-and-industry-data

**Lanza, A.J. (2023) NYC Small Business NYSenate.gov:** https://www.nysenate.gov/newsroom/articles/2023/andrew-j-lanza/nyc-small-business 

**Small business first - nyc.gov:** https://www.nyc.gov/assets/smallbizfirst/downloads/pdf/small-business-first-report.pdf

**Dol, N. (2023) 2023 gender wage gap report: Impact of covid on women, NYS DOL Reports**:https://nysdolreports.com/gwg/2023-gwgreport/

**Original Dataset:** https://catalog.data.gov/dataset/database-of-economic-incentives 

**Cleaned Data:** (https://github.com/AGA-Datathon-2023/Data-Noobs/blob/main/NY%20Economic%20Incentives.csv)

**Description of Variables**
- The ‘Program’ variable consists of various programs that received state funding. Due to the vast amount of programs, we categorized them into: Agriculture, Business, Development, Direct Federal Funds, Employment, Environment, Federal Department of Defense, Innovation/Education, Minority/Women related Programs, Misc.,Small Business, and
Tax Programs.
- 'Region' refers to the geographical locations withing New York State. We categirized it to: Northeast, Northwest, Southeast, and Southwest.
- 'Industry' includes multiple sectors that programs operate in. We categorized it to: Education Arts, Food Services, Manufacturing, Professional Services, and Public Administration programs.
- 'Total State Awards' is the total Department of State assistance projects received.
- 'Disbursements to Date' is the amount the projects have received up to date. 

# **Statistical Modeling**
- Multiple Regression Analysis (MLR)
- Power Analysis
- Hypothesis Testing
- 
Apart from simple regression we also performed regression on the normalised dataset, cleaned dataset(Without any outliers) and a dataset focussed only on Southwest region (since that region appeared to be the centre of fund allocation from initial analysis) We then compared all these results and found that The Normalized Data Model provides the best overall fit and explains a significant portion of the variance in the dependent variable, indicating that transforming the data can improve the model's performance. We also drilled deeper and performed a similar analysis just for the southwest region and got a deeper understanding of how various variables and conditions affect the allocation of state awards and how the funds reach the grassroots levels. 

# **Data Viasualizations**

- Scatterplot

There is weak correlation betweeen them as the data points are not closely grouped.

![standardized residuals and leverage scatter plot](https://github.com/AGA-Datathon-2023/Data-Noobs/assets/148115960/90f92091-0146-40f3-937c-ce464728b757)


All of the data points are within Cook's distance lines which indicates that there are no influential points in our model.

![fitted values and standardized residuals scatter plot](https://github.com/AGA-Datathon-2023/Data-Noobs/assets/148115960/06f323f1-0c74-4ea7-a7a8-a253c23ed7a3)


In this scale-location plot, the residuals are spread closely near the red line, which is horizontal. Points 807 and 120090 are the outliers. In this plot, the assumption of equal variance (homoscedasticity) is good as the horizontal line has equally (randomly) spread points. 

![standardize residuals and theoretical quantiles scatter plot](https://github.com/AGA-Datathon-2023/Data-Noobs/assets/148115960/7ab75e0f-6e31-4541-8e05-270ff8330722)


This Q-Q normal plot shows that the residuals are normally distributed. It’s good as the residuals are lined well on the straight dashed line.

![fitted values and residuals scatter plot](https://github.com/AGA-Datathon-2023/Data-Noobs/assets/148115960/babefcd6-7ef0-4975-add0-ac8e0e75dd4b)


Linearity holds reasonably well, as the red line is close to the dashed line. We can also note the heteroscedasticity: as we move to the right on the x-axis, the spread of the residuals seems to be increasing. Finally, points 807 and 120090 may be outliers, with large residual values.


- Bar Plot


Economic activity is most active in the southwest region which is expected as New York City is more densely populated compared to the rest of the state. Public Administration programs receive the most funidng in the southwest and the rest of the regions.

- Presentation Quality Tables (quantitative & qualitative variables)


# **Results & Interpretations**

Using an alpha of 0.01, the entire model is statistically significant. 38% of the variation in total states awards can be explained by knowing region, industry, program, and disbursement to date. 

Based on the regression analysis, we interpreted the significance of the Region, Industry, Programs, and Disbursement to date to the allocation of awards from the Department of State in New York. 
Organizations in the Northwest, Southeast, and Southwest regions tend to receive higher awards compared to the Northeast region. This suggests that regional disparities exist, and policymakers should consider addressing them

In accordance with that, for every additional dollar spent in the Disbursement to Date, the allocation of awards is estimated to increase by approximately $0.02319, and is statistically significant (p<0.018). For Northwest region, residing in this region is associated with an estimated increase of approximately $153,968 I in the allocation of awards compared to the Northeast region. Similar interpretations would apply to the Southeast and Southwest regions, where being in those regions is associated with estimated increases of approximately $118,075 and $449,630 , respectively, in the allocation of awards compared to the Northeast region. These differences are statistically significant, meaning they are likely not random (p = 0.006). 

Also, for industries such as food service. The data suggests that for every additional dollar spent in the food services sector, there is a decrease of $506,624 in the total state awards compared to the  industry of education arts. This could indicate that resources allocated to this industry may not be as effective in generating awards. Understanding industry-specific dynamics is crucial for resource allocation decisions.
 The choice of program type significantly affects the total state awards. Some program types, like "Development," have a highly positive impact, while "Innovation/Education" has a negative impact. In simpler terms, spending more in development programs seems to bring in more state awards . The policy makers should focus on equitable disbursement. Development is understandably an important aspect of society but equal if not more importance should be given to Education, Minority sections of the locality and so on.

These results suggest that various factors, including disbursements, region, industry, and program type, significantly impact the allocation of state awards. It's important to note that these effects are not likely due to random chance, as indicated by the low p-values, and they can provide valuable insights for decision-making and resource allocation.


**Minority/Women:**
In our analysis, the following data about minority/women related program has been collected and subsequent results have been generated: Frequency: 4 Threshold = 546161204.2 (mean of the dataset) We conducted a hypothesis testing to check if enough funds were allocated to minority/Women related programs. To understand that we did the following hypothesis test and found:  There is not enough evidence that the average Total State Awards for Minority/Women related programs is less than the threshold 

Based on our analysis, it can be derived that minority women, an already suffering group in the socioeconomic structure, are receiving less awards. Women hold a significant portion of 48.8% in the labour market in New York. However, in 2021, women in New York earned 88.2 cents for every dollar earned by their male counterparts, a figure notably better than the national average of 81.5 cents. As there exists a wage gap based on the gender, it may benefit women by receiving more government aid. The gender pay gap remains significantly wider for women of colour, both in New York and across the country. This context highlights the significance of our findings, which are the funding disparities women and minorities face in the labour market. Specifically, Black or African American women in New York earned only 67.8 cents for every dollar earned by men, while Hispanic and Latino women received just 62.9 cents for each dollar earned by their male counterparts. These disparities underscore the importance of programs supporting minority women-related initiatives.

New York's Governor Hochul is committed to create more opportunities for women in the workforce. Starting in 2023, the Governor allocated $7 billion over four years to enhance affordable childcare access, raising the income eligibility threshold to 300% of the federal poverty level. This extends access to over half of New York's young children and broadens the options for childcare providers. In 2023, Governor Hochul launched a pioneering program offering 12 weeks of fully paid parental leave to over 10,000 unrepresented state employees for bonding with a child. These initiatives are a crucial step towards addressing the funding disparities that women and minorities face in the labor market, as highlighted by our findings. It is important to consider that minority and women-related programs aim to address funding disparities experienced by these groups in the labour market. Women, especially women of colour, have historically faced wage gaps and reduced economic opportunities. The analysis suggests that allocating funds to programs designed to support women and minority groups can be an effective strategy to bridge these funding gaps and promote equality in the workforce.

**Small business:**

In our analysis, the following data about small business related program has been collected and subsequent results have been generated: Frequency: 40887 Threshold: 546161204.2 (mean of the dataset) We conducted a hypothesis testing to check if enough funds were allocated to small business related programs. To understand that we did the following hypothesis test and found that :Hypothesis: There is enough evidence that the average Total State Awards for Small Business related programs is not less than the threshold. This seems to be a good sign for the push needed for small businesses and the funds reaching the grass root levels.  
In our analysis we found that the most economic activity takes place in the Southwest part of New York. 
Supporting small businesses in New York is critical for economic growth and job creation. With 2.3 million small businesses employing 4.1 million people, they play a significant role in the state's economy. However, it's crucial to ensure that these businesses provide equal opportunities for all, especially women and minorities. The regression results, particularly the negative coefficient for "Small Business," suggest that additional efforts may be needed to direct funding in a way that effectively supports women's economic empowerment within the small business sector.


# **Limitations**

Limitation include the outliers that need to be removed. The findings are not substantively significant. Disbursements to date and public investments are correlated but may not necessarily have a meaningful connection.

# **Conclusion**

This analysis confirms that public awards are not evenly spread among industries, regions, and programs. We recommend further analysis into the allocation strategies in New York to promote economic diversity. Specifically, adding a variable to measure the job creation impact of funded programs by race and sex, will help the Department of State in New York to prioritize sectors, that they may not be currently well represented, with the most job-creating potential and long-term boost of the economy. 


