# Data-Analysis-Project
  This repository contains Python code for analyzing and visualizing data from a CSV file (data.csv). The project utilizes Pandas for data manipulation, and Matplotlib and Seaborn for data visualization. The dataset contains information about countries, including their birth rate, internet usage, and income group. Various analyses are performed, including filtering, statistical analysis, and visualizations.

**Project Structure**  
  -data.csv: The dataset containing country-related data such as country name, country code, birth rate, internet users, and income group.  
  -data_analysis.ipynb: Jupyter notebook that contains the analysis and visualization steps applied to the CSV data.

**Features**  
  -Data Inspection: The notebook performs basic data exploration using methods such as .head(), .tail(), .info(), and .describe() to understand the structure and summary statistics of the dataset.  
  -Data Manipulation:  
       -Renaming columns for easier understanding.  
       -Adding and dropping columns.  
       - Filtering data based on conditions.  
  -Visualizations:  
      -Distribution Plot: Displays the distribution of internet users using Seaborn's distplot().  
      -Box Plot: Visualizes the relationship between income group and birth rate using boxplot().  
      -Scatter Plot / Regression Plot: Uses lmplot() to analyze the relationship between birth rate and internet users.  

**Data Analysis Workflow**  
  1.Loading the Data: The dataset is loaded from a CSV file using pd.read_csv() and stored in a pandas DataFrame (df).  
              df = pd.read_csv(r'C:\\path\\to\\data.csv')  
  2.Data Exploration:  
            -Use .shape, .columns, .info(), .head(), .tail(), and .describe() to inspect the structure of the data.  
                  df.shape  
                  df.head()  
                  df.describe()  
  3.Data Cleaning:  
            -Rename columns for easier understanding.  
                  df.columns = ['CountryName', 'CountryCode', 'BirthRate', 'InternetUsers', 'IncomeGroup']  
            -Add a new calculated column myCalc and then drop it.  
                  df['myCalc'] = df.BirthRate * df.InternetUsers  
                  df = df.drop('myCalc', axis=1)  
  4.Filtering Data:  
           -Filter the data based on specific conditions, such as countries with less than 2 internet users or birth rates above 40.  
                Filter = df.InternetUsers < 2  
                df[Filter] 
  5.Visualizations:  
          -Distribution Plot: To visualize the distribution of internet users.  
                vis1 = sns.distplot(df["InternetUsers"])  
                plt.show() 
          -Box Plot: To visualize birth rates across income groups.  
                vis2 = sns.boxplot(data=df, x="IncomeGroup", y="BirthRate")  
                plt.show()  
          -Linear Regression Plot: Visualizing the relationship between internet usage and birth rate.  
                vis3 = sns.lmplot(data=df, x='InternetUsers', y='BirthRate', fit_reg=True, hue='IncomeGroup')  
                plt.show()  

**Outputs**  
-Statistical Summaries: Outputs from .describe(), .head(), and .tail() help understand the basic statistics and structure of the data.  
-Filtered Data: Output from filtering conditions, such as countries with internet users below 2 or birth rates above 40.  
-Visualizations:  
          A distribution plot showing the spread of internet users across the dataset.  
          A box plot comparing birth rates across income groups.  
          Linear regression plots showing the relationship between internet usage and birth rate.  

**Example of Data Exploration Output**  
      df.head() 
      This will display the first few rows of the dataset to give you an idea of what the data looks like.  

  sns.distplot(df["InternetUsers"])  
  plt.show()  
This will display a distribution plot of internet users across the countries.  
