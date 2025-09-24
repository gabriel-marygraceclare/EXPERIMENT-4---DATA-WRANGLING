# EXPERIMENT-4---DATA-WRANGLING

This repository contains the following Programming Assignments

Experiment 4: Data Wrangling and Data Visualization

ECE Board Exam Problem link:  

### ECE Board Exam Problem

1. I started with importing the pandas libraries.
```python
import pandas as pd
```
2. Then, I used the read_excel() function from pandas to load the contents of the Excel file named 'board2.xlsx'.
```python
board_exam = pd.read_excel('board2.xlsx')
```
3. Finally, I displayed the contents of the DataFrame by simply typing the variable name. This will output the data in tabular form.
```python
board_exam
```

CREATING DATA FRAMES - INSTRU
1. After importing the pandas library, I applied .loc to select only the rows that meet the criteria.
```python
Instru = board_exam.loc[
    (board_exam['Electronics'] > 70) & 
    (board_exam['Track'] == 'Instrumentation') & 
    (board_exam['Hometown'] == 'Luzon'), 
    ["Name", "GEAS", "Electronics"]
]

```
2.Finally, I displayed the filtered DataFrame Instru to show the results that matched the given conditions.
```python
Instru
```

CALCULATING THE AVERAGE OF THE 4 SUBJECTS
1. After importing the pandas library and loading the file, I created a new column called "Average" in the Data Frame which contains the average scores for the students across 4 subjects.
```python
board_exam["Average"] = board_exam[["Math", "Electronics", "GEAS", "Communication"]].mean(axis=1)
```
2. Then, I displayed the updated board_exam DataFrame which now includes the "Average" column.
```python
board_exam
```

CREATING DATA FRAMES - MINDY
1. After importing the pandas library and loading the file, I, then filtered the data to show only female students from Mindanao who have an average score of 55 or above.
And from those results, I selected only the "Name", "Track", "Electronics", and "Average" columns.
```python
Mindy = board_exam.loc[
    (board_exam['Average'] >= 55) &
    (board_exam['Gender'] == 'Female') &
    (board_exam['Hometown'] == 'Mindanao'),
    ["Name", "Track", "Electronics", "Average"]
]
```
2. Then I displayed the data frame
```python
Mindy
```

Creating a visualization that shows how the different features contributes to average grade.
1. First, import the Matplot library
```python
import matplotlib.pyplot as plt
```
2. After loading the excel file and calculating the average, create a bar chart to visualize average scores and track.
```python
plt.bar(board_exam['Track'], board_exam['Average'])
```
3. Then the bar chart for the average and gender.
```python
plt.bar(board_exam['Gender'], board_exam['Average'])
```
4. Lastly, bar graph for average and hometown.
```python
plt.bar(board_exam['Hometown'], board_exam['Average'])
```
