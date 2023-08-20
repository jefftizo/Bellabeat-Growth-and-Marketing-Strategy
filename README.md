# Bellabeat Growth and Marketing Strategy
## Empowering Women's Wellness: Unveiling Smart Device Insights for Bellabeat's Growth and Marketing Strategy
![bellabeat_logo](https://github.com/jefftizo/Bellabeat-Growth-and-Marketing-Strategy/assets/59502483/0677e3a0-1498-4fa4-9cd7-c52403eed833)

### **This project was done on R**

<div style="margin-bottom: 60px;">

**Prepared by:** [Mr. Jefferson Mwatati](https://www.linkedin.com/in/jefferson-mwatati/) 
**LinkedIn:** https://www.linkedin.com/in/jefferson-mwatati/
</div>

## **Business Task**
Bellabeat company is a high-tech manufacturer of health-focused products for women that provides users with health data related to their **activity, sleep, stress, menstrual cycle, and mindfulness habits**. The company wants to become a larger player in the global smart device market. By analyzing smart device fitness data on **how consumers are using their smart devices** could help unlock new growth opportunities for the company. The insights discovered will also help guide marketing strategy for the company. The key question for this analysis will be:-

1. What are some **trends in smart device** usage?
2. How could these trends apply to Bellabeat customers?
3. How could these trends help influence Bellabeat marketing strategy?

#### **The big question:** How Can Bellabeat Wellness Technology Company Play It Smart?

*"Any Woman Can Enjoy a Better, More Optimized Lifestyle"* [by Bellabeat Company](https://bellabeat.com/)

## Analysis
To see a complete analysis of this project done on R, check the "bellabeat_analysis.Rmd" it has everything

## **Visualizations and Key Findings**

**Below are some of the visualizations**

The plotted data represents the trend in total steps taken over a period of time. Initially, there is a gradual and consistent decline in the number of steps recorded with fluctuations, indicating a potential shift in activity levels. However, what stands out most prominently is the sudden and steep decline observed towards the end of the time frame. This sharp decline could signify a significant change in behavior or external factors impacting step count. Further investigation into this sharp decline could reveal valuable insights into the underlying reasons for the observed trend.
![total_steps](https://github.com/jefftizo/Bellabeat-Growth-and-Marketing-Strategy/assets/59502483/7e15b679-452f-44a1-9809-a6453bdbe121)


The presented plot illustrates a woman's consistent activity level in terms of total steps over the span of a month. Despite maintaining a steady performance, there are noticeable fluctuations on certain days, indicating variability in her routine. Some days stand out with notably higher step counts, showcasing her capacity for increased activity. However, as the month progresses, there's a gradual decline in her overall activity, suggesting a potential change in her exercise routine. 

![participant_trend](https://github.com/jefftizo/Bellabeat-Growth-and-Marketing-Strategy/assets/59502483/0782f901-6075-4886-a236-85a8e1295ae9)


This composite plot offers a comprehensive perspective on individual women's total steps over a 31-day span. Each woman's activity trend is depicted in a separate facet, allowing for direct comparison. While some exhibit consistent patterns with occasional fluctuations, others showcase varying levels of daily steps. 

![composite_plot](https://github.com/jefftizo/Bellabeat-Growth-and-Marketing-Strategy/assets/59502483/2b590191-1cad-4bfc-8f8e-a88a6b483657)




**2. Visualizations and Key Findings of "cleansleepday_df"**


The plotted data illustrates a distinct sleep pattern for 24 women over the course of a month. There is an initial decline in total minutes asleep, marked by numerous fluctuations characterized by alternating periods of increased and decreased sleep. Toward the end of the month, there's a pronounced steep decline in sleep duration. This trend suggests possible disruptions in sleep quality and consistency, highlighting the need for further investigation into factors impacting sleep patterns. 

```{r}
# Plot the trend in total minutes asleep over time

ggplot(TotalMinutesAsleep_by_date, aes(Date, total_minutes_asleep)) +
  geom_line(color = "darkblue", linewidth = 1.2) +
  labs(title = "Exploring Sleep Patterns: Total Minutes Asleep Over Time",
       subtitle=paste0("Analyzing Sleep Trends Across Dates for 24 Women"),
       caption=paste0("Prepared by Mr. Jefferson Mwatati"),
       x="Date",
       y="Total Minutes Asleep")

```



The displayed plot reveals a consistent downward trend in total time spent in bed for 24 women over the span of a month. Amidst this decline, there are notable fluctuations, with periods of increased and decreased bedtimes. Towards the final days, a sharp and significant drop in total time in bed is evident, indicating potential changes in sleep patterns or external factors influencing bedtime routines. 

```{r}
# Plot the trend in total time in bed over time

ggplot(TotalTimeInBed_by_date, aes(Date, total_time_in_bed)) +
  geom_line(color = "darkred", linewidth = 1.2) +
  labs(title = "Tracking Bedtime Trends: Total Time in Bed Over a Month",
       subtitle=paste0("Analyzing Bedtime Duration Patterns Across Dates for 24 Women"),
       caption=paste0("Prepared by Mr. Jefferson Mwatati"),
       x="Date",
       y="Total Time in Bed")

```



The depicted plot portrays a participant's inconsistent sleep pattern over a 31-day period. The total time spent in bed exhibits continuous fluctuations, with no discernible steady trend. These fluctuations suggest an unstable sleep routine, potentially influenced by various factors impacting the participant's bedtime habits.

```{r}
ggplot(fitnesswomenTTIB, aes(Date,TotalTimeInBed)) +
  geom_line(color = "maroon", linewidth = 1.2) +
  labs(title = "Exploring Bedtime Patterns: 31-Day Total Time in Bed Analysis",
       subtitle=paste0("Tracing a Participant's Bedtime Trends Over Time"),
       caption=paste0("Prepared by Mr. Jefferson Mwatati"),
       x="Date",
       y="Total Time in Bed")+
  theme_light()

```



The presented histogram provides insight into the distribution of sleep durations among participants. The x-axis represents the total minutes asleep, with the y-axis indicating the frequency of occurrences. The histogram showcases a range of sleep durations, from a minimum of 58 minutes to a maximum of 796 minutes, with an average of approximately 419.47 minutes.

```{r}
# Create a histogram to visualize the distribution of TotalMinutesAsleep

ggplot(cleansleepday_df, aes(x = TotalMinutesAsleep)) +
  geom_histogram(binwidth = 30, col = "white", fill = "darkred") +
  labs(title = "Understanding Sleep Duration Distribution",subtitle=paste0("Exploring the Spread of Total Minutes Asleep in a Dataset"),x = "Minutes Asleep", y = "Frequency", caption=paste0("Prepared by Mr. Jefferson Mwatati")) +
  theme_bw()

```



The histogram visualizes the distribution of total time spent in bed among participants. The x-axis represents the time in bed (in minutes), while the y-axis indicates the count of occurrences. The histogram showcases a range of bedtime durations, spanning from a minimum of 61 minutes to a maximum of 961 minutes, with an average duration of approximately 458.64 minutes.

```{r}
# Plot the distribution of total time in bed
ggplot(cleansleepday_df, aes(x = TotalTimeInBed)) +
  geom_histogram(binwidth = 10, col = "white", fill = "darkblue") +
  labs(title = "Exploring Bedtime Duration Distribution",subtitle=paste0("Analyzing the Spread of Total Time in Bed within the Dataset"), x = "Total Time in Bed (minutes)", y = "Count", caption=paste0("Prepared by Mr. Jefferson Mwatati")) +
  theme_light()
```



This scatter plot illustrates the connection between two variables: total minutes asleep and total time in bed. The x-axis represents the total minutes asleep, while the y-axis signifies the total time spent in bed. The green regression line highlights a strong positive correlation (0.920414) between these two variables. This indicates that as sleep duration increases, there is a tendency for longer time spent in bed.There are a few outliers on the scatter plot, which indicates that there are some people who do not follow the general trend. 

```{r}
# Create a scatter plot with regression line
ggplot(cleansleepday_df, aes(x = TotalMinutesAsleep, y = TotalTimeInBed)) +
  geom_point(color = "brown") +
  geom_smooth(method = "lm", se = FALSE,linewidth = 1.4, color = "green") +
  labs(x = "Total Minutes Asleep", y = "Total Time in Bed (minutes)", title = "Exploring the Relationship between Sleep Duration and Bedtime",subtitle=paste0("A strong positive correlation exists between total minutes asleep and total time in bed"), caption=paste0("Prepared by Mr. Jefferson Mwatati"))+
   theme_light()
  

```


**3. Visualizations and Key Findings of "cleanweightloginfo_df"**


The histogram displays the distribution of recorded weights in kilograms. The x-axis shows weight intervals of 9 kg each, while the y-axis represents the frequency of weights falling within each interval. The graph indicates a common weight range around 45-54 kg, with an average weight of 72.04 kg. The minimum and maximum weights are 52.6 kg and 133.5 kg, respectively.

```{r}
ggplot(cleanweightloginfo_df, aes(x = WeightKg)) +
  geom_histogram(binwidth = 9, fill = "blue", color = "black") +
  labs(x = "Weight (Kg)", 
       y = "Frequency", 
       title = "Distribution of Weight in Kilograms",
       subtitle=paste0("Frequency Distribution of Recorded Weights"),
       caption=paste0("Prepared by Mr. Jefferson Mwatati"))

```


The pie chart illustrates the distribution of manual and automatic reports. Manual reports make up the majority of the generated reports at 61%, indicating that a significant portion of data entry is done manually.
Automatic reports contribute to 39% of the total reports, suggesting that there's a mix of automated and manual data collection.

```{r}
# Create a pie chart with percentages
ggplot(grouped_IsManualReport, aes(x = "", y = no_of_reports, fill = factor(IsManualReport))) +
  geom_bar(stat = "identity", width = 1) +
  coord_polar("y", start = 0) +
  labs(fill = "IsManualReport",
       title = "Manual and Automatic Reports",
       subtitle=paste0("Proportion of Reports Generated Manually and Automatically"),
       caption=paste0("Prepared by Mr. Jefferson Mwatati")) +
  scale_fill_manual(values = c("TRUE" = "purple", "FALSE" = "orange")) +
  geom_text(aes(label = scales::percent(no_of_reports / sum(no_of_reports))), 
            position = position_stack(vjust = 0.5)) +
  theme_void()


```



The pie chart represents the distribution of different BMI categories among individuals. The largest portion of participants falls under the "Normal weight" category, constituting 50.7% of the individuals, indicating a significant proportion of healthy weight individuals.The "Overweight" category accounts for 47.8% of the distribution, suggesting a substantial proportion of participants are classified as overweight based on their BMI.While relatively small in proportion at 1.5%, the presence of individuals in the "Class III Obesity" category indicates that some participants have a severe level of obesity. 

```{r}
# Create a pie chart
ggplot(counted_categories, aes(x = "", y = Count, fill = BMI_Category)) +
  geom_bar(stat = "identity", width = 1) +
  coord_polar("y", start = 0) +
  labs(fill = "BMI Category",
       title = "BMI Category Distribution",
       subtitle=paste0("Proportion of Different BMI Categories Among Individuals"),
       caption = "Prepared by Mr. Jefferson Mwatati") +
  scale_fill_brewer(palette = "Set1") +  
  geom_text(aes(label = scales::percent(Count / sum(Count))), 
            position = position_stack(vjust = 0.5)) +
  theme_void()
```






## **A summary of analysis**

The analysis of the smart device data has revealed some interesting trends that could be applied to Bellabeat customers and inform their marketing strategy.Here are the key findings based on the analysis:

<div style="color: blue;">**There is a decline in activity levels over time.**</div> This is evident in the total steps taken, total distance covered, and calories burned data. This trend could be due to a number of factors, such as busy schedules, changes in weather, or simply boredom with the same old workout routine. Bellabeat could target their marketing efforts to encourage users to stay active, even when they're feeling unmotivated. They could offer new workout challenges, provide access to workout classes, or simply send motivational messages to their users.

<div style="color: blue;">**There is a lot of variability in sleep patterns.**</div> This is evident in the total minutes asleep and total time in bed data. Some users get a consistent 8 hours of sleep per night, while others have much more variable sleep patterns. Bellabeat could target their marketing efforts to help users improve their sleep quality. They could offer tips on sleep hygiene, provide access to sleep tracking apps, or even sell sleep products.

<div style="color: blue;">**There is a strong correlation between weight and BMI.**</div> This means that as weight increases, BMI also increases. This is to be expected, as BMI is a measure of body fat, and weight is a major component of body fat. Bellabeat could use this information to target their marketing efforts to users who are overweight or obese. They could offer weight loss programs, provide access to healthy recipes, or even sell fitness trackers.

<div style="color: blue;">**A large proportion of reports are manual.**</div> This suggests that there is a need for Bellabeat to improve their automated data collection process. They could invest in new software or hire more staff to help with data entry. This would free up their users to focus on their health and wellness goals, rather than spending time entering data manually.

<div style="color: blue;">**The majority of participants are classified as "Normal weight" or "Overweight."**</div> This suggests that Bellabeat has a good mix of users, from those who are looking to maintain a healthy weight to those who are looking to lose weight. Bellabeat could target their marketing efforts to both groups of users, offering different products and services to meet their individual needs.


#### **Influence on Marketing Strategy**

* **Activity-focused Campaigns:** Bellabeat can run campaigns promoting the benefits of consistent physical activity, highlighting the connection between activity levels and overall health. This can attract users who are looking for holistic health solutions.

* **Sleep Improvement Initiatives:** Marketing efforts can emphasize the importance of quality sleep and how Bellabeat's products can help users achieve better sleep patterns. Testimonials and success stories can reinforce these messages.

* **Personalized Weight Management:** Bellabeat can position itself as a comprehensive health companion by showcasing how its products help users manage their weight and BMI effectively. Educational content on weight management can establish the company as an authority in the field.

		

## **Recommendations Based on Analysis**

Here are the recommendations based on the analysis:

* **Create a challenge to encourage users to increase their activity levels.** This could be a step challenge, a distance challenge, or a calorie burn challenge. Bellabeat could offer prizes to the winners of the challenge to motivate users to participate.
* **Offer a sleep tracking app or program.** This would help users track their sleep patterns and identify areas where they can improve their sleep quality. Bellabeat could also offer tips on sleep hygiene and provide access to relaxing music or sounds to help users fall asleep.
* **Create a weight loss program.** This could include meal plans, workout routines, and support from a coach. Bellabeat could also offer discounts on fitness trackers or other products that can help users lose weight.
* **Improve their automated data collection process.** This would free up their users to focus on their health and wellness goals, rather than spending time entering data manually.
* **Target their marketing efforts to specific groups of users.** This could include users who are looking to maintain a healthy weight, users who are looking to lose weight, or users who are interested in improving their sleep quality.
* **Offer products and services that meet the individual needs of their users.** This could include fitness trackers, workout clothes, meal plans, or weight loss programs.
* **Add more data points to monitor users behavior.** This could include age,diet of food eaten every day, residence etc. This kind of data points will add to the analysis depth and understanding of the users.


#### **Recommendations for New Fitness Clients:**

* **Activity:** New fitness clients should aim for a daily step count and distance similar to the analyzed averages. Gradual increases in activity can lead to improved health outcomes.

* **Sleep:** Clients should focus on maintaining consistent sleep schedules and durations. Prioritizing sleep quality through relaxation techniques and sleep hygiene practices is essential.

* **Weight Management:** Clients should be educated about the correlation between weight and BMI. A balanced diet, regular exercise, and consultation with healthcare professionals can aid in achieving and maintaining a healthy weight.


In conclusion, the analysis of smart device data provides valuable insights for Bellabeat's growth strategy. By tailoring their products to address the identified trends and user needs, Bellabeat can enhance customer engagement and solidify its position as a leader in women's health technology. Additionally, implementing the recommended marketing strategies can help the company effectively communicate its value proposition to its target audience.



<div style="margin-bottom: 60px;">

**Prepared by:** [Mr. Jefferson Mwatati](https://www.linkedin.com/in/jefferson-mwatati/) 
**LinkedIn:** https://www.linkedin.com/in/jefferson-mwatati/
</div>

################################################################################
                                    **End of Report**






















