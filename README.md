# MongoDB
#University Database MongoDB Code
This repository contains MongoDB code snippets for managing a university database. The code demonstrates various operations such as data insertion, data retrieval, and data aggregation within MongoDB. Below is a breakdown of each section of the code:

## 1. Data Insertion
The code begins by inserting data into several collections representing different aspects of a university database:

STUDENT: Contains student information including student numbers, names, classes, and majors.
COURSE: Stores information about courses, such as course names, course numbers, credit hours, and departments.
TERM: Contains data related to academic terms, including term identifiers, course numbers, semesters, years, and instructors.
GRADE_REPORT: Tracks student grades in specific terms.
PREQUISITE: Stores information about course prerequisites.
## 2. Aggregating Data - Query 1
In the first aggregation query, the code fetches information about students who took the "Information Storage & Management I" course during the fall semester. Here's the breakdown:

It uses the $lookup stage to join the TERM collection with the GRADE_REPORT collection based on the Term_identifier field.
The $unwind stage flattens the resulting array.
Another $lookup stage joins the STUDENT collection using the Student_number field.
A final $lookup stage links the COURSE collection based on the Course_number from the TERM collection.
The $match stage filters the results based on the course name ("Information Storage & Management I") and semester ("Fall").
The $project stage shapes the output by selecting relevant fields.
## 3. Aggregating Data - Query 2
The second aggregation query retrieves information about a specific student, "Tony Brown." Here's how it works:

It follows a similar structure to the first query, using $lookup stages to join the TERM, STUDENT, and COURSE collections.
The $match stage filters results based on the student's name ("Tony Brown").
The $project stage selects and renames fields for the output.
## 4. Aggregating Data - Query 3
This query aims to retrieve the names of students who took the "Information Storage & Management I" course in the fall of 2022 and their grades for that term. It uses the $match stage to filter based on specific course name, semester, and year conditions.

## 5. Aggregating Data - Query 4
The final query fetches the names of prerequisite courses for the "Information Storage & Management I" course. Here's how it works:

It utilizes multiple $lookup stages to link the COURSE collection with the PREQUISITE collection.
A $match stage filters for the course with the name "Information Storage & Management I."
The query unwinds the resulting array and performs another $lookup to obtain the names of prerequisite courses.
The output includes the names of prerequisite courses for "Information Storage & Management I."
These MongoDB code snippets demonstrate how to interact with a university database, showcasing common operations that can be performed to retrieve specific information from the given collections. You can adapt and use these queries as needed for your own MongoDB-based university database projects.
