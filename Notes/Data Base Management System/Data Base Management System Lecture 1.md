---
Title: Data Base Management System Lecture 1
Status: 
marker: 
tags: 
Date: 22-07-2024
Time: 13:17
---
# Database Management System Lecture 1

## Introduction
This lecture covers the basics of representing data in a tabular format and the initial steps in designing a database, including understanding user requirements, creating visual formats, and developing schemas using entity-relationship models. The focus is on organizing data efficiently and understanding the fundamental concepts of database design.

## Contents

### [1. Introduction to Tabular Representation of Data](#1-introduction-to-tabular-representation-of-data)
#### [1.1 Overview](#11-overview)
- [Tabular Representation of Data](#tabular-representation-of-data)
- [Problem Statement Analysis](#problem-statement-analysis)
- [Visual Format](#visual-format)
- [Schema Preparation](#schema-preparation)
- [Entity-Relationship Model](#entity-relationship-model)
- [Data Cleaning](#data-cleaning)

#### [1.2 Steps to Convert Abstract Ideas into a Schema](#12-steps-to-convert-abstract-ideas-into-a-schema)
1. [Understand User Requirements](#understand-user-requirements)
2. [Visual Representation](#visual-representation)
3. [Schema Preparation](#schema-preparation)
4. [Entity-Relationship Model](#entity-relationship-model)
5. [Data Cleaning](#data-cleaning)

#### [1.3 Key Concepts](#13-key-concepts)
- [Tabular Representation](#tabular-representation)
- [User Requirements](#user-requirements)
- [Visual Format](#visual-format)
- [Schema](#schema)
- [Entity-Relationship Model (ERM)](#entity-relationship-model-erm)
- [Data Cleaning](#data-cleaning)

### [2. Entity Sets](#2-entity-sets)
#### [2.1 Definitions](#21-definitions)
- [Entity](#entity)
- [Entity Set](#entity-set)
- [Primary Key](#primary-key)
- [Candidate Key](#candidate-key)

#### [2.2 Representation of Entity Sets in Graphs](#22-representation-of-entity-sets-in-graphs)
**Example:**
- [Instructor Table](#instructor-table)
- [Student Table](#student-table)

### [3. Relationship Sets](#3-relationship-sets)
- [Relationship](#relationship)

### [4. Roles](#4-roles)
- [Course Prerequisite](#course-prerequisite)

### [5. Why Use Entities Instead of Attributes](#5-why-use-entities-instead-of-attributes)

### [6. Attribute Types](#6-attribute-types)
- [Simple and Composite Attributes](#simple-and-composite-attributes)
- [Single Valued and Multivalued Attributes](#single-valued-and-multivalued-attributes)
- [Derived Attributes](#derived-attributes)
- [Domain](#domain)

#### [6.1 Representing Complex Attributes in ER Diagram](#61-representing-complex-attributes-in-er-diagram)
**Example:**
- [Instructor Table with Complex Attributes](#instructor-table-with-complex-attributes)

### [7. Mapping Cardinalities](#7-mapping-cardinalities)

### [8. Total and Partial Participation](#8-total-and-partial-participation)
#### [8.1 Total Participation](#81-total-participation)

### [9. Expressing Weak Entity Sets](#9-expressing-weak-entity-sets)

### [10. Redundant Attributes](#10-redundant-attributes)

### [11. Partial Participation](#11-partial-participation)


## 1. Introduction to Tabular Representation of Data

### 1.1 Overview
#### Tabular Representation of Data
Organizing information in a table format for clear presentation.

#### Problem Statement Analysis
Understanding user
## Introduction
This lecture covers the basics of representing data in a tabular format and the initial steps in designing a database, including understanding user requirements, creating visual formats, and developing schemas using entity-relationship models. The focus is on organizing data efficiently and understanding the fundamental concepts of database design.

## Contents

### 1. Introduction to Tabular Representation of Data
#### 1.1 Overview
- **Tabular Representation of Data**: Organizing information in a table format for clear presentation.
- **Problem Statement Analysis**: Understanding user requirements to address specific needs.
- **Visual Format**: Transforming abstract ideas into visual representations.
- **Schema Preparation**: Designing the structure for organizing data.
- **Entity-Relationship Model**: Developing a model to define relationships between data entities.
- **Data Cleaning**: Refining data to ensure accuracy and consistency.

#### 1.2 Steps to Convert Abstract Ideas into a Schema
1. **Understand User Requirements**: Analyze the problem statement to comprehend the user's needs and expectations.
2. **Visual Representation**: Create visual formats such as diagrams or flowcharts to illustrate abstract ideas.
3. **Schema Preparation**: Develop a structured schema that organizes data efficiently.
4. **Entity-Relationship Model**: Establish entities and relationships to define how data elements interact.
5. **Data Cleaning**: Clean the data to remove inconsistencies and finalize the schema.

#### 1.3 Key Concepts
- **Tabular Representation**: Using tables to present data clearly and concisely.
- **User Requirements**: Detailed understanding of what the user needs.
- **Visual Format**: Diagrams, flowcharts, and other visual tools to represent ideas.
- **Schema**: The structured framework for organizing data.
- **Entity-Relationship Model (ERM)**: A diagram that shows the relationships between entities in a database.
- **Data Cleaning**: The process of correcting or removing inaccurate records from a dataset.

### 2. Entity Sets
#### 2.1 Definitions
- **Entity**: An object that exists and is distinguishable from other objects.
- **Entity Set**: A collection of entities of the same type sharing the same properties.
- **Primary Key**: A subset of attributes that uniquely identify an entity in an entity set.
- **Candidate Key**: A set of attributes that can uniquely identify a row in a database table.

#### 2.2 Representation of Entity Sets in Graphs
- Attributes are listed inside an entity rectangle.
- The primary key attributes are underlined.

**Example:**

| Instructor |
| ---------- |
| ID         |
| Name       |
| Salary     |

| Student       |
| ------------- |
| ID            |
| Name          |
| Total Credits |

### 3. Relationship Sets
- **Relationship**: An association among several entities.

**Example:** 
- `44553 (Peltier)` Advisor `2222 (Einstein)`
- Student entity - Relationship - Instructor Entity

### 4. Roles
- **Course Prerequisite**: One course is a prerequisite for another.

### 5. Why Use Entities Instead of Attributes
- When there are many values shared by multiple entities, it is easier to use an entity instead of an attribute.

### 6. Attribute Types
- **Simple and Composite Attributes**
- **Single Valued and Multivalued Attributes**
  - Example of multivalued attribute: `Phone_Number`
- **Derived Attributes**
  - Can be computed from other attributes
  - Examples: 
    - Age, given date of birth
    - Course Credits
- **Domain**: The set of permitted values for each attribute.

#### 6.1 Representing Complex Attributes in ER Diagram

| Instructor         |
| ------------------ |
| ID                 |
| Name               |
| - First Name       |
| - Middle Name      |
| - Last Name        |
| Address            |
| - Street           |
| - Locality         |
| etc.               |

### 7. Mapping Cardinalities
- Refer to diagrams in Teams notes.

### 8. Total and Partial Participation
#### 8.1 Total Participation
- Every row of the entity should participate in a relation.
- Example: A student must be related to the college with a course_relation.

### 9. Expressing Weak Entity Sets
### 10. Redundant Attributes
### 11. Partial Participation

## References

### Enhancements Needed
- Add proper indexing.
- Include charts and visual aids.
- Enhance notes with additional relevant information.
- Organize topics logically for better understanding.