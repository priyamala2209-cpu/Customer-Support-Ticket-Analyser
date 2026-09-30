# Python-Based Ticket Analysis System

> A Python project for cleaning, analyzing, and generating insights from customer support ticket data using core Python concepts.

This project shows how basic text preprocessing and keyword-based analysis can help support teams understand recurring issues, prioritize urgent tickets, and improve service quality.

### 🔗 Live Project: [Jupyter Notebook]

---

### 📌 Overview
The Python-Based Ticket Analysis System is a beginner-friendly yet business-oriented data analysis project built entirely in Python.

It takes raw customer support tickets and transforms them into clean, structured, and actionable insights. The project is designed to demonstrate real-world data cleaning and analytical thinking without using advanced libraries.

**Dataset includes:**
- Ticket Number
- Customer Name  
- Issue Description
- Priority (High / Medium / Low)

### 🎯 Problem Statement
Customer support teams deal with messy data - inconsistent text formatting, missing values, duplicate records, and incorrect priorities.

This project builds a system to:
1.  Store and organize raw ticket data
2.  Clean and standardize customer names and issue descriptions
3.  Validate and correct priority levels
4.  Analyze priority distribution
5.  Identify critical tickets and recurring keywords

### 🛠️ Tech Stack
- **Language:** Python
- **Environment:** Jupyter Notebook
- **Libraries:** Core Python (No external dependencies) + Pandas for display
- **Concepts Used:** Dictionaries of Lists, Loops, Functions, String Manipulation, Data Cleaning, Set Operations, Conditional Logic

  ---

# Objectives

The main objectives of this project are:

1. Store customer support ticket information.
2. Display ticket information in a readable format.
3. Allow users to add new tickets.
4. Automatically generate ticket numbers.
5. Validate ticket priorities.
6. Clean customer issue descriptions.
7. Count tickets containing specific keywords.
8. Analyse High, Medium, and Low priority tickets.
9. Find the ticket with the longest issue description.
10. Extract unique words from all ticket descriptions.

---

# Tools and Technologies Used

### Programming Language

**Python**

### Python Concepts Used

* Dictionary
* List
* Set
* String
* Variables
* `input()`
* `print()`
* `len()`
* `append()`
* `replace()`
* `lower()`
* `strip()`
* `capitalize()`
* `split()`
* `join()`
* `sorted()`
* `if`
* `elif`
* `else`
* `for` loop
* `while` loop
* Functions
* `return`
* `break`

---

# Project Workflow

The project follows these steps:

```text
Start
  ↓
Load Preloaded Tickets
  ↓
Display Initial Tickets
  ↓
Ask User to Add New Tickets
  ↓
Validate Priority
  ↓
Generate Ticket Number
  ↓
Add New Ticket
  ↓
Clean Issue Descriptions
  ↓
Keyword Analysis
  ↓
Priority Analysis
  ↓
Find Longest Issue
  ↓
Find Unique Words
  ↓
Display Final Results
  ↓
End
```

---

### 🔄 Workflow
Raw Data -> Data Cleaning & Standardization -> Priority Validation -> Keyword Analysis -> Priority Analysis -> Final Insights

### 🧹 Key Features Implemented

**1. Data Cleaning:**
- Stripped extra spaces, converted to lower case, handled empty descriptions
- Standardized Priority values to `High`, `Medium`, `Low`

  Step 1 — Preloaded Ticket Data

The project starts with a dictionary called `ticket_data`.

It contains four lists:

```python
ticket_data = {
    'Ticket_No': [...],
    'Customer_Name': [...],
    'Issue_Description': [...],
    'Priority': [...]
}
```

A dictionary is used because it allows related information to be stored using meaningful keys.

For example:

```python
ticket_data['Customer_Name']
```

accesses the customer names.

---

**2. Keyword-Based Insights (Case-insensitive):**
```python
def count_tickets_with_word(word):
    # Returns count of tickets containing a keyword
Example: good - 2 tickets, poor - 2 tickets, slow - 2 tickets
```
---

# Step 2 — Adding New Tickets

The program asks the user:

```text
How many new tickets do you want to add?
```

For each new ticket, the user enters:

* Customer Name
* Issue Description
* Priority

The `input()` function is used to collect information from the user.

A `for` loop is used to repeat the process according to the number of tickets entered.

---

Priority Validation

The program accepts only three priority values:

* High
* Medium
* Low

A `while` loop is used to keep asking the user until a valid priority is entered.

The following methods are used:

### `strip()`

Removes unwanted spaces from the beginning and end of the input.

Example:

```text
" High "
```

becomes:

```text
"High"
```

### `capitalize()`

Converts the first letter to uppercase.

Example:

```text
"high"
```

becomes:

```text
"High"
```

This makes the input more consistent.

---

# Automatic Ticket Number

The program automatically creates the next ticket number using:

```python
len(ticket_data['Ticket_No']) + 1
```

If there are currently 10 tickets:

```text
10 + 1 = 11
```

Therefore, the next ticket receives ticket number **11**.

This avoids manually entering ticket numbers.

---

# Adding Data Using `append()`

The `append()` method is used to add new information to the end of a list.

Example:

```python
ticket_data['Customer_Name'].append(customer_name)
```

This adds the new customer's name to the customer list.

The same method is used for:

* Ticket number
* Customer name
* Issue description
* Priority

---

# Step 3 — Text Cleaning

Customer descriptions may contain:

* Capital letters
* Extra spaces
* Punctuation
* Shorthand words

A function called `clean_text()` is created to clean the descriptions.

### Cleaning Operations

#### Convert to lowercase

```python
text.lower()
```

Example:

```text
"GREAT SUPPORT"
```

becomes:

```text
"great support"
```

---

#### Remove punctuation

The `replace()` method removes:

```text
.
,
!
?
```

Hyphens are replaced with spaces.

---

#### Replace shorthand

```python
text.replace("ok", "okay")
```

changes:

```text
ok
```

to:

```text
okay
```

---

#### Split the text

```python
text.split()
```

breaks a sentence into individual words.

Example:

```text
"good support service"
```

becomes:

```python
["good", "support", "service"]
```

---

#### Join the words

```python
" ".join(words)
```

joins the words together using one space.

This helps remove multiple spaces.

---

#### Remove outside spaces

```python
text.strip()
```

removes spaces from the beginning and end of the text.

---

#  Step 4 — Keyword Analysis

A function called:

```python
count_tickets_with_word(word)
```

is created.

Its purpose is to count how many ticket descriptions contain a particular word.

The project checks these keywords:

* `poor`
* `good`
* `slow`
* `excellent`

The description is split into individual words, and the program checks whether the searched word exists.

For example:

```python
count_tickets_with_word("poor")
```

returns
---

# 📈 Key Analysis Questions

The project answers the following questions:

### 1. How many High-priority tickets are present?

This helps identify the number of urgent customer issues.

### 2. How many Medium-priority tickets are present?

This identifies the number of moderately urgent issues.

### 3. How many Low-priority tickets are present?

This shows the number of less urgent support requests.

### 4. Which ticket has the highest priority?

The system identifies the ticket that should receive the earliest attention.

### 5. Which customer has a High-priority issue?

This helps support teams identify customers who require immediate assistance.

### 6. What is the overall priority distribution?

The project compares High, Medium, and Low tickets to understand the workload and urgency level.

---

# 💡 Key Insights

The analysis provides the following types of insights:

* High-priority tickets should be handled first because they represent urgent customer issues.
* Medium-priority tickets require timely attention but may be handled after critical requests.
* Low-priority tickets can generally be scheduled after higher-priority requests.
* Cleaning the ticket data improves the reliability of the analysis.
* Standardizing text values makes customer and issue information more consistent.
* Priority analysis helps support teams allocate their time and resources effectively.

---

# 🧠 Python Concepts Demonstrated

This project demonstrates practical use of the following Python concepts.

## Lists

Lists are used to store multiple ticket values.

```python
ticket_numbers = [1, 2, 3, 4]
```

## Dictionaries

Dictionaries are used to organize different ticket attributes.

```python
ticket_data = {
    "Ticket Number": ticket_numbers,
    "Customer Name": customer_names,
    "Priority": priorities
}
```

## For Loop

Loops can be used to process each ticket.

```python
for ticket in ticket_numbers:
    print(ticket)
```


## Functions

Functions can be created to perform reusable operations such as data cleaning and priority analysis.

```python
def count_priority(priorities, priority):
    return priorities.count(priority)
```

---

# 📁 Project Structure

A recommended GitHub repository structure is:

```text
Python-based-Ticket-Analysis-System/
│
├── Python-based Ticket Analysis System.ipynb
│
├── README.md
│
└── screenshots/
    ├── cleaned_data.png
    ├── priority_analysis.png
    └── final_output.png
```

The Jupyter Notebook contains the complete Python implementation, while the README provides an explanation of the project.

---

# ▶️ How to Run the Project

## Step 1: Install Python

Install Python on your computer.

## Step 2: Install Jupyter Notebook

```bash
pip install notebook
```

## Step 3: Start Jupyter Notebook

```bash
jupyter notebook
```

## Step 4: Open the Project

Open:

```text
Python-based Ticket Analysis System.ipynb
```

## Step 5: Run the Cells

Run each notebook cell from top to bottom to:

1. Create the ticket data
2. Clean the data
3. Analyze priorities
4. Identify important tickets
5. Display the final results

---

# 📌 Project Outcome

The project successfully demonstrates how Python can be used to build a simple ticket analysis system.

By using basic Python programming concepts, the system can transform raw ticket information into structured and useful analysis.

The project demonstrates practical skills in:

* Data cleaning
* Data validation
* Data organization
* Data analysis
* Logical problem solving
* Python programming
* Business-oriented interpretation of data

---

# 🚀 Future Improvements

The project can be further enhanced by adding:

* Ticket status such as Open, In Progress, and Closed
* Ticket creation and resolution dates
* Resolution-time analysis
* Customer satisfaction scores
* Ticket category analysis
* Charts and visualizations using Matplotlib
* Pandas DataFrame analysis
* Exporting cleaned data to CSV
* Interactive dashboards using Power BI
* Automated ticket priority classification

---

# 📚 Learning Outcomes

Through this project, I learned how to:

* Work with structured data in Python
* Use lists and dictionaries
* Apply loops and conditional statements
* Create and use functions
* Clean inconsistent data
* Handle duplicate records
* Validate data values
* Analyze priority categories
* Extract useful information from raw data
* Present analytical results clearly

---

# 👩‍💻 Author

**Priyadharshini Naresh D**

Aspiring AI-Driven Data Analyst

### Skills

* Python
* Microsoft Excel
* Power BI
* MySQL
* Data Analysis
* Data Visualization

---

# ⭐ Conclusion

The **Python-based Ticket Analysis System** is a practical beginner-level data analytics project that demonstrates the complete process of working with customer support ticket data.

From **raw ticket data → data cleaning → analysis → insights**, the project shows how Python programming can be applied to solve a real-world business problem.

This project also provides a foundation for developing more advanced analytics solutions using **Pandas, visualization libraries, SQL, Power BI, and machine learning**.

---

## 🔖 Keywords

`Python` `Data Analytics` `Ticket Analysis` `Customer Support` `Data Cleaning` `Data Analysis` `Python Project` `Jupyter Notebook` `Priority Analysis` `Business Analytics` `Aspiring Data Analyst`
