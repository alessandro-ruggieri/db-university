# Database: University

## Table: departments

- id
- name
- address
- phone
- mail

## Table: degrees

- id
- department_id FK
- name 
- type
- duration
- degrees_url

## Table: courses

- id
- degree_id FK
- name
- year
- semester
- cfu 

## Table: teachers

- id 
- name
- surname 
- office_address
- phone
- mail 

## Table (pivot): course_teacher

- id 
- course_id FK
- teacher_id FK

## Table: exams

- id 
- course_id FK
- date
- time 
- location

## Table: students

- id 
- degree_id 
- name 
- surname 
- birth_date
- CF
- phone
- mail
- registration_number 
- date_of_enrolment

## Table (pivot): student_exam

- id 
- student_id
- exam_id
- vote