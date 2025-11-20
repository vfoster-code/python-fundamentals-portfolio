# Movie Dataset Analysis

A Python project demonstrating advanced list manipulation, custom sorting algorithms, and statistical analysis using only core Python (no pandas).

## Project Overview

This project analyzes a movie dataset using fundamental Python to perform filtering, calculations, and custom sorting. It showcases the ability to build analytical functions from scratch without relying on libraries, demonstrating deep understanding of algorithms and data structures.

## Problem Statement

Analyze movie data that contains:
- Inconsistent name formatting (mixed case)
- String-formatted numerical data
- Multiple data points per movie

Perform analysis including:
- Data cleaning and standardization
- Decade-based filtering
- Statistical calculations
- Custom sorting implementation
- Comprehensive reporting

## Features

### 1. Data Cleaning
- Parse comma-separated movie data
- Standardize titles to title case
- Convert years to integers
- Convert ratings to floats

### 2. Filtering & Analysis
- Count movies by decade (1990s)
- Calculate average ratings across dataset
- Filter highly-rated movies (≥9.0)

### 3. Custom Sorting Algorithm
- Implemented sorting without built-in `.sort()` initially
- Created custom logic using temporary lists
- Ordered movies by rating

### 4. Report Generation
- Professional formatted output
- Clear statistics and breakdowns
- Organized movie listings

## Code Highlights

### Data Cleaning Pipeline
```python
for movie in movies:
    movie[0] = movie[0].title()      # Standardize titles
    movie[1] = int(movie[1])         # Convert year to integer
    movie[2] = float(movie[2])       # Convert rating to float
```

### Decade Filtering
```python
for movie in movies:
    if movie[1] >= 1990 and movie[1] <= 1999:
        count_movies_1990s += 1
        list_movies_1990s.append(movie)
```

### Custom Sorting Algorithm
```python
# Extract unique ratings
temp_ordered_ratings_list = []
for movie in highly_rated_movies:
    temp_ordered_ratings_list.append(movie[2])

# Remove duplicates and sort
temp_ordered_ratings_list = list(set(temp_ordered_ratings_list))
temp_ordered_ratings_list.sort()

# Rebuild movie list in rating order
temp_ordered_movies = []
for rating in temp_ordered_ratings_list:
    for movie in highly_rated_movies:
        if rating == movie[2]:
            temp_ordered_movies.append(movie)
```

### Statistical Calculations
```python
movie_count = 0
movie_ratings_sum = 0

for movie in movies:
    movie_count += 1
    movie_ratings_sum += movie[2]

movie_rating_avg = movie_ratings_sum / movie_count
```

## Sample Output

```
=== Movie Report ===

Total Movies: 5 movies
Average rating for all movies: 9.0

Movies from the 1990s: 3 movies
The Shawshank Redemption 1994
Pulp Fiction 1994
Forrest Gump 1994

Highly Rated Movies (9.0 or higher): 3 movies
The Dark Knight 9.0
The Godfather 9.2
The Shawshank Redemption 9.3
```

## Skills Demonstrated

### Core Python
- **List Manipulation**: Multi-dimensional lists, nested structures
- **String Processing**: Parsing, splitting, formatting
- **Type Conversion**: String to int/float conversions
- **Loops**: Nested iteration, accumulation patterns
- **Conditionals**: Multiple filtering criteria

### Algorithms
- **Sorting**: Custom sorting algorithm implementation
- **Filtering**: Multi-criteria data filtering
- **Aggregation**: Sum and average calculations
- **Deduplication**: Using sets for unique values

### Data Analysis
- **Statistical Measures**: Averages, counts
- **Data Segmentation**: Filtering by criteria
- **Ranking**: Ordering by specific attributes
- **Reporting**: Clear data presentation

## Algorithm Complexity

### Custom Sorting Algorithm
```
Time Complexity: O(n²)
Space Complexity: O(n)

Where n = number of movies to sort
```

**Process:**
1. Extract ratings: O(n)
2. Remove duplicates: O(n)
3. Sort ratings: O(k log k) where k = unique ratings
4. Rebuild movie list: O(n × k)

**Note:** While less efficient than built-in sorting, this demonstrates understanding of sorting logic from first principles.

## Data Structure

```python
movies = [
    [title: str, year: int, rating: float],
    [title: str, year: int, rating: float],
    ...
]
```

## Analysis Results

### Dataset Statistics
- **Total Movies**: 5
- **Average Rating**: 9.0/10
- **1990s Movies**: 3 (60%)
- **Highly Rated (≥9.0)**: 3 (60%)

### Rating Distribution
- 9.0-9.2: 2 movies
- 9.2-9.4: 1 movie
- 8.8-9.0: 2 movies

## Technical Details

- **Language**: Python 3.11
- **Libraries**: None (pure Python)
- **Environment**: Jupyter Notebook
- **Key Concepts**: Algorithms, data structures, statistical analysis

## Use Cases

This type of analysis is relevant for:
- Movie recommendation systems
- Content curation platforms
- Entertainment analytics
- Rating aggregation services
- Historical trend analysis
- Dataset quality assessment

## Comparison: Custom vs. Built-in Sorting

### Custom Implementation (This Project)
```python
# Manual sorting logic
temp_ordered_ratings_list = list(set([m[2] for m in movies]))
temp_ordered_ratings_list.sort()
# ... rebuild list
```

**Pros:**
- Demonstrates algorithm understanding
- Shows problem-solving approach
- Educational value

**Cons:**
- More code
- Less efficient
- More complex

### Built-in Sorting (Production Code)
```python
highly_rated_movies.sort(key=lambda x: x[2])
```

**Pros:**
- Concise
- Optimized
- Standard practice

## Future Enhancements

Potential improvements could include:
- Genre analysis
- Multi-field sorting (year, then rating)
- Median and standard deviation calculations
- Decade trend analysis
- Director/actor cross-referencing
- Data visualization
- CSV import/export

## Learning Outcomes

This project reinforced:
- Building analytical functions from scratch
- Understanding sorting algorithms
- Working with multi-dimensional data
- Statistical calculation implementation
- Report formatting best practices
- Balancing custom code vs. libraries

## Key Insights

**Why This Project Matters:**
1. **Foundation**: Shows understanding of how libraries work "under the hood"
2. **Problem-Solving**: Demonstrates algorithmic thinking
3. **Flexibility**: Can analyze data without dependencies
4. **Progression**: Sets foundation for more advanced analysis with pandas

**When to Use This Approach:**
- Learning fundamentals
- Understanding algorithms
- Simple datasets
- No library dependencies allowed

**When to Use Libraries:**
- Production code
- Large datasets
- Complex operations
- Team collaboration

---

[← Back to Portfolio](../README.md)
