# Database: University

## Table: departments

- id SMALLINT PK AI UNIQUE NOTNULL
- name VARCHAR(255) UNIQUE NOTNULL
- address VARCHAR(255) NULL
- phone VARCHAR(20) NULL UNIQUE
- mail VARCHAR(100) NULL UNIQUE

## Table: degrees

- id SMALLINT PK AI UNIQUE NOTNULL
- department_id SMALLINT FK NOTNULL
- name VARCHAR(255) UNIQUE NOTNULL
- type VARCHAR(70) NOTNULL
- duration VARCHAR(20) NULL
- degrees_url VARCHAR(255) NULL

## Table: courses

- id SMALLINT PK AI UNIQUE NOTNULL
- degree_id SMALLINT FK NOTNULL
- name VARCHAR(255) NOTNULL
- year VARCHAR(10) NULL
- semester VARCHAR(20) NULL
- cfu TINYINT NULL

## Table: teachers

- id SMALLINT PK AI UNIQUE NOTNULL
- name VARCHAR(30) NOTNULL
- surname VARCHAR(30) NOTNULL
- office_address VARCHAR(255) NULL
- phone VARCHAR(20) NULL 
- mail VARCHAR(100) NULL UNIQUE

## Table (pivot): course_teacher

- id SMALLINT PK AI UNIQUE NOTNULL
- course_id SMALLINT FK 
- teacher_id SMALLINT FK

## Table: exams

- id MEDIUMINT PK AI UNIQUE NOTNULL
- course_id SMALLINT FK NOTNULL
- date DATE NOTNULL
- time TIME NOTNULL
- location VARCHAR(255) NULL

## Table: students

- id MEDIUMINT PK AI UNIQUE NOTNULL
- degree_id SMALLINT FK NOTNULL
- name VARCHAR(30) NOTNULL
- surname VARCHAR(30) NOTNULL
- birth_date DATE NULL
- CF VARCHAR(20) NOTNULL UNIQUE
- phone VARCHAR(20) NULL UNIQUE
- mail VARCHAR(100) NULL UNIQUE
- registration_number VARCHAR(30) NOTNULL UNIQUE
- date_of_enrolment DATE NULL 

## Table (pivot): student_exam

- id MEDIUMINT PK AI UNIQUE NOTNULL
- student_id MEDIUMINT FK 
- exam_id MEDIUMINT FK
- vote TINYINT NOTNULL