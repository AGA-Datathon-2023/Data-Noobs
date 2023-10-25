# Data-Noobs

# **Team Members**

- Elina Paraschou, MS Analytics at American University
- Kritika Goyal, MS Analytics at American University
- Nabila Nishat Raisa,  MS Analytics at American University
- Aatsend Lkhagvadorj, MS Analytics at American University

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

In our analysis, we assesed how the allocation of awards from the Department of State in New York is influenced by disbursements to date, programs, regions, and industries. The distribution of the funds is not evenly spread among programs, industries, and regions. We also wanted to dive deeper and focus on the impact public funds have in minority/women programs and in small businesses. 

Using an alpha of 0.05, the entire model is statistically significant, and the null hypothesis is rejected, keeping all else constant. 

Based on the regression analysis, we interpreted the significance of the Region, Industry, Programs, and Disbursement to date to the allocation of awards from the Department of State in New York. In accordance with that, for every additional dollar spent in the Disbursement to Date, the allocation of awards is estimated to increase by approximately $0.02319, and is statistically significant ( p = 0.018). For Northwest region, residing in this region is associated with an estimated increase of approximately $745,300 in the allocation of awards compared to the other region. Similar interpretations would apply to the Southeast and Southwest regions, where being in those regions is associated with estimated increases of approximately $965,600 and $1,324,000, respectively, in the allocation of awards compared to the reference region. These differences are statistically significant, meaning they are likely not random (p = 0.006). So, being in the Northwest region, on average, seems to bring in more state awards compared to the aforementioned region. Also, for industries such as food service. The data suggests that for every additional dollar spent in the food services sector, there is  a decrease of  $767,700 in the total state awards in the industry of education arts. This increase is statistically significant (p < 0.001). In simpler terms, spending more in development programs seems to bring in more state awards, and this increase is very likely not due to chance. Some program types, like "Innovation/Education" and "Misc.," also show significant impacts, suggesting that every extra dollar spent in these programs leads to a substantial increase in state awards. However, not all program types show such significant impacts.

**Minority/Women:**
In our analysis, the following data about minority/women related program has been collected and subsequent results have been generated: 
Frequency: 4
Threshold = 546161204.2  (mean of the dataset)
We conducted a hypothesis testing to check if enough funds were allocated to minority/Women related programs.
To understand that we did the following hypothesis test: 
Null Hypothesis: There is not enough evidence that the average Total State Awards for Minority/Women related programs is less than the threshold
Alternative Hypothesis: There is evidence that the average Total State Awards for Minority/Women related programs is less than the threshold
to conduct the test, we calculated the test statistics using t test. 
The test statistics, t-test was conducted. The result of the test statistics = -22840.01 and P value< 0.01
in this test, the significance level,  alpha <- 0.05,
in statistical rule, as the p.value < alpha, we were able to reject the null hypothesis: There is evidence that the average Total State Awards for Minority/Women related programs is less than the threshold.

Based on our analysis, it can be derived that minority women, an already suffering group in the socioeconomic structure, are receiving less awards. Women hold a significant portion of 48.8% in the labor market in New York. However,in 2021, women in New York earned 88.2 cents for every dollar earned by their male counterparts, a figure notably better than the national average of 81.5 cents. As there exists a wage gap based on the gender, it may benefit women by receiving more government aid. The gender pay gap remains significantly wider for women of color, both in New York and across the country. This context highlights the significance of our findings, which are the funding disparities women and minoritties face in the labor market. Specifically, Black or African American women in New York earned only 67.8 cents for every dollar earned by men, while Hispanic and Latino women received just 62.9 cents for each dollar earned by their male counterparts. These disparities underscore the importance of programs supporting minority women-related initiatives.

Occupations that are both low-paying and heavily segregated by gender, such as education, are primarily staffed by women, who make up 90% of the workforce in this sector. Women are more likely to take temporary breaks from their careers or work part-time to care for their children. These circumstances can directly impact their income and job opportunities.

New York's Governor Hochul is committed to create more opportunities for women in the workforce. Starting in 2023, the Governor allocated $7 billion over four years to enhance affordable childcare access,raising the income eligibility threshold to 300% of the federal poverty level. This extends access to over half of New York's young children and broadens the options for childcare providers. In 2023, Governor Hochul launched a pioneering program offering 12 weeks of fully paid parental leave to over 10,000 unrepresented state employees for bonding with a child. These initiatives are a crucial step towards addressing the funding disparities that women and minorities face in the labor market, as highlighted by our findings. By providing essential support for women, these programs work to bridge the gender pay gap and promote equality in New York's workforce.

**Small business:**
In our analysis, the following data about small business related program has been collected and subsequent results have been generated: 
Frequency: 40887
Threshold: 546161204.2  (mean of the dataset)
We conducted a hypothesis testing to check if enough funds were allocated to small business related programs.
To understand that we did the following hypothesis test: 
Null Hypothesis: There is not enough evidence that the average Total State Awards for Small Business  related programs is less than the threshold
Alternative Hypothesis: There is evidence that the average Total State Awards for Small Business  related programs is less than the threshold
to conduct the test, we calculated the test statistics using t test. 
The test statistics, t-test was conducted. The result of the test statistics = -22840.01 and P value< 0.01
in this test, the significance level,  alpha <- 0.05,
in statistical rule, as the p.value < alpha, we were able to reject the null hypothesis: There is evidence that the average Total State Awards for Small Business  related programs is less than the threshold

In our analysis we found that the most economic activity takes place in the Southwest part of New York. In fact,small businesses are the backbone of New York City's economy. Out of the 200,000 businesses in the city, 98% are considered small, with fewer than 100 employees, and 89% are categorized as very small, with fewer than 20 employees. These small enterprises employ over 50% of the city's private sector workforce and frequently offer entrepreneurs their first opportunity for economic self-reliance and a path to the middle class. 

Small businesses in New York City consistently face challenges due to a complex regulatory framework. This framework includes over 6,000 rules and regulations, approximately 250 business-related licenses and permits, and various compliance processes, making it difficult for them to establish, run, and expand their enterprises. 

To address these challenges,the NYC Business Express Service Team (BEST) initiative has played a pivotal role in preserving over $22 million for small businesses in New York City by helping them evade fines and violations. Since its inception, NYC BEST, a no-cost program, has aided over 2,200 diverse businesses throughout the five boroughs. It provides personalized expert guidance, allowing business owners to effectively address or prevent fines and violations, streamline their interactions with the city government's rules and regulations, and expedite the permit and licensing procedures while also saving time and money.

Small Business Month commences amidst New York City's remarkable economic resurgence. The city has already reclaimed 99.7% of its pre-pandemic private sector jobs, defying previous forecasts that predicted recovery well into 2025 or beyond, as reported by the New York State Department of Labor (NYSDOL).



# **Limitations**

Limitation include the outliers that need to be removed. The findings are not substantively significant. Disbursements to date and public investments are correlated but may not necessarily have a meaningful connection.

# **Conclusion**

This analysis confirms that public awards are not evenly spread among industries, regions, and programs. We recommend further analysis into the allocation strategies in New York to promote economic diversity. Specifically, adding a variable to measure the job creation impact of funded programs by race and sex, will help the Department of State in New York to prioritize sectors, that they may not be currently well represented, with the most job-creating potential and long-term boost of the economy. 


