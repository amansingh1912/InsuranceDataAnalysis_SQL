# Insurance Data Analysis Using SQL

![Insurance data](https://user-images.githubusercontent.com/72240938/211582101-90824a58-a43f-4521-b2de-5e9dc61dace3.jpeg)

## Overview:

I came up with few questions regarding Insurance Data and for them I wrote SQL queries for the analysis:

### Questions with Code and answer:

Q1) Find Total Sum of Charges from Insurance Data where Sex is Male and not a smoker ( Code including Output)
Ans:

### Code:
SELECT ROUND(SUM(charges)) as TotalCharges from `insurance` where
sex= "Male" and smoker = "No";

### Output:
4181085

Q2) Find Total Sum of Charges from Insurance Data where Sex is Male and a smoker (Code including Output)
Ans:

### Code:
SELECT ROUND(SUM(charges)) as TotalCharges from `insurance` where
sex= "Male" and smoker = "Yes";

### Output:
5253679

Q3) Find region wise total charges from Insurance Data 
Ans:

### Code:
SELECT region, ROUND(SUM(charges)) as TotalCharges from `insurance`
group by region
order by TotalCharges desc;

### Output:
Northeast -> 4343669
Southeast -> 5363690
Southwest -> 4012755
Northwest -> 4035712


Q4) Make a age range column extra in the table where mention the Age range like "Under 20", "20-30", "31-50" and "above 50".
Ans:

### Code:
UPDATE insurance
SET `age range`= "Under 20"
where age<20;

UPDATE insurance
SET `age range`= "20-30"
where age>=20 and age<=30;

UPDATE insurance
SET `age range`= "31-50"
where age>30 and age<=50;

UPDATE insurance
SET `age range`= "Above 50"
where age>50;


Q5) Find Age Range with total charges from insurance.
Ans:

### Code:
SELECT `age range`, ROUND(SUM(charges)) as TotalCharges from insurance
group by `age range`
order by TotalCharges desc;

### Output:
Under 20:137
20-30: 307
31-50 : 538
Above 50:  356


Q6) Find average bmi from insurance.
Ans:

### Code:
SELECT ROUND(avg(bmi)) from insurance;

### Output:
Avg bmi index of insurance is 31.

Q7) Find no. of smoker types from insurance.
Ans:

### Code:
SELECT smoker, COUNT(*) AS TotalCount from insurance
group by smoker
order by TotalCount desc;

### Output:
No. of non-smokers: 1064
No. of smokers: 274




