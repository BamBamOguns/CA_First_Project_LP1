# Indian Start-up Funding Analysis (2018 - 2021)

Ideas, creativity, and execution are essential for a start-up to flourish. But are they enough? Investors provide start-ups and other entrepreneurial ventures with the capital, popularly known as "funding"---to think big, grow rich, and leave a lasting impact.

In this project, the intention is to analyze the funding received by start-ups in India from 2018 to 2021. The data for each year of funding was obtained from two separate CSV files (2018 and 2019) and from a database for the years 2020 and 2021. These files provide details about the start-ups, the funding amounts received, the investors, and other relevant information.

## 1. Business Understanding

### 1.1 Determining Business Objectives

The primary objective is to identify the key factors that influence startup funding and predict future funding trends within the Indian startup ecosystem. This analysis is crucial for stakeholders such as startup founders, investors, policymakers, and industry analysts who rely on these insights to make informed decisions.

### 1.2 Assess the Situation

In this phase, the current situation is assessed, considering resources, constraints, and risks. Resources include access to historical startup funding data from 2018 to 2021, data analysis tools like Python, Pandas, and Seaborn, and domain knowledge. Constraints may involve data quality issues, limited access to private funding data, and time constraints. Potential risks include incomplete or inaccurate data and changing market conditions affecting the predictions.

### 1.3 Define Data Mining Goals

The primary goals are to analyze historical funding data to uncover trends and patterns and build predictive models to forecast future funding trends. Secondary goals involve identifying the key factors influencing the likelihood and amount of funding startups receive.

### 1.4 Defining Hypothesis and Business Analysis Questions

#### 1.4.1 Hypothesis

- Null Hypothesis (H0): There is no significant difference in the average funding amounts received across different sectors within the Indian startup ecosystem from 2018 to 2021.
- Alternative Hypothesis (H1): There is a significant difference in the average funding amounts received across different sectors within the Indian startup ecosystem from 2018 to 2021.

#### 1.4.2 Business Analysis Questions

1. Analyze the growth trajectory of startups over the past four years from 2018 to 2021. Investigate if there is an increase in the number of startups being funded and the average size companies of funded annually.
2. Investigate the financial landscape for Indian startups over the four years. Has the average funding amount increased, indicating growing investor confidence, or has it plateaued or decreased overtime?
3. Identify the booming sectors within the ecosystem and which top city serves as the industrial hub in India.
4. Determine the top investors within the startup ecosystem and identify the proportion of investment by the first 3 investors that have funded different sectors from 2018 - 2021.
5. Explore which stages of startups (e.g., Seed, Series A, Series B) are receiving the majority of investments. What are the predominant stages funded, and which cities are the identified stages of business situated.

## 2. Data Understanding

In the Data Understanding phase, the focus is on getting familiar with the data and identifying data quality issues. This phase involves collecting the initial data, describing it, exploring it, and verifying its quality.

### 2.1 Data Collection

Data was collected from various sources:
- Public database with provided credentials saved in a .env format for datasets 2020 and 2021
- Github repository in CSV format (2019 dataset)
- OneDrive account in CSV format (2018 dataset)

### 2.2 Data Description

The collected data is loaded into Pandas DataFrames by importing the necessary libraries, and an initial inspection is performed to understand its structure and basic characteristics. This involves checking the data types, shape, unique values, the presence of missing and duplicated values, and getting an overview of the data using descriptive statistics.

## 3. Data Preparation

In the Data Preparation phase, the focus is on preparing the data for analysis. This phase involves cleaning the data, handling missing values, and transforming the data into a suitable format for analysis.

### 3.1 Data Cleaning

Data cleaning involves handling missing values, correcting errors, and standardizing formats. For example, funding amounts may need to be converted from strings to numerical values.

Concerns with the Data as all 4 datasets will be cleaned and preprocessed separately:
- Columns from different years have different names that must be renamed to be the same for effective analysis.
- A year column must be added to all the DataFrames to represent the year of investment. This is needed and important when the 4 tables are merged.
- All Amounts columns need to be standardized to the same currency ($), and converted to the same datatype (float). All symbols and commas should be deleted and assume that Amount values without any currency signs are taken to be in Dollars.
- All duplicated values in each table should be dropped.
- All missing values should be filled with an appropriate value for each column.

### 3.2 Merged Dataset

Understanding, cleaning, and preprocessing the merged dataset is very important for the intended analysis. Below were the cleaning processes that were followed:
- Checking for duplicates
- Cleaning the 'Sector' and 'Stage' columns very well
- Dealing with different missing data
- Checking and ensuring datatypes are as required
- Applying any column rule-based check if required

### 3.3 Exploratory Data Analysis (EDA)

EDA was carried out on the cleaned merged data to have a holistic understanding of the data and to also see if there are notable patterns that would provide valuable insights when answering the intended business questions. Below are the EDAs carried out on the data:
- The number of startups in each funding year
- The trend of startup funding within the period 2018 - 2021
- The number of startups each year
- The number of startups in each city
- The top 10 sectors with the most number of startups
- The top 10 investors who funded different startups
- The average funding on a yearly basis

### 3.4 Hypothesis Testing

The Hypothesis Testing was carried out using the ANOVA one-way method to determine the F-statistic and p-value of the dataset in consideration.

Below are the values for both the F-statistic, p-value, and the hypothesis adopted for the analysis:
- F-Statistic: 0.036108096661287135
- P-Value: 0.9999999999999999
- Fail to reject Null Hypothesis. There is no significant difference in average funding amounts across sectors.

### 3.5 Answering the Analytical Questions

The 5 business questions stated earlier were answered and these are the observations for each question:

1. A line graph and a bar chart were plotted to show the trend of startups within the given period and the number of startups each year.

   - **Observation:** Over the span of four years from 2018 to 2021, the data reflects a notable increase in the number of startups receiving funding. However, the notable dip in the number of startups funded in 2019, with only 89 startups receiving funding, may have been influenced by various real factors such as economic uncertainty associated with the outbreak of COVID-19 pandemic. That notwithstanding, there is an indication of economic rebound per the trend after 2019 which suggests resilience and potential for growth in the startup ecosystem.

2. A bar chart was plotted with a line of regression included to determine the average funding amount over the four years to see if there is a steady increase or decrease.

   - **Observation:** Over the four-year period from 2018 to 2021, the financial landscape for Indian startups has seen remarkable growth, as evidenced by a substantial increase in average funding amounts. Starting from $13.4 million in 2018 to an average funding amount surge of $151.3 million in 2021. This indicates growing investor confidence and a maturing startup ecosystem.

3. Two horizontal bar charts were plotted to determine the top 5 sectors with the most startups and to confirm the top 5 locations with the highest number of FinTech startups being the 1st amongst the top 5 sectors.

   - **Observation:** The findings reveal that the top booming sectors within the Indian startup ecosystem are FinTech, EdTech, Finance, E-Commerce, and SaaS, with FinTech leading the pack. Additionally, Bangalore emerges as the industrial hub in India, boasting the highest number of FinTech startups among the top cities, followed by Mumbai, Gurugram, New Delhi, and Chennai. The dominance of FinTech reflects the growing importance of digital financial services, while EdTech's prominence indicates significant demand for technology-driven educational solutions.

4. A horizontal bar chart was plotted to determine the top 5 investors and a doughnut pie chart plotted to confirm the top 3 investors by the percentage of investments who funded different startups with Inflection Point Ventures taking the 1st.

   - **Observation:** The analysis identifies Inflection Point Ventures, Venture Catalysts, and Mumbai Angels Network as the top investors within the Indian startup ecosystem. These key players have funded multiple startups across diverse sectors from 2018 to 2021. Inflection Point Ventures stands out with the highest proportion of investment, followed by Venture Catalysts and Mumbai Angels Network. Their diverse investment portfolios reflect a strategic approach to spreading risk and capitalizing on opportunities across various sectors, contributing to the growth and innovation of the startup ecosystem.

5. A vertical bar chart was plotted to determine the top 5 stages of startups using the distribution of funding as criteria. Also, a pie chart was plotted for the top 3 locations with the 1st of the top 5 stages of startups.

   - **Observation:** The top investors in the Indian startup ecosystem have shown a preference for funding businesses at various stages, with a notable focus on Debt investments. Debt funding is a strategic tool for startups looking to raise capital while retaining ownership and control. This method of raising capital has several potential benefits, especially compared to equity financing, which involves selling shares of the company to investors. Bangalore emerges as the primary location for Debt startups, accounting for 48.6% of investments, followed by New Delhi at 29.7% and Mumbai at 21.6%.

### 3.6 Recommendations

Based on the observations on the Indian startup ecosystem, here are some informed recommendations for the team to consider to make informed decision:

1. **Stay Resilient and Adaptable:** The Indian startup ecosystem has shown resilience and potential for growth, even in the face of challenges like the economic uncertainty associated with the COVID-19 pandemic. The team should be prepared to navigate uncertainties and adapt strategies as needed.

2. **Focus on High-Growth Sectors:** The booming sectors within the Indian startup ecosystem, such as FinTech, EdTech, Finance, E-Commerce, and SaaS, present lucrative opportunities for investment and innovation. The team should consider these sectors to capitalize on the growing demand and investor interest.

3. **Location Strategy:** Bangalore emerges as the industrial hub in India, with a high concentration of startups, particularly in the FinTech sector. The team should consider establishing a presence in Bangalore to tap into the vibrant startup ecosystem and access talent, resources, and networking opportunities.

4. **Strategic Partnerships with Top Investors:** The team is encouraged to form strategic partnerships with top investors like Inflection Point Ventures, Venture Catalysts, and Mumbai Angels Network. These investors have a proven track record of funding successful startups across diverse sectors and can provide valuable insights, mentorship, and funding opportunities.

5. **Focus on Debt Investments:** Given the preference of top investors for Debt investments, the team should consider targeting startups at this stage for investment or partnership opportunities. Debt Financed startups have typically proven their business model and are ready to scale, offering lower risk and significant growth potential.
