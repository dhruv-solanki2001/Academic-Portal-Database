# Academic Portal Database

## CS301 Databases Course Project (Phase A)

A basic academic portal for an academic university using only database system functionalities such as stored procedures & triggers.

| Name            | Entry No.   |
| --------------- | ----------- |
| Ashish Sharma   | 2019MCB1213 |
| Solanki Dhruv   | 2019CSB1122 |
| Sudhanshu Kumar | 2019CSB1123 |

### Relations & Schemas used in the project

- Departments (contains all departments of the academic institute)
> `departments` (dept_id, dept_name)

  For example :- 
  ```sql
    CREATE TABLE IF NOT EXISTS departments
    (
    dept_id VARCHAR(5) PRIMARY KEY,
    dept_name TEXT NOT NULL
    );
    INSERT INTO departments(dept_id,dept_name)
    VALUES('cs','Computer Science');

    INSERT INTO departments(dept_id,dept_name)
    VALUES('ee','Electrical Engineering');

    INSERT INTO departments(dept_id,dept_name)
    VALUES('ma','Mathematics');
  ```    

| *dept_id* | *dept_name*                      |
| --------- | -------------------------------- |
| cs        | Computer Science                 |
| ee        | Electrical Engineering           |
| ma        | Mathematics                      |

- Faculty (contains all faculty members in the institute)
> `faculty` (fac_id, fac_name, dept_id)

- Students (contains all students in the institute)
> `students` (student_id, student_name, dept_id, join_year)

- Batch Advisor
> `batch_advisor` (fac_id, dept_id, batch_yr)

- Course Catalogue
> `course_catalogue` (course_id, title, dept_id, lec_hr, tut_hr, prac_hr, ss_hr, credits)

- Prerequisite
> `prerequisite` (course_id, prereq_id, batches, dept_allowed, cgpa)

- Course Offering
> `course_offering` (course_id, sem, year)

- Teaches
> `teaches` (course_id, sem, year, fac_id, section_id)

- Slots
> `slots` (slot_id, num_sect, start_time, end_time, slot_type, days)

- Section Slot Information
> `section_slot_info` (course_id, slot_id, num_sect, sect_occupied)

- Tickets
> `tickets` (ticket_id, sem, year, course_id, student_id, cause)

- UG Curriculum
> Separate relations for various batches
