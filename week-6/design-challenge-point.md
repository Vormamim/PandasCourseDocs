# Design Challenge Point

## Define Your Project – Ask a Question, Plan Your Analysis

Download the new data and create a new repository for for this project

{% file src="../.gitbook/assets/health_activity_data.csv" %}

### 🎯 Learning Objectives

You will:

* Identify a real-world question that can be answered with data
* Write a project purpose statement
* Define the functional and non-functional requirements of your project
* Plan your approach using a project notebook
* Create test cases for what your code must handle

***

### ⏱️ Estimated Time: 3 Hours

This week is about planning — not coding. Complete each of the five tasks below and commit your work.

***

### 🧠 Task 1: Explore Examples of Good Questions

Before you write your question, look at a few examples:

| ❌ Too vague                  | ✅ Better                                                                |
| ---------------------------- | ----------------------------------------------------------------------- |
| How many athletes are there? | How has the average age of female athletes changed since 1980?          |
| Who wins medals?             | Which 5 countries have the highest medal-per-athlete ratio in swimming? |
| What sport is best?          | What sport has the tallest average male athletes?                       |

In your journal, list:

* One question about **age**
* One about **gender**
* One about **medals**

***

Task 2: Define Your Project Question

Write your project’s guiding question or hypothesis. It must be:

* **Answerable** using the Olympic dataset
* Specific and measurable
* Ethical and relevant

Example:

> _"I want to investigate whether the average height of gymnasts has changed over time, and whether this differs by gender."_

***

**Task 3: Write Your Purpose & Audience**

In your project notebook, write:

* A **Project Title**
* A 3–5 sentence **Purpose Statement**
* The **intended audience** of your findings (e.g. sports scientists, Olympic fans, PE teachers)

***

**Task 4: List Your Functional and Non-Functional Requirements**

#### Functional Requirements:

* What will your program **do**?
* What filters, calculations, or visualisations will you use?

Example:

* Filter athletes by year and sport
* Group by gender and calculate average height
* Plot a line chart of change over time

#### Non-Functional Requirements:

* How will your project be:
  * Easy to use?
  * Well presented?
  * Respectful of data privacy?

***

**Task 5: Plan Test Cases**

Describe 2–3 test cases for your code:

* What inputs will be used?
* What output is expected?

Example:

> _If I filter gymnastics by year 2000, the code should return approx. 300 rows with valid heights and genders._

You can write this in a table like:

| Test Case | Input                           | Expected Output             |
| --------- | ------------------------------- | --------------------------- |
| TC1       | Sport = Gymnastics, Year = 2000 | \~300 rows                  |
| TC2       | Age < 16                        | Only athletes 15 or younger |
| TC3       | Medal = 'Gold'                  | All rows show Medal = Gold  |

***

### 🧭 Reflection

Answer in your journal or GitBook:

1. What inspired your project question?
2. Who might benefit from this kind of analysis?
3. What challenges do you expect to face next?

***

### 💬 REMINDER: GitHub Commit Checklist

After completing your plan:

* [ ] Save all writing in a file (Markdown, TXT, or notebook PDF)
* [ ] Open GitHub Desktop
* [ ] Commit with a message like: “Project plan and test cases added”
* [ ] Push to origin

***

### ✅ Week 6.1 Checklist

* [ ] Defined a clear, measurable project question
* [ ] Wrote a purpose and audience statement
* [ ] Listed functional and non-functional requirements
* [ ] Created at least 3 test cases
* [ ] Completed a reflection
* [ ] Committed and pushed work to GitHub

***

> 🚀 Next week: Begin your project implementation – writing the code and creating charts!
