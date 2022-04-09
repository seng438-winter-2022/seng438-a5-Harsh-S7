**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#:      |    28    |
| -------------- | -------- |
| Student Names: |          |
| Harshit Sharma | 30092470 |
| Heidi Toews    | 30094995 |
| Muhammad Khan  | 30092202 |
| Shamis Ali     | 30096335 |

# Introduction
The purpose of this lab is to learn about reliability assessment testing. We will first use the provided integration test data to perform the assessment using reliability growth testing. Then we will assess the system under test (SUT) using a reliability demonstration chart. Finally, we will discuss the differences between the two techniques. 

# Assessment Using Reliability Growth Testing 
Comparison of Top Two Models

<img width="631" alt="image" src="https://user-images.githubusercontent.com/56179869/162557334-7bb7f4e1-c603-41fe-94bd-07bdba03d982.png">

<img width="642" alt="image" src="https://user-images.githubusercontent.com/56179869/162557351-ddd2c9b4-e3a1-40e9-af59-881155a097ca.png">

As can be seen from the graph and chart, the 2 best models are DW3 and IFRGSB. This can mainly be shown from the likelihood column in the tabel where they had the highest scores. 

Range Analysis
As can be seen from the graphs below, these models are very close to the actual graphs and fit the distribution of the failure data accurately. Aside from a superficial look at the data, There doesn’t seem to be an ideal method to analyze this data with C-SFRAT. As such the whole range must be considered when looking for reliable data. 

Plots for Failure Rate and Reliability 

<img width="633" alt="image" src="https://user-images.githubusercontent.com/56179869/162558806-05d69fb1-8a06-4893-9a09-8ffea1143997.png">

<img width="647" alt="image" src="https://user-images.githubusercontent.com/56179869/162558811-f6737526-b855-44bd-a4a1-bcaa1e8dfa0f.png">

Decision Making Given a Target Failure

<img width="641" alt="image" src="https://user-images.githubusercontent.com/56179869/162558823-88704078-334d-4c6f-ae5e-a6dee5e2d29a.png">

After looking at the default failure intensity of 1.0, it was determined that it was not ideal 
and was too large for the given plot. As such, it was decided that cutting the intensity in half may end up yielding better results. After setting the intensity to 0.5, it was determined that this intensity was more ideal however it still had its own issues. The graph indicates that the target rate will be hit at an interval beyond the testing range. But the trend is colose enough to consider it valid and is far closer than anything higer than 0.5. 

Advantages and Disadvantages of Reliability Growth Analysis
Disadvantages:
-Different tools can bring different results. As such we decided to only stick to 1 for the report. 
-different methods to enter data with some methods taking longer than others. (i.e. csv vs excel vs txt files)
-models can very in effectiveness, (different models use different functions). So comparing models is essential.
-graphs can be difficult to analize when the tools have limited capabilities.

Advantages:
-due to the nature of reliability growth analysis, it is easy to see the effect of any thing that has potential to impact the results or development of a project. This is because of how each changes impact can be determined based on the time that change occurred.
-graphs that are created are an ideal way to determine any time based information and allow for accurate predictions.
 


# Assessment Using Reliability Demonstration Chart 
MTTF min

![image](https://user-images.githubusercontent.com/56179869/162557147-1b04d910-dba0-405a-b3ed-b4542e7d8562.png)

Double MTTF min

![image](https://user-images.githubusercontent.com/56179869/162557149-0930940f-f173-4ee7-8677-3ef0e6c3c24f.png)

Half MTTF min

![image](https://user-images.githubusercontent.com/56179869/162557153-5ae7e74b-8201-4a64-b973-b597d14e9c1a.png)

Observing Discrimination Ratio

![image](https://user-images.githubusercontent.com/56179869/162557158-fbed3a85-99c4-453c-89b7-5ebdc8a992f6.png)

Observing Customer Risk

![image](https://user-images.githubusercontent.com/56179869/162557170-ff4dea8e-0939-49bd-add3-782d0cda7b2c.png)

Observing Developer Risk

![image](https://user-images.githubusercontent.com/56179869/162557121-808a4daf-9d44-4ff4-9f40-8f0d75c10ed2.png)

To determine the MTTF min, we tested the system under various input parameters until the failure data barely crossed the acceptable line. 

We had also experimented with what if scenarios to understand the discrimination ratio, developer risk and customer risk and their impact on the failure plot. In this case when we change discrimination ratio value to double the original value, the acceptance and rejections both decrease by half thus lowering the range where more testing would be required. When we change the customer risk, the acceptance value decreases, thus making it easier to accept the value. When the developer risk is doubled, the rejection bar is actually decreased, thus making it easier to reject data

Advantages of RDC Testing
Time Efficient
Cost Efficient 
Versatile

Disadvantages of RDC Testing:
Only indicates whether the system under test is acceptable
Only demonstrates failure trend
High requirements of manual labor due to the various tests required to find MTTF min


# Comparison of Results
Although the RGT and RDC methodology had their similarities there were some major differences which created some fundamental changes within the processes.

The RGT had a major focus on the failure intensity, and this allowed us to focus on the failures with respect to time. We had to utilize laplace testing to convert the data to become useful. We also had to scrunch the data in order for it to fit the program. 

On the other hand, the RDF provided more information about the MTTFs which allowed our group to find the minimum MTTF. The MTTF output was useful as it allows the user to understand whether the system under test is able to utilize the system or not. 

Though both the RDC and RGT provide different results, the final conclusion drawn from the programs is the same, as the 2 processes allow the user to understand whether the system under test is useful or not or if more testing is needed. Comparing the two results, the MTTF min was 1.5 for our program from the RDC testing and it was 0.5 from RGA.


# Discussion on Similarity and Differences of the Two Techniques
Both reliability growth testing and reliability demonstration charts are used during integration testing to assess an SUT. Both techniques use inter failure time and either a target failure rate or a minimum time to failure. 
Reliability growth testing also uses failure count data. Reliability growth testing attempts to model previously gathered failure data, and then extrapolate that data into the future, to see how much more testing and debugging is required before the SUT can be accepted. 
Reliability demonstration chart uses three different types of risk in assessing the SUT. The first is product or measurement risk, which is the main risk component. The other two are customer risk and developer risk. Customer risk is the probability of wrongfully rejecting the SUT, while developer risk is the probability of wrongfully accepting the SUT. Reliability demonstration chart then uses these risk levels and the failure data to create a chart, which can be used to decide whether the SUT can be accepted or rejected, or whether more testing needs to be done first. 


# How the team work/effort was divided and managed
For this lab, we split into our usual pairs (Heidi & Harsh and Usman & Shamis). Usman and Shamis worked on assessment using reliability growth testing, while Heidi and Harsh worked on assessment using reliability demonstration charts. Then we switched and each pair went over the other’s work, to ensure that it had been done correctly and to make sure that everyone understood the entire lab. 

# Difficulties encountered, challenges overcome, and lessons learned
We had some difficulties setting up the reliability growth testing software. The SRTAT software did not work on any of our computers - it would set up and install, but did not load the provided data. Because of this, we used the C-SFRAT software instead, as it was easier to set up and was able to read the data. Other than that, the lab went relatively smoothly. 

# Comments/feedback on the lab itself
Overall, the lab was a good learning experience. More detailed instructions on the steps in parts 2.5.1 and 3.4.2 would have been appreciated, but we did figure it out in the end. We learned a lot about reliability assessment testing and the difference between reliability testing and reliability demonstration charts. 
