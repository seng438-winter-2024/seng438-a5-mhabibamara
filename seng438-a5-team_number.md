**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#:       |   |
|-----------------|---|
| Student Names:  | Mohamed Amara  |
|                 | Nour Ajami  |
|                 | Krishna Shah  |
|                 | Zuhaer Rahman  |

# Introduction
The main purpose of this lab is to build upon the knowledge regarding Reliability Growth Testing that we learned in our lectures. In order to better understand Reliability Growth Testing and the Reliability Demonstration Chart we used tools such as SRTAT, C-SFRAT and RDC-11. This lab also introduced us to the concept of using failure data in order to better our application and analyze this data so we can prevent future failures. 
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
Figure 1: 1 Failure per 500 calls

![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/942b79e6-66b1-41c1-b98f-96e6f559804c)


Figure 2: 1 Failure per 1000 calls

![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/8a136e4e-a582-4151-9a46-1537c480a546)


Figure 3: 1 Failure per 2000 calls

![image](https://github.com/seng438-winter-2024/seng438-a5-mhabibamara/assets/103873879/b532b3b2-82b5-4a50-989a-3aace91b7c7f)


As you can see in Figure 1 & 2 when using data where a failure would only occur every 500 or 1000 calls, this would result in acceptable behaviour from the program as the observed failures was mostly in the green section. However, when using data where a failure would occur every 2000 calls this resulted in unaccapteable output as the observed failure were almost entirely in the red section.

The MTTF value selected for this graph was determined through looking at the data and aiming for a value where the RDC was mostly in the continuous testing range. The value chosen was effective in showcasing the impacts of halving and doubling the MTTF, which is shown in the figures above. When increasing the input data set to only allow 1 failure for every 1000 seconds, we noticed that observed failures are signficicantly more in the red section as the software needs to only allow specific failures.


# Comparison of Results
Through RGT, our iterative testing approach facilitated early failure detection and systematic improvement. Analysis of RGT data revealed a progressive reduction in cumulative failures over time, indicative of enhanced reliability through iterative design modifications. Additionally, trend analysis of failure data allowed for targeted improvements, enabling the mitigation of potential failure modes. In contrast, RDC provided a static assessment of reliability against predefined targets. Our RDC analysis demonstrated the system's reliability performance within specified confidence bounds, aiding in compliance assessment and decision-making regarding system release. While RGT emphasized dynamic improvement through iterative testing and trend analysis, RDC offered a structured approach to validate reliability against predetermined targets, enabling comprehensive risk management throughout the system's development lifecycle.

In conclusion, both Reliability Growth Testing and Reliability Demonstration Chart methodologies offer unique insights into system reliability. While RGT facilitates iterative improvement through proactive failure detection and trend analysis, RDC provides a structured framework for validating reliability against predefined targets. By integrating these methodologies, organizations can establish a comprehensive reliability management strategy, effectively addressing both early-stage failures and compliance with reliability specifications.
# Discussion on Similarity and Differences of the Two Techniques
Similiarites:
* Visual Reliability of Tools: Both methods provide a graphical representation to aid in the visualization of reliability data. This makes it clear and easier for test engineers and decision-makers to understand complex reliability and make informed decisions
* Failure Time and Mean Time to Failure (MTTF): Both methods can be utlizied to analyzie failure times and calculate the MTTF, which is a crucial component for reliability metric to indicate the time between failures
* Assessment of System Reliability: Growth Anaysis testing and RDC charts are both valuable for evaluating how reliable a system is under certain and specific conditions. Overall they help us to understand the robustness of a system and its ability to perform its required function without failures

Differences:

* Reliability Growth Analysis Focuses on Failure Rate: The primary focus for reliability growth analysis is on the failure rate and how it changes over time. The goal is often to demonstrate a decreasing trend in failures rates, which indicate reliability growth.
* Predicting Failure Trends (Reliability Growth Analysis): By analyzing the trend of failures during the testing phase, the anaylsis can predict how the system's reliability will evolve with further development and refinement.
* RDC (Acceptance Criteria): The RDC chart is focus on wether a system meets predefined reliability criteria. The chart provides a clear decision on whether a system is acceptable or needs further improvement, making it a critical tool in the decision-making process.
* RDC (Time to Failure)**: The RDC chart focuses on specific time-to-failure data to decide Whether the SUT is acceptable or not.
# How the team work/effort was divided and managed

We initally had a group discussion on how to divide and handle the work and we decided it was best for us to work on both sections of the lab together so that everyone could gain a strong understanding
of all the work being done. We held 2 meetings during the course of the assignment, 1 for the Reliability Growth Testing and another for the Reliability Demonstration Chart. By working as a collective we ensured that we all learned how to use the tools and were able to get past any hurdles quickly.

# Difficulties encountered, challenges overcome, and lessons learned
The biggest difficulty and challenge that we had to overcome was a lack of understanding on how to create a valid input data set (for the tools that we were using) from the invalid data given to us. Since the instructions given to us in the report document were quite vague, as well the documentation to be unhelpful, we found ourself stuck on this portion of the assignment for quite some time. Some lessons that we learned was to ask for help from a TA sooner rather then later, as this would have saved us some time.

# Comments/feedback on the lab itself
The only comment we have regarding the lab goes hand-in-hand with the challenges our team faced. We and many other groups found ourselves stuck early on into this lab as either the tools were not running properly on some operating systems or the information regarding creating a input set was quite vague and confusing. We believe if there was cleaner failure data given or more instruction on how to create a valid input, this lab would have gone much smoother.
