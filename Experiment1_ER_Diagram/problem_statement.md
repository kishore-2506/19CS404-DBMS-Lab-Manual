# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Kishore M

## Scenario Chosen:
University

## ER Diagram:
![Screenshot 2025-05-06 131114](https://github.com/user-attachments/assets/6285d4fb-46dd-4290-a0cc-3c74a22e7330)


## Entities and Attributes:
Entities and Attributes:

1. Student
   - StudentID (PK)
   - FullName
   - DOB
   - Gender
   - Email
   - Phone
   - Address
   - AdmissionDate

2. Instructor
   - InstructorID (PK)
   - FullName
   - Email
   - Phone
   - Specialization
   - HireDate

3. Department
   - DepartmentID (PK)
   - DepartmentName
   - DepartmentHead

4. Program
   - ProgramID (PK)
   - ProgramName
   - Duration
   - DegreeType (e.g., B.Sc, M.Tech)
   - DepartmentID (FK)

5. Course
   - CourseID (PK)
   - CourseName
   - Credits
   - SemesterOffered
   - ProgramID (FK)
   - InstructorID (FK)

6. Enrollment
   - EnrollmentID (PK)
   - StudentID (FK)
   - CourseID (FK)
   - EnrollmentDate
   - Grade
## Relationships and Constraints:
- Department — Program: 1 to Many
  Each department offers multiple programs.

- Program — Course: 1 to Many
  A program includes several courses.

- Instructor — Course: 1 to Many
  An instructor may teach multiple courses, but each course is taught by one instructor.

- Student — Course: Many to Many (resolved via Enrollment)
  A student can enroll in many courses, and each course can have many students.

- Course — Prerequisite (self-relationship): 1 to Many
  A course may require other courses as prerequisites.


## Extension (Prerequisite / Billing):
Entity: Prerequisite
- Tracks which courses are required before enrolling in a course.
- Implements curriculum flow.
- Example: "Data Structures" requires "Programming Fundamentals".

## Design Choices:
- Student, Instructor, Program, Department, Course: essential academic entities.
- Enrollment: tracks many-to-many relationship and academic performance.
- Prerequisite: enables enforcement of curriculum logic.
- Normalized design supports future features like attendance, feedback, or timetable modules.

  
## RESULT
Successfully designed an ER diagram for the University Database with entities, relationships, constraints, and a prerequisite-extension using the Prerequisite entity to support real-world academic operations such as structured curriculum flow, enrollment tracking, and program management.

