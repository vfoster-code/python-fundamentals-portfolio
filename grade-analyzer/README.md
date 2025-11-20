# Grade Analyzer

A Python project demonstrating data transformation from messy string data to structured pandas DataFrames, with grade calculation and analysis.

## Project Overview

This project transforms raw student grade data from inconsistently formatted strings into a clean, structured DataFrame. It showcases data parsing, nested data structures, calculation logic, and the transition from basic Python to pandas.

## Problem Statement

Process student data that contains:
- Mixed case names (uppercase, lowercase, title case)
- Comma-separated test scores as strings
- Data in "name:score1,score2,score3..." format

Transform this into a structured format with:
- Clean, standardized names
- Individual test scores as integers
- Calculated averages
- Letter grade assignments
- Final pandas DataFrame for analysis

## Features

### Multi-Step Data Pipeline

**Step 1: Parse Structure**
- Split name from scores
- Separate individual test scores
- Convert strings to appropriate data types

**Step 2: Clean Data**
- Standardize names to title case
- Convert score strings to integers
- Create nested list structure

**Step 3: Calculate Metrics**
- Compute average scores for each student
- Assign letter grades based on averages
- Build dictionary with all student data

**Step 4: Structure Data**
- Convert dictionary to pandas DataFrame
- Organize data for easy analysis

## Code Highlights

### Data Parsing
```python
for i in range(len(students)):
    students[i] = students[i].split(':')  # Split name from scores
    students[i][1] = students[i][1].split(',')  # Split individual scores
```

### Data Cleaning
```python
for student in students:
    student[0] = student[0].title()  # Standardize names
    for i in range(len(student[1])):
        student[1][i] = int(student[1][i])  # Convert scores to integers
```

### Grade Assignment Logic
```python
if score >= 90:
    students_dict['letter_grade'].append('A')
elif score >= 80:
    students_dict['letter_grade'].append('B')
elif score >= 70:
    students_dict['letter_grade'].append('C')
elif score >= 60:
    students_dict['letter_grade'].append('D')
else:
    students_dict['letter_grade'].append('F')
```

### DataFrame Conversion
```python
import pandas as pd
students_df = pd.DataFrame(students_dict)
```

## Sample Output

### Final DataFrame
```
  student_name           test_scores  score_avg letter_grade
0        Alice  [85, 92, 78, 90, 88]       86.6            B
1          Bob  [95, 89, 94, 91, 93]       92.4            A
2      Charlie  [72, 68, 75, 70, 71]       71.2            C
3        Diana  [88, 85, 90, 87, 89]       87.8            B
4          Eve  [60, 65, 58, 62, 61]       61.2            D
```

## Skills Demonstrated

### Python Fundamentals
- **List Manipulation**: Nested lists, list comprehension concepts
- **String Methods**: `.split()`, `.title()` for data parsing
- **Type Conversion**: String to integer and float conversion
- **Loops**: Nested iteration through complex data structures
- **Dictionaries**: Building structured data from lists

### Data Processing
- **Data Cleaning Pipeline**: Multi-step transformation process
- **Calculations**: Average computation with loops
- **Conditional Logic**: Grade assignment based on thresholds
- **Data Structures**: Organizing related data efficiently

### Pandas Integration
- **Dictionary to DataFrame**: Converting Python structures to pandas
- **DataFrame Creation**: Understanding pandas data organization
- **Column Management**: Working with named columns

## Data Transformation Journey

```
Raw Input:
"Alice:85,92,78,90,88"

Step 1 - Parse:
["Alice", "85,92,78,90,88"]

Step 2 - Split Scores:
["Alice", ["85", "92", "78", "90", "88"]]

Step 3 - Clean & Convert:
["Alice", [85, 92, 78, 90, 88]]

Step 4 - Add Calculations:
["Alice", [85, 92, 78, 90, 88], 86.6, "B"]

Step 5 - Structure:
{
  "student_name": ["Alice", ...],
  "test_scores": [[85, 92, ...], ...],
  "score_avg": [86.6, ...],
  "letter_grade": ["B", ...]
}

Final - DataFrame:
Structured pandas DataFrame ready for analysis
```

## Technical Details

- **Language**: Python 3.11
- **Libraries**: pandas
- **Environment**: Jupyter Notebook
- **Key Concepts**: Data transformation, nested structures, pandas basics

## Use Cases

This type of data processing is relevant for:
- Educational data systems
- Student information systems (SIS)
- Grade book automation
- Academic performance analysis
- Report card generation
- Learning management systems (LMS)

## Grading Scale

| Grade | Score Range |
|-------|-------------|
| A     | 90-100      |
| B     | 80-89       |
| C     | 70-79       |
| D     | 60-69       |
| F     | Below 60    |

## Future Enhancements

Potential improvements could include:
- Reading data from CSV files
- Handling missing test scores
- Weighted grade calculations
- Class statistics (class average, median)
- Grade distribution charts
- Identifying at-risk students
- Trend analysis over time

## Learning Outcomes

This project reinforced:
- Building data cleaning pipelines from scratch
- Working with nested data structures
- Importance of data type management
- Progressive data transformation
- Transitioning from Python basics to pandas
- Organizing code for readability

## Key Insights

**Why This Project Matters:**
- Demonstrates ability to handle messy real-world data
- Shows understanding of data transformation workflow
- Bridges Python fundamentals to data analysis libraries
- Illustrates practical application of control flow and data structures

---

[← Back to Portfolio](../README.md)
