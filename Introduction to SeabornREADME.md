###Introduction to Seaborn###
##Making a count plot with a DataFrame##
# Import Matplotlib, Pandas, and Seaborn
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns


# Create a DataFrame from csv file
df=pd.read_csv(csv_filepath)

# Create a count plot with "Spiders" on the x-axis
sns.countplot(x='Spiders',data=df)

# Display the plot
plt.show()

##adding third variavle with hue 
##Hue and scatter plots
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Change the legend order in the scatter plot
sns.scatterplot(x="absences", y="G3", 
                data=student_data, 
                hue="location",
                hue_order=['Rural','Urban'])

# Show plot
plt.show()


##Hue and count plots
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create a dictionary mapping subgroup values to colors
palette_colors = {'Rural': "green", 'Urban': "blue"}

# Create a count plot of school with location subgroups
sns.countplot(x='school',data=student_data,hue='location',palette=palette_colors)



# Display plot
plt.show()


##Visualizing Two Quantitative Variables##
##Creating subplots with col and row
# Change this scatter plot to arrange the plots in rows instead of columns
sns.relplot(x="absences", y="G3", 
            data=student_data,
            kind="scatter", 
            row="study_time")

# Show plot
plt.show()


##Creating two-factor subplots##
# Adjust further to add subplots based on family support
sns.relplot(x="G1", y="G3", 
            data=student_data,
            kind="scatter", 
            col="schoolsup",
            col_order=["yes", "no"],
            row='famsup',
            row_order=['yes','no'])

# Show plot
plt.show()


##Changing the size of scatter plot points##
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create scatter plot of horsepower vs. mpg
sns.relplot(x="horsepower", y="mpg", 
            data=mpg, kind="scatter", 
            size="cylinders",hue='cylinders')

# Show plot
plt.show()


##Changing the style of scatter plot points
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Create a scatter plot of acceleration vs. mpg
sns.relplot(x='acceleration',y='mpg',data=mpg,kind='scatter',style='origin',hue='origin')



# Show plot
plt.show()


##Visualizing standard deviation with line plots##
# Make the shaded area show the standard deviation
sns.relplot(x="model_year", y="mpg",
            data=mpg, kind="line",ci='sd')

# Show plot
plt.show()


##Plotting subgroups in line plots##
# Import Matplotlib and Seaborn
import matplotlib.pyplot as plt
import seaborn as sns

# Add markers and make each line have the same style
sns.relplot(x="model_year", y="horsepower", 
            data=mpg, kind="line", 
            ci=None, style="origin", 
            hue="origin",
            markers=True, dashes=False)

# Show plot
plt.show()


###Visualizing a Categorical and a Quantitative Variable###
##Count plots##
# Separate into column subplots based on age category
sns.catplot(y="Internet usage", data=survey_data,
            kind="count",col='Age Category')

# Show plot
plt.show()

##Bar plots with percentages
# Create a bar plot of interest in math, separated by gender
sns.catplot(x="Gender",y='Interested in Math',kind='bar',data=survey_data)


# Show plot
plt.show()


##Customizing bar plots##
# List of categories from lowest to highest
category_order = ["<2 hours", 
                  "2 to 5 hours", 
                  "5 to 10 hours", 
                  ">10 hours"]


# Turn off the confidence intervals
sns.catplot(x="study_time", y="G3",
            data=student_data,
            kind="bar",
            order=category_order,ci=None)

# Show plot
plot.show()


##Create and interpret a box plot##
# Specify the category ordering
study_time_order = ["<2 hours", "2 to 5 hours", 
                    "5 to 10 hours", ">10 hours"]

# Create a box plot and set the order of the categories
sns.catplot(x='study_time',y='G3',data=student_data,kind='box',order=study_time_order)




# Show plot
plt.show()


##Omitting outliers##
# Create a box plot with subgroups and omit the outliers
sns.catplot(x='internet',y='G3',data=student_data,kind='box',hue='location',sym='')





# Show plot
plt.show()
