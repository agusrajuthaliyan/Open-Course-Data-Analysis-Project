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
5. [K Means Clustering](#5-k-means-clustering)
6. [Multinomial Logistic Regression](#6-multinomial-logistic-regression)
***

### **1. PROJECT BACKGROUND**

In the fifth semester, students across 12 departments gets to enroll in a course, out of 13 options. The students are mandated to fill in a form. The form requires students to fill in their informations such as gross points from the first two semesters, choice fillings from first to sixth along with their unique id and parent department information. The students will be elected based on the priority of choices and gross percentage scores.

***
### **2. ABOUT THE DATA**

The data was collected by the Department of Statistics. The mode of collection of data was facilitated by using [Google Forms](https://docs.google.com/forms/u/0/ "See Online💡") which the students had to fill in. Data from the year 2019 & 2020 were used conveniently for comparison purposes. The data collected was then made to undergo a few transformations and some basic cleaning in [Microsoft Excel](https://www.microsoft.com/en-us/microsoft-365/excel "See Online💡")

#### **2.1. Data Files :**
1. **[Allotment-Data-2019.xlsx](Data/Allotment-Data-2019.xlsx)**      
2. **[Allotment-Data-2020.xlsx](Data/Allotment-Data-2020.xlsx)**

#### **2.2. Data Info :**

|     | Rows | Columns |
|-----|------|---------|
|2019 | 368  |  10     |
|2020 | 413  |  12     |

#### **2.3. Columns :**

  - **Program** : The name of the "parent department" where students are from.
  - **ID** : The unique ID of the students.
  - **gp** : Gross Percentage score of students, it is calculated by taking the average scores of first two semesters.
  

``` math
gp = (\text{Sem I Score} + \text{Sem II Score}) / \text{Total Score in Both}
```

```math
  gp \space = \space {{Sem \space I \space Score + Sem \space II \space Score } \over Total \space Marks}
  ```
    
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
  3. B.Sc. Botany and B.Sc. Chemistry were the only two programs that had a decrease in average GP scores.
  4. Science subjects had a higher GP scores than arts subjects.
  5. B.Sc. Mathematics has the highest sverage gp scores in both years.
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
1. The departments B.Sc. Botany and B.Sc. Chemistry were the only two departments to have a decrease in the average gp score.
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
- For the art departments, it is less likely to be elected to the course of their choice.

***



  ### Count of Students in the Parent Department
  ![Image](Charts/Students-Distribution.png) \
*fig 1.0. showing the count of students in various departments.*

![image](Charts/Mean-GP-Dept-Bargraph.png)

![Popular Choices of Students](Charts/Pop-choices-both.png) \
*fig 2.0. showing the Total Count of Top 3 Choices received to Open Course Subjects.*


![Image](Charts\cluster\par-cluster-allot-19.png)


### **5. K-Means Clustering**
### **6. Multinomial Logistic Regression**