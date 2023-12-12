# Open-Course-Elective-Choice-Trends-of-Students [2019-2020]
***Data Source*** : Department of Statistics, [Mar Athanasius College of Arts and Science (Autonomous), Kothamangalam](https://macollege.in)    
***Language*** : Python   
***Workflow*** : JupyterLab, Microsoft Excel

 **Certain columns with [Personally Identifiable Information [PII]](https://www.ibm.com/topics/pii "See Meaning💡") have been removed for privacy reasons.*
 
## TABLE OF CONTENTS :
1. [Project Background](#1-project-background)
2. [About the Data](#2-about-the-data)
3. [Project Summary](#3-project-summary) 
4. [Exploratory Data Analysis [EDA]](#4-exploratory-data-analysis-eda)
5. [K-Means Clustering](#5-k-means-clustering)
6. [Multinomial Logistic Regression](#6-multinomial-logistic-regression)

### **1. PROJECT BACKGROUND**

In the fifth semester, students across 12 departments gets to enroll in a course, out of 13 options. The students are mandated to fill in a form. The form requires students to fill in their informations such as gross points from the first two semesters, choice fillings from first to sixth along with their unique id and parent department information. The students will be elected based on the priority of choices and gross percentage scores.

***
### **2. ABOUT THE DATA**

The data was collected by the Department of Statistics. The mode of collection of data was facilitated by using [Google Forms](https://docs.google.com/forms/u/0/ "See Online💡") which the students had to fill in. Data from the year 2019 & 2020 were used conveniently for comparison purposes. The data collected was then made to undergo a few transformations and some basic cleaning in [Microsoft Excel](https://www.microsoft.com/en-us/microsoft-365/excel "See Online💡").

#### **2.1. Data Files :**
1. **[Allotment-Data-2019.xlsx](Data/Allotment-Data-2019.xlsx "Download")**      
2. **[Allotment-Data-2020.xlsx](Data/Allotment-Data-2020.xlsx "Download")**

#### **2.2. Data Info :**

|     | Rows | Columns |
|-----|------|---------|
|2019 | 368  |  10     |
|2020 | 413  |  12     |

#### **2.3. Columns :**

  - **Program** : The name of the "parent department" where students are from.
  - **ID** : The unique ID of the students.
  - **gp** : Gross Percentage score of students, it is calculated by taking the average scores of first two semesters.
  
 $$
gp = \frac{Sem \space I \space Score + Sem \space II \space Score}{Total \space Marks}
$$

    
  - **FC**  : First choice
  - **SC** : Second choice
  - **TC** : Third Choice
  - **FOC** : Fourth Choice
  - **FIC** : Fifth Choice
  - **SIC** : Sixth Choice
  - **Allotted Course** : The allotted course of the student.

#### **2.4. Departments :**

  1. *B.Com. Model I*
  2. *B.A. Economics*
  3. *B.A. Sociology*
  4. *B.A. English*
  5. *B.A. History*
  6. *Physical Education*
  7. *B.Sc. Chemistry*
  8. *B.Sc. Mathematics*
  9. *B.Sc. Statistics*
  10. *B.Sc. Zoology*
  11. *B.Sc. Botany*
  12. *B.Sc. Physics*
  13. *B.A. Hindi*
  
#### **2.5. Notations of Course Choices :**
  
  - **CO** : Course of **Commerce**
  - **EC** : Course of **Economics**
  - **SO** : Course of **Sociology**
  - **EN** : Course of **English**
  - **HI** : Course of **History**
  - **PE** : Course of **Physical Education**
  - **CH** : Course of **Chemistry**
  - **MA** : Course of **Mathematics**
  - **ST** : Course of **Statistics**
  - **ZO** : Course of **Zoology**
  - **BO** : Course of **Botany**
  - **PH** : Course of **Physics**
  - **HN** : Course of **Hindi**

***
### **3. PROJECT SUMMARY**
  1. Nearly 75% to 80% of students got their first choice as their allotted department.
  2. There was a general increase in the average gp of the entire college from 2019 to 2020.
  3. **B.Sc. Botany** and **B.Sc. Chemistry** were the only two programs that had a decrease in average GP scores.
  4. Science subjects had a higher GP scores than arts subjects.
  5. **B.Sc. Mathematics** has the highest sverage gp scores in both years.
  6. There were six students in the year 2020 who were admitted to a course outside of their choice.
  7. Science students have better chances of being admitted to the course of their choice compared to arts students.

***

### **4. EXPLORATORY DATA ANALYSIS [EDA]**

EDA is a very important step in a any data analysis project.

#### 4.1. Gross Percentage Descriptive Stats


| Department      |  Avg. GP 2019 | Avg. GP 2020 |  Change +/- |
|-----------------|------------|--------|---------|
| B.A Economics   |  47.69     | 56.23  | &#9650; | 
| B.A English     |  58.43     | 64.23  | &#9650; | 
| B.A Hindi       |  45.50     | 55.03  | &#9650; | 
| B.A History     |  46.51     | 50.29  | &#9650; | 
| B.A Sociology   |  43.22     | 53.01  | &#9650; | 
| B.Com Model I   |  65.70     | 75.01  | &#9650; | 
| B.Sc Botany     |  68.83     | 64.07  |🔻      | 
| B.Sc Chemistry  |  76.37     | 75.69  |🔻      |
| B.Sc Mathematics|  76.67     | 78.30  | &#9650; |
| B.Sc Physics    |  67.98     | 76.24  | &#9650; |
| B.Sc Statistics |  71.97     | 76.46  | &#9650; |
| B.Sc Zoology    |  61.14     | 63.06  | &#9650; |

*Table 1.0.  shows the department wise average Gross Percentage of students and the change from years 2019 and 2020.*
From the above Table we can observe the following:
1. The departments **B.Sc. Botany** and **B.Sc. Chemistry** were the only two departments to have a decrease in the average gp score.
2. Science departments have higher average scores than most arts courses.

***


##### 4.1.1. GP Descriptive Stats 2019

| Department       | count  | mean	| std	| min	|  25%	| 50%   | 75%	| max   |
|------------------|--------|-------|-------|-------|-------|-------|-------|-------|
| B.A Economics	   | 35.0	| 47.70	| 22.44 | 0.00  | 32.82	| 44.10 | 70.30 | 76.90 |
| B.A English	   | 35.0	| 58.44	| 20.54	| 10.60 | 37.90 | 63.80	| 75.60	| 87.40 |
| B.A Hindi	       | 22.0	| 45.50	| 23.93	| 7.00	| 26.10 | 47.00	| 62.67	| 84.17 |
| B.A History	   | 36.0	| 46.51	| 17.07 | 13.40	| 32.98	| 49.20	| 55.98	| 87.20 |
| B.A Sociology    | 33.0	| 43.22	| 21.45 | 5.00  | 29.00	| 44.60	| 59.00	| 87.70 |
| B.Com Model I	   | 50.0	| 65.70	| 16.78	| 23.00 | 60.04	| 71.71	| 76.98	| 88.58 |
| B.Sc Botany	   | 28.0	| 68.84	| 13.90 | 31.17	| 64.19	| 71.21	| 79.62	| 85.42 |
| B.Sc Chemistry   | 24.0	| 76.37	| 15.43 | 34.83	| 67.33	| 82.46	| 87.77 | 92.25 |
| B.Sc Mathematics | 25.0	| 76.67	| 12.67 | 36.24	| 70.48	| 76.50	| 87.17	| 91.92 |
| B.Sc Physics	   | 23.0	| 67.99	| 18.20	| 29.17	| 56.88	| 75.08	| 79.79 | 89.75 |
| B.Sc Statistics  | 29.0	| 71.97	| 10.47	| 47.67	| 65.58	| 74.08	| 78.08 | 88.67 |
| B.Sc Zoology	   | 28.0	| 61.14	| 16.95	| 24.17	| 52.63	| 65.09	| 74.17	| 88.50 |

*Table 1.1.  shows the department wise descriptive statistics of Gross Percentage in the year 2019.*

***
##### 4.1.2. GP Descriptive Stats 2020

|Department        | count	| mean|	std	    |  min	| 25%	|  50%	|  75%  |   max|
|------------------|--------|-----|---------|-------|-------|-------|-------|------|
|B.A Economics	   | 49.0	|56.23|	22.00   |8.70	|38.20	|58.80	|74.90  |87.20|
|B.A English	   | 40.0	|64.24|	16.89	|30.50	|48.00	|68.20	|79.80	|88.70|
|B.A Hindi	       | 29.0	|55.04| 22.11	|16.33	|35.50	|48.33	|76.17	|90.83|
|B.A History	   | 42.0	|50.29|	22.92	|0.00	|36.65	|54.25	|66.55	|89.50|
|B.A Sociology	   | 43.0	|53.02|	15.75   |15.60	|43.95	|55.90	|62.45	|81.70|
|B.Com Model I     | 51.0	|75.01|	16.00	|27.67	|67.96	|79.58	|87.21	|93.33|
|B.Sc Botany	   | 23.0	|64.07|	22.31	|15.50	|54.92	|73.92	|78.46	|87.08|
|B.Sc Chemistry	   | 26.0	|75.69|	16.32	|37.00	|71.19	|82.87	|86.73	|92.83|
|B.Sc Mathematics  | 25.0	|78.30|	12.02	|50.58	|75.67	|81.33	|86.50	|90.67|
|B.Sc Physics	   | 29.0	|76.24|	12.36	|38.58	|69.33	|80.25	|85.25	|93.17|
|B.Sc Statistics   | 27.0	|76.47|	16.57	|29.25	|71.58	|81.58	|88.88	|92.25|
|B.Sc Zoology	   | 29.0	|63.07|	16.63	|28.92	|50.33	|65.92	|78.42	|89.08|

*Table 1.2.  shows the department wise descriptive statistics of Gross Percentage in the year 2020.*

***

##### 5.0. A Rather Miss-Happenning in 2020

|   ID    |    Program   |      gp   |
|---------|--------------|-----------|
|   1020  | B.A Economics|  67.700000|
|   1038  | B.A Economics|  65.100000|
|   1066  |  B.A English |  30.500000|
|   1099  |    B.A Hindi |  43.666667|
|  1109   |   B.A Hindi  |  18.500000|
|  1133   |  B.A History |  47.900000|

*Table 1.3. showing the students who were not admitted to any of their 6 choice preferences.*

***

|    Department   | Top Allotted [2019] | Top Choice [2019] | Top Allotted [2020] | Top Choice [2020] |
|-----------------|-----|----|----|----|
| B.A Economics   |  CO | ST | CO | CO | 
| B.A English     |  SO | SO | SO | PE |
| B.A Hindi       |  EN | SO | BO | HI |
| B.A History     |  EC | EC | EN | SO |
| B.A Sociology   |  HI | HI | EC | HI |
| B.Com Model I   |  ST | ST | ST | ST |
| B.Sc Botany     |  CH | CH | ZO | ZO |
| B.Sc Chemistry  |  MA | MA | MA | MA |
| B.Sc Mathematics|  ST | ST | CO | CO |
| B.Sc Physics    |  CO | CO | MA | MA |
| B.Sc Statistics |  MA | MA | CO | CO |
| B.Sc Zoology    |  CH | CH | CH | CH |

*Table 2.0.  Table depicting the Top Choice and the Top Allotted Course of each parent department on both years.* 
- The science departments have been mostly admitted to the course of their choice.
- For students in the art departments, it is less likely that they get elected to the course of their choice.

***



### **Distribution of Students in Parent Departments [2019-2020]**
  ![Image](Charts/Pie-chart/Students-Distribution.png)   
*fig 1.0. showing the proportion and count of students in various departments.*

- The department with the most students are in **B. Com Model I** on both 2019 and 2020.
- The department with the least students is **B.A. Hindi** in 2019 and **B.Sc. Botany** in 2020.

***

### **Average Department-Wise GP [2019-2020]**
![image](Charts/Bar-plots/Mean-GP-Dept-Bargraph.png)
*fig 2.0. shows the department-wise average GP scores of students.*
- In the year 2019, **B.Sc. Mathematics** had the highest average GP scores followed by **B.Sc. Chemistry** and **B.Sc. Statistics**, while the least GP scores obtained was by **B.A. Sociology**.
- In 2020, **B.Sc. Mathematics** had the highest GP closely followed by **B.Sc. Statistics** and **B.Sc. Chemistry**.

***

### **Change in GP Score from (2019 - 2020)**
  ![image](Charts/Bar-plots/GP-Change-Bar.png)
  *fig 2.1. showing the change in the average GP score of departments as observed from 2019 to 2020.*
  - The arts subjects namely **B.A. Sociology** (+23%), **B.A. Hindi** (+21%) and **B.A. Economics** (+18%) had a great deal of improvement.
  - While most departments saw an increase in the GP scores, the Departments **B.Sc. Botany** had a significant fall of nearly (-7%) followed by **B.Sc. Chemistry** (-1%).

***



### **Boxplots - GP Scores (2019-2020)**
![Image](Charts/Box-plots/GP-Boxplot.png)
*fig. 2.2. shows the boxplots of GP scores in both years*
- It can be observed that, even though there have been a general increase in the average GP scores of departments, [outliers](https://mathworld.wolfram.com/Outlier.html "See Definition!") have also had a significant increase in the year 2020 as compared to 2019.
- It is found out that most Science departments had outliers.

***


### **Lineplot of GP Scores (2019-2020)**
![image](Charts/Line-plots/GP-lineplot.png)
*fig. 2.3. shows the line plot of departments*
- The general increase in GP score trend as verified from the other plots have also been observed here.

***


### **Probability Distribution Plot - GP Scores (2019-2020)**
![Image](Charts/Hist-plots/GP-Distplot.png)
*fig. 2.4. shows the layered [probability density plot](https://www.khanacademy.org/math/statistics-probability/random-variables-stats-library/random-variables-continuous/v/probability-density-functions) of GP scores in both years*
- There is a general trend pointing that there has been an increase in the GP scores of departments.

***


### **Top Popular Open Course Subjects (2019-2020)**

![Popular Choices of Students](Charts/Bar-plots/Pop-choices-both.png)  
*fig 3.0. showing the Total Count of Top 3 Choices received to each Open Course Subjects.*
- On both years, It is evident that the open course subject of **Sociology** had the most demand followed by **Economics**.
- While **Hindi** had received the least of interest from the students.

***


### **Top Choice Allotted Proportion (2019-2020)**

![Chart](Charts/Bar-plots/FA-FC-ALlot-Prop.png)
*fig 4.0. shows the proportion of students being allotted to the first choice*
- We can observe that on both years, nearly 80% of students were usually admitted to the first choice that they preferred.

***

### **Heatmap - Allotment Proportion of Parent Departments (2019-2020)**

![Heatmap](Charts/Heatmaps/Parent-Allot-Heatmap.png)
*fig 5.0. Heatmap showing the proportion of students from parent department to the allotted open course subjects*
- The above [heatmap](https://www.hotjar.com/heatmaps/ "See Online💡") depicts a general trend where students in the art departments are allotted to another art departments and vice-versa for science departments.
- There were less consolidation of students in 2020 as compared to that in the year 2019, As a result we are able to observe that students have been distributed ti different courses.

***

### **Heatmap - Change in Allotment Proportion of Parent Departments (2019-2020)**

![Heatmap](Charts/Heatmaps/Parent-Allot-Change.png)
*fig 5.1. Heatmap showing the proportion of students from parent department to the allotted open course subjects*
- There was a significant increase in the students being admitted from **B.Sc. Mathematics** to **Commerce**, **B.Sc. Physics** to **Sociology** and to **Mathematics**.
- There was a significant decrease in the students being admitted from **B.Sc. Physics** to **Commerce**, **B.Sc. Botany** to **B.Sc. Chemistry. [See Fig 5.1 for more]

***

### **Top Parent Department Allotments (2019-2020)**
![Network Diagram](Charts/Network-plots/TOP-ALLOT-COURSE-NTQ.png)
*fig 5.2. [Network Diagram](https://acqnotes.com/acqnote/tasks/network-diagram "See Online💡") showing the top course allotted by each parent department*
- In the year 2019, **Statistics**, **Mathematics**, **Commerce** and **Chemistry** had students allotted from more than one departments.
- In the year 2020, due to less consolidation only two courses had students being allotted from parent departments. As a result **Commerce** and **Mathematics** are the subjects with more than one departments.

***

### **Heatmap - Allotment Proportion in Open Course Subjects (2019-2020)**
![Heatmap](Charts/Heatmaps/Target-Allot-Heatmaps.png)
- The general trend observed is similar to that from *[fig 5.0](#heatmap---Allotment-proportion-of-parent-departments-2019-2020)* where students in arts subjects are mostly from art departments and vice-versa for science open course subjects.
- **Economics** and **English** subjects had a healthy mix of students from multiple departments in both years.
- **B.Sc Zoology** students have a significant proportion in Chemistry open courses in both years. Likewise, **B.Com Model I** students also has a great presence in **Statistics**.
- **B.A. History** students have a notable presence in **Hindi** open courses in 2019 but not in 2020.

***

### **Heatmap - Change in Allotment Proportion in Open Course Subjects (2019-2020)**

![Heatmap](Charts/Heatmaps/Target-Allot-Change-Heatmap.png)
*fig 5.3. shows the change in allotment proportion trends in the open course subjects*
- There was a steady increase in the **B.A. Economics** students being present in the **English** course (+31%) and **B.A. Hindi** students in **Botony** (+23%).
- **Economics** saw a decrease in the students coming from **B.A. History**.

***

### **Top Open Course Allotments (2019-2020)**
![Network Diagram](Charts/Network-plots/TOP-RECEIVED-Program-NTQ.png)
*fig. 5.4. shows the top parent program received in the open course subjects*
- Arts subjects contributed more to certain departments while the science students were spread equally across departments.
- In 2019, **B.A. History**, **B.A. Sociology**, **B.Com. Model I**, **B.Sc. Botany** contributed to multiple departments.
- In 2020, similarly **B.A. History** ,**B.A. Sociology**, **B.Com. Model I** and **B.A. Economics** contributed more to various departments.

***

### **Heatmap - First Choice (2019-2020)**
![Heatmap](Charts/Heatmaps/FC-Heatmap.png)
*fig. 5.5. shows the first choice proportion of students*
- Yearly Consistency: The pattern of preference remains relatively consistent between 2019 and 2020.
- On both years B.Sc. Zoology** students preferred **Chemistry**, similarly similar interest were also observed from **B.Sc. Chemistry** to **Mathematics** and from **B.Com Model I** to **Statistics**

***

### **Heatmap - Change in First Choice (2019-2020)**
![Heatmp](Charts/Heatmaps/FC-Change-Prop_Heatmap.png)
*fig. 5.6 shows the change in first choice proportions of students*
- An increase in the interest of (+32%) from **B.Sc. Mathematics** to **Commerce** was observed. A similar interest was also observed from **B.Sc. History** to **Physical Education**.
- A significant decrease of (-55%) was observed from **B.Sc. Botany** to **Chemistry**.

***
### **Top Choices (2019-2020)**
![Network diagram](Charts/Network-plots/TOP-FC-NTQ.png)
*fig. 5.7. showing the network diagram representing the top elective course prefered by departmeants*
- In 2019, **Mathematics** and **Physical Education** was the top choices of students in nearly 3 parent departments.
- In 2020 however **Commerce** was the only subject to have had the top choices of students. **Mathematics** and **History** were other course receiving high demands of choices.
- On both years **Physics**, **Hindi**, **English** and **Hindi** were courses with little to no choice applications. 




### **5. K-Means Clustering**
### **6. Multinomial Logistic Regression**