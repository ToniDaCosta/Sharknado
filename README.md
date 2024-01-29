# Sharknado Intro:

- This is a project to learn how to clean data using several methods.

- A file with over 25.000 raws and 25 columns has been provided to start the proyect.

- In this file we can find several columns with usefull information like: number of attacks, dates, times, places, sharks species, countries, names, and sex of the people attacked, among them we will also find several raws and columns with empty or not usefull values.

# Goals:
- Scrub and clean the data until we can make it reusable to create charts and plots.

- Apply the methods learned so far to help you with the task at hand.

- Create charts and plots that can help you to present the information found.

---------------------  Set Up ---------------------------

# First:

- Within your Ironhack folder, create a "projects" directory.

- Create a repo on github. Don't worry too much about how to name it, you can change this in the future on the Settings tab on your repo. It can be "project-I" if you wish.

- Clone it into your projects directory.

Make sure it has the following documents (you can do this by using VSCode). Keep in mind when it has a slash it's a directory:
-->README.md
-->src/
-->cleaning.py
-->visualization.py
-->main.py
-->images/ 
-->data/
-->git add, commit and push!

# Second:

- start with downloading the csv file provided in : https://www.kaggle.com/datasets/teajay/global-shark-attacks

- Tip: file might need to be unzipped. 

- once the file is downloaded, is time to import these libraries:

        -import pandas as pd
        -import seaborn as sns
        -import matplotlib.pyplot as plt
        -import pandas as pd
        -import numpy as np

- now import the file to proyect sheet, using the following command:

- #data = pd.read_csv("data/attacks.csv", encoding = "ISO-8859-1", dtype=object)

# Codes and functions applied():

      -  .columns()
      -  .drop()
      -  .dropna()
      -  .head()
      -  .rename()
      -  .fillna()
      -  .astype(int)
      -  .range()
      -  .mean()
      -  pd.to_numeric()
      -  .drop_duplicates()
      -  .sort_values()
      -  .groupby()
      -  .round()
      -  .isin()
      -  .unique()
      -  .groupby()
      -  .size()
      -  .reset_index()
      -  .value_counts()
      -  .annotate()
      -  .notnull()
      -  .strip()


# Get ready to start with charts and plots :

- Dont forget to set parameters, use the following suggested :
```python
%matplotlib inline
%config Inlinebackend.figure_format= 'retina'
sns.set_context("poster")
sns.set(rc={"figure.figsize": (12.,6.)})
sns.set_style("whitegrid")
```

- Start creating subsets and filtering the data.

Final Tip : Dont recycle code, always right down in order what you want to apply, remember you will need to make the coding work from begining to end every time.


# Cheet samples for plots and charts : 

-------------------------------Atacks by Gender-----------------------------

`filtered_data = data[data['sex_'].isin(['F', 'M', 'undefined'])]`


unique_values = filtered_data['sex_'].unique()


palette = {'M': 'blue', 'F': 'pink', 'undefined': 'gray'}


ax = sns.barplot(x='sex_', y='count', data=filtered_data.groupby('sex_').size().reset_index(name='count'), palette=palette, hue='sex_', dodge=True)

ax.set_title('Number of Attacks by Gender', fontsize=25 )
ax.set_xlabel('Gender', fontsize=20)
ax.set_ylabel('Count', fontsize=20);

