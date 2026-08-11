# Real Estate Schmitt AG — Data Engineering & Data Warehouse

## Overview

**Real Estate Schmitt AG** is an end-to-end data engineering project developed for the real estate division of the Schmitt AG conglomerate.

The project addresses the design of an integrated data platform for a growing real estate business, covering the complete data lifecycle from **conceptual data modeling and relational database design to data warehousing, legacy-data migration, and data quality management**.

The main objective is to establish a reliable and scalable data foundation that supports both operational processes and future **Business Intelligence (BI)** requirements.

---

## Project Objectives

The project covers five major areas:

1. **Conceptual Data Modeling**

   * Development of a complete Entity-Relationship Model based on the **Chen notation (P. Chen, 1976)**.
   * Documentation of entities, attributes, relationships, and cardinalities.

2. **Relational Database Design**

   * Transformation of the conceptual ER model into a normalized relational database.
   * Definition of tables, primary keys, foreign keys, and relationships.
   * Documentation of the resulting database structure.

3. **Data Warehouse & Business Intelligence**

   * Design of a data warehouse architecture for analytical workloads.
   * Development of an appropriate dimensional data model.
   * Separation of operational and analytical workloads.

4. **Data Migration & Data Quality**

   * Development of a concept for integrating existing legacy data into the new IT environment.
   * Identification and handling of inconsistent, incomplete, and duplicate data.
   * Definition of data quality processes targeting a quality level of **>97%**.

5. **Project Presentation**

   * Documentation and presentation of the proposed solution and project results.

---

# 1. Entity-Relationship Model

The first step was to model the business domain using the **Entity-Relationship Model according to Chen notation**.

The model captures the core entities and business relationships of the real estate brokerage process.

The conceptual model serves as the foundation for the subsequent database implementation.

### Key modeling aspects

* Real estate properties
* Property owners
* Customers / buyers
* Brokers / employees
* Property offers
* Contracts
* Locations
* Transactions
* Business relationships and cardinalities

The model was documented before being transformed into the physical database schema.

---

# 2. Relational Database

The conceptual ER model was transformed into a relational database.

The database design focuses on:

* Referential integrity
* Primary and foreign keys
* Normalization
* Consistent data types
* Elimination of redundant data
* Maintainable relationships between business entities

The resulting database provides the operational data foundation for the Real Estate department.

### Database Design

The transformation follows the principle:

```text
Business Requirements
        ↓
Entity-Relationship Model
        ↓
Relational Schema
        ↓
Database Tables
        ↓
Primary / Foreign Keys
        ↓
Operational Data
```

---

# 3. Data Warehouse & Business Intelligence

To support analytical workloads and Business Intelligence requirements, a dedicated **data warehouse layer** was designed.

Operational systems and analytical systems have different requirements. Therefore, analytical workloads should not directly depend on the transactional database.

The proposed architecture separates operational data processing from reporting and analytics.

### Conceptual Architecture

```text
Operational Systems
        │
        ▼
   Data Integration
        │
        ▼
   Staging Layer
        │
        ▼
   Data Warehouse
        │
        ▼
 Dimensional Data Model
        │
        ▼
 BI / Reporting / Analytics
```

### Dimensional Modeling

The analytical model follows a dimensional approach with:

* **Fact tables** for measurable business events
* **Dimension tables** for descriptive business context

Potential dimensions include:

* Property
* Customer
* Employee / Broker
* Location
* Date
* Property Type

This structure enables analytical questions such as:

* How many properties were sold over time?
* Which regions generate the highest revenue?
* Which brokers perform best?
* Which property types are most frequently sold?
* How does sales performance develop over time?

---

# 4. Data Integration, Migration & Data Quality

A major challenge of the project is the migration of existing legacy data into the new IT environment.

Legacy systems may contain:

* Duplicate records
* Missing values
* Inconsistent formats
* Invalid addresses
* Different naming conventions
* Inconsistent identifiers
* Outdated records

Therefore, data migration is treated as a structured **ETL / data-quality process** rather than a simple data import.

### Proposed Migration Process

```text
Legacy Data
     │
     ▼
Data Extraction
     │
     ▼
Staging
     │
     ▼
Data Profiling
     │
     ▼
Cleaning & Standardization
     │
     ▼
Validation
     │
     ▼
Duplicate Detection
     │
     ▼
Data Quality Checks
     │
     ▼
Transformation
     │
     ▼
Target Database / DWH
```

### Data Quality Strategy

The target is to achieve and continuously maintain a data quality level of **more than 97%**.

The quality framework considers dimensions such as:

| Dimension    | Example                                      |
| ------------ | -------------------------------------------- |
| Completeness | Required fields are populated                |
| Accuracy     | Values represent valid business information  |
| Consistency  | Values follow common formats and rules       |
| Uniqueness   | Duplicate records are identified and removed |
| Validity     | Values comply with defined constraints       |
| Timeliness   | Data is sufficiently up to date              |

Data-quality checks should be performed continuously rather than only during the initial migration.

---

# 5. Technology & Concepts

The project focuses primarily on **data engineering and data architecture concepts**, including:

* Entity-Relationship Modeling
* Relational Database Design
* Database Normalization
* SQL
* Data Warehousing
* Dimensional Modeling
* ETL / ELT
* Data Migration
* Data Profiling
* Data Quality Management
* Business Intelligence

---

# 6. Project Deliverables

The project consists of the following main deliverables:

### Entity-Relationship Model

A complete conceptual data model based on Chen notation.

### Relational Database

A database implementation derived from the conceptual model, including documentation of the schema and relationships.

### Data Warehouse Model

A dimensional data model designed to support Business Intelligence and analytical workloads.

### Data Migration & Data Quality Concept

A structured approach for integrating legacy data and achieving a target data quality level of **>97%**.

### Project Presentation

The complete project results are documented in the accompanying presentation:

**`Präsentation_Gruppe2_.pptx`**

---

# 7. Architecture Overview

The overall solution can be summarized as:

```text
                  ┌─────────────────────┐
                  │   Legacy Systems    │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │ Data Integration &  │
                  │     Staging         │
                  └──────────┬──────────┘
                             │
                  ┌──────────▼──────────┐
                  │  Data Quality &     │
                  │  Transformation     │
                  └──────────┬──────────┘
                             │
                ┌────────────▼────────────┐
                │   Operational Database │
                └────────────┬────────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │    Data Warehouse   │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │ BI / Reporting /    │
                  │      Analytics      │
                  └─────────────────────┘
```

---

# 8. Key Learning Outcomes

This project demonstrates practical understanding of the complete data engineering lifecycle:

**Business Requirements → Data Modeling → Database Design → Data Integration → Data Quality → Data Warehouse → Business Intelligence**

It also demonstrates how operational data systems can be designed to provide a reliable foundation for downstream analytics and decision-making.

---

# 9. Presentation

The project results are summarized in the following presentation:

📊 **Präsentation_Gruppe2_.pptx**

---

## Author

**Dat Tran**

Data Scientist | Machine Learning Engineer | Data Engineering

GitHub: `https://github.com/tatdattran`
