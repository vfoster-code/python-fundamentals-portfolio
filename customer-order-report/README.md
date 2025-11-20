# Customer Order Report

A Python project demonstrating data cleaning, conditional logic, and automated report generation for customer order processing.

## Project Overview

This project takes messy customer order data and transforms it into a clean, formatted report. It showcases fundamental Python skills including string manipulation, data validation, calculations, and conditional formatting.

## Problem Statement

Process raw customer order data that contains:
- Inconsistent formatting (extra whitespace, mixed case)
- Data entry errors (typos in phone numbers)
- Variable discount rules based on membership status

Generate a professional, formatted order report with accurate calculations.

## Features

### Data Cleaning
- Remove leading/trailing whitespace from customer names
- Standardize names to title case
- Convert emails to lowercase for consistency
- Correct typos in phone numbers

### Business Logic
- Calculate average price per item
- Apply 15% discount for loyalty members
- Calculate final totals after discount
- Handle both member and non-member scenarios

### Report Generation
- Professional formatted output
- Clear section headers
- Proper currency formatting
- Dynamic content based on membership status

## Code Highlights

### String Manipulation
```python
customer_name = customer_name.strip().title()
email = email.lower()
phone = phone.replace('oli', '011')
```

### Conditional Logic
```python
if loyalty_member == True:
    # Apply 15% discount
    print(f'Member = 15% Discount')
else:
    # No discount
    print(f'Non Member = No Discount')
```

### Function with Formatting
```python
def customer_order_report():
    print(f'''====== Customer Order Report =====
    
{customer_name}
{phone}
{email}
...
''')
```

## Sample Output

```
====== Customer Order Report =====

Sarah Johnson
555-011-1234
sarah.johnson@email.com
Age = 28

Member = 15% Discount    
Items Ordered: 7
Order Subtotal: $156.79
Discount: $23.52
Total: $133.27
```

## Skills Demonstrated

- **String Methods**: `.strip()`, `.title()`, `.lower()`, `.replace()`
- **F-Strings**: Multi-line formatted strings with variable interpolation
- **Arithmetic**: Basic calculations and percentage operations
- **Functions**: Creating reusable report generation functions
- **Conditionals**: If/else logic for business rules
- **Boolean Logic**: Membership status handling

## Data Flow

1. **Input**: Raw customer data with formatting issues
2. **Cleaning**: Apply string methods to standardize data
3. **Calculation**: Compute averages, discounts, and totals
4. **Logic**: Determine membership status and apply rules
5. **Output**: Generate formatted report

## Technical Details

- **Language**: Python 3.11
- **Environment**: Jupyter Notebook
- **Key Concepts**: Data cleaning, conditional logic, string formatting

## Use Cases

This type of data processing is relevant for:
- E-commerce order processing
- Customer relationship management (CRM) systems
- Invoice generation
- Data validation pipelines
- Report automation

## Future Enhancements

Potential improvements could include:
- Reading data from CSV files
- Processing multiple customers in batch
- Variable discount tiers
- Tax calculations
- Database integration
- Email report delivery

## Learning Outcomes

This project reinforced:
- Importance of data cleaning before analysis
- Using functions for reusable code
- Professional output formatting
- Business logic implementation in code
- Testing different scenarios (member vs. non-member)

---

[← Back to Portfolio](../README.md)
