# EXNO2DS
# AIM:
To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT

    import pandas as pd
    df=pd.read_csv('titanic_dataset.csv')
    df

<img width="862" height="461" alt="image" src="https://github.com/user-attachments/assets/5735a3f4-9afc-4705-a063-88bee4d778a2" />

    df.shape

<img width="669" height="36" alt="image" src="https://github.com/user-attachments/assets/a6aab6af-66c1-4325-83c5-7b15a3c00c55" />

    df.set_index("PassengerId",inplace=True)
    df

<img width="874" height="460" alt="image" src="https://github.com/user-attachments/assets/189223dc-a080-457f-9989-7467b7a87e7e" />

    df.nunique()

<img width="243" height="199" alt="image" src="https://github.com/user-attachments/assets/c9170df6-cf94-4ec0-8aa0-c5cf748e5e56" />

    df['Sex'].value_counts()

<img width="346" height="84" alt="image" src="https://github.com/user-attachments/assets/625550af-dc66-473c-ad13-bec629b0e557" />

    df.Survived.unique()

<img width="430" height="34" alt="image" src="https://github.com/user-attachments/assets/c864dc3d-06e0-47c4-9586-c1acb4ae642a" />

    df.rename(columns={"Sex":"Gender"},inplace=True)
    df

<img width="851" height="485" alt="image" src="https://github.com/user-attachments/assets/3d52eaba-d3fb-4571-8b1d-2b523180b994" />

    import seaborn as sns
    sns.countplot(data=df)

<img width="622" height="412" alt="image" src="https://github.com/user-attachments/assets/ffb7d89c-de63-4b02-92e8-4938fe38688d" />

    sns.countplot(x="Survived",hue="Gender",data=df)
 
<img width="636" height="430" alt="image" src="https://github.com/user-attachments/assets/7654f282-4308-4e3b-897a-f229e3a57623" />

     sns.catplot(x="Survived",hue="Gender",data=df,kind="count")

<img width="686" height="485" alt="image" src="https://github.com/user-attachments/assets/a79232e2-1a22-4741-a550-05f1643da3e7" />

    sns.catplot(x="Survived",col="Gender",data=df,kind="violin")

<img width="874" height="447" alt="image" src="https://github.com/user-attachments/assets/9df036f9-def1-457e-b0c8-6d6d0a90d9e5" />

    sns.boxplot(data=df)

<img width="645" height="414" alt="image" src="https://github.com/user-attachments/assets/88eea813-3bbc-497d-8093-039cc2d98a78" />

    df.boxplot(column="Survived",by="Gender")

<img width="656" height="456" alt="image" src="https://github.com/user-attachments/assets/3e977b08-097a-4fee-8514-a6556d0412a1" />

    sns.scatterplot(data=df)

<img width="693" height="425" alt="image" src="https://github.com/user-attachments/assets/057f1121-1fcc-43f4-9e73-7acf7aa061e5" />

    sns.scatterplot(x=df['Age'],y=df['Fare'])

<img width="627" height="431" alt="image" src="https://github.com/user-attachments/assets/e16f0662-3317-4dd3-8944-c709dd72777c" />

    sns.jointplot(x='Age',y='Fare',data=df)

<img width="607" height="576" alt="image" src="https://github.com/user-attachments/assets/5d39fc14-fd22-4438-852d-c58cb796f4da" />

    sns.jointplot(x='Age',y='Fare',data=df,kind="kde")

<img width="666" height="572" alt="image" src="https://github.com/user-attachments/assets/11d3f37b-5283-4ec0-b40b-2619d8353369" />

    sns.jointplot(x='Age',y='Fare',data=df,kind="hist")

<img width="658" height="563" alt="image" src="https://github.com/user-attachments/assets/9989e0b1-0cb1-466c-8923-736425d549c2" />

     sns.pairplot(data=df)

<img width="551" height="568" alt="image" src="https://github.com/user-attachments/assets/b708da35-35d3-4001-8407-308fca6d6557" />

     corr1=df.select_dtypes(include=['number']).corr()
     sns.heatmap(corr1,annot=True)

<img width="567" height="413" alt="image" src="https://github.com/user-attachments/assets/8f9a4875-b7af-4ce2-a2a9-cdf13ba874c1" />

    sns.catplot(x='Gender',col='Survived',data=df,kind='count',color='green')

<img width="861" height="455" alt="image" src="https://github.com/user-attachments/assets/2a5e2c11-9ec2-419e-b77f-34fa3ceb4f61" />

# RESULT
    Hence performing Exploratory Data Analysis on the given data set is successful
