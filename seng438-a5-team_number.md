**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#:       |   |
|-----------------|---|
| Student Names:  |   |
|                 |   |
|                 |   |
|                 |   |

# Introduction

# 

# Assessment Using Reliability Growth Testing 
### Result of model comparison (selecting top two models)
For this section, our group chose to work with the C-SFRAT testing tool to test the test data file "CDS.DAT" under the Failure_Count directory. The following models were compared to determine which one aligned/fit mostly with our input failure data:
- IFR Salvia & Bollinger
- IFR generalized Salvia & Bollinger
- S Distribution
- Discrete Weibull (Order 2)
- Discrete Weibull (Type III)
- Geometric
- Negative Binomial (Order 2)
- Truncated Logistic

In the below chart, we can see the original failure and model reliability plot against our two covariates (T,F and (E,F)):
![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/a4e2ba01-21af-4ca2-8f74-3dd762683f65)

To compare the models, we simply selected the Model Comparison tab which gave us a table with a list of all models. The top two models are the ones we want to look at:
![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/24e09638-5d89-433f-aa32-607f7125f6c6)
Sorting by log-liklihood, gives us the models in order of how cloself they fit with our failure data. So in our case, DW3(E) and DW3(F) were the closest models to our failure data. 

The Discrete Weibull (DW3) is particularly applicable for modeling failure data measured in discrete units like cycles or shocks. This distribution provides a versatile tool for analyzing scenarios where the timing of events is counted in distinct intervals, making it distinctively useful in fields that deal with discrete data patterns and reliability analysis.

### Result of range analysis (an explanation of which part of data is good for proceeding with the analysis)
In order to select the best models from those that the C-SFRAT gave us, we had to look at the data for the range analysis that would best fit the locations on the failure data graph. We also made sure to look at the log-likelihood column, as previously noted, and discover the two biggest numbers (-398.597 and -403.575). Based on this, we were able to select our two top models, which are shown below. The range was also largely utilized to determine how many failures there were in the dataset, allowing us to generate 140 periods and assess the dependability of the failures that happened inside that time frame.

### Plots for failure rate and reliability of the SUT for the test data provided
MVF Graph for DW3(E) model:

![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/89a4c67a-bf38-42a8-8962-ad87fb593f15)

Intensity Graph for DW3(E) model:

![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/af1604a4-171e-4eef-87d4-3cbfbef8357b)

MVF Graph for DW3(F) model:

![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/12b6247d-aff5-4eb1-b3b5-6a2bd52dc6f9)

Intensity Graph for DW3(F) model:

![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/e5b6ea82-4310-4f96-9d3e-37a698e68c1c)

Failure Intensity Graph for both models:

![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/ab6095c8-2aea-494c-b3d6-01d65343eec2)

### A discussion on decision making given a target failure rate
We utilized the C-SFRAT tool once more to assist in forecasting the testing of the new prediction intervals and the SRTAT tool to assist in predicting the failure rate based on the data's failure number in order to determine the failure rate target. We were able to calculate the failure rate—which is calculated by dividing the total number of system hours by the number of failures—using both of these technologies. Failure rate also aids in our assessment of how much better testing is required to reduce this rate and ensure the amount of problems the system will encounter upon end-user deployment. In order to guarantee that the application's safety is not jeopardized by the dependability of the failure data that was provided to us, our goal was to achieve the lowest rate feasible. Since 0.4 was the lowest intensity for both of the models in the desired intervals for the intensity graph shown in the preceding section, we intended to designate 0.4 as the target failure rate for our two predictions. The failure data with this desired failure rate will give the system being tested, from which the data originated, reliability.

### A discussion on the advantages and disadvantages of reliability growth analysis
Advantages:

1. Improved Reliability: The primary advantage of reliability growth analysis is that it leads to improved reliability of the system or product. By identifying and addressing weaknesses, defects, or failure modes, the reliability of the system can be enhanced.

2. Early Detection of Issues: Reliability growth analysis allows for the early detection of potential reliability problems. By monitoring and analyzing reliability data during development or operational phases, issues can be identified and addressed before they lead to significant failures.

3. Cost Savings: By addressing reliability issues early in the development process, the overall cost of fixing these issues is typically lower compared to addressing them after deployment or production. This can result in significant cost savings over the lifecycle of the system or product.

4. Enhanced Customer Satisfaction: Improved reliability leads to higher customer satisfaction. Customers are more likely to trust and continue using products or systems that demonstrate high reliability, which can result in increased sales and positive brand reputation.

5. Data-Driven Decision Making: Reliability growth analysis relies on data-driven decision making. By collecting and analyzing reliability data, organizations can make informed decisions about design improvements, maintenance strategies, and resource allocation.

Disadvantages:

1. Resource Intensive: Reliability growth analysis can be resource-intensive, requiring significant time, effort, and expertise to collect, analyze, and interpret reliability data. This can be a barrier for organizations with limited resources or expertise in reliability engineering.

2. Complexity: Reliability growth analysis often involves complex statistical methods and models. Understanding and applying these methods correctly require specialized knowledge and skills in reliability engineering, which may not be readily available within an organization.

3. Assumption Dependencies: Reliability growth analysis relies on certain assumptions about the underlying failure mechanisms and the effectiveness of reliability improvement actions. Deviations from these assumptions can lead to inaccurate predictions and unreliable results.

4. Limited Predictive Capability: While reliability growth analysis can provide insights into the reliability improvement process, it may have limited predictive capability, especially for complex systems with uncertain failure modes. Predicting future reliability performance accurately can be challenging.

5. Resistance to Change: Implementing reliability growth analysis may face resistance within organizations accustomed to traditional development and testing methodologies. Convincing stakeholders to adopt new approaches and invest in reliability improvement initiatives can be challenging.
   
# Assessment Using Reliability Demonstration Chart 

# 

# Comparison of Results

# Discussion on Similarity and Differences of the Two Techniques

# How the team work/effort was divided and managed

# 

# Difficulties encountered, challenges overcome, and lessons learned

# Comments/feedback on the lab itself
