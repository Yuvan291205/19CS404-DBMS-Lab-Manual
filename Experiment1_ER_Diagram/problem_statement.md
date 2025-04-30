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

# ER Diagram Submission - Yuvan M

## Scenario Chosen:
University 

## ER Diagram:
![image](https://github.com/user-attachments/assets/23722860-94b2-4c22-b53e-0ccb1367a55b)


## Entities and Attributes:
STUDENT: Admission No,Name,Date of Birth,Phone No,Email id
PROGRAM: Program ID, Program Name, Department
DEPARTMENT: Department id,Department Name
COURSE: Course id,Course Name,Credits
INSTRUCTOR: Staff id,Staff Name,Date Of Birth,PhoneNumber,Email id
...
...

## Relationships and Constraints:
Enrolls (STUDENT — PROGRAM) Cardinality: Many-to-One (Many students can enroll in one program)
Participation: Total on STUDENT (every student must enroll in a program), partial on PROGRAM (not all programs may have enrolled students)

Governing Department (PROGRAM — DEPARTMENT) Cardinality: Many-to-One (Many programs are governed by one department)
Participation: Total on PROGRAM, partial on DEPARTMENT

Grouped (DEPARTMENT — PROGRAM) Cardinality: One-to-Many (One department can group multiple programs)
Participation: Partial on both sides (not all departments may have programs, and not all programs must be grouped under a department explicitly — this is slightly redundant with "Governing Department")

Catalogue (PROGRAM — COURSE) Cardinality: One-to-Many (One program can offer many courses)
Participation: Total on COURSE (every course must belong to a program), partial on PROGRAM

Register (STUDENT — COURSE) Cardinality: Many-to-Many (A student can register in many courses, and each course can have many students)
Participation: Partial on both

Teaching (INSTRUCTOR — COURSE) Cardinality: One-to-Many (One instructor teaches multiple courses)
Participation: Total on COURSE (each course must be taught by an instructor), partial on INSTRUCTOR

...

Extension (Prerequisite / Billing):
Modeling Prerequisites (for Courses): New Relationship: Prerequisite
Entities Involved: COURSE — COURSE (a recursive relationship)

Meaning: A course may require completion of another course before enrollment.

Structure:

Relationship Name: Prerequisite

Attributes: Possibly Required Grade or Prerequisite Type (optional)

Cardinality: Many-to-Many (a course can have multiple prerequisites and be a prerequisite for multiple other courses)

Participation: Partial on both (not all courses require or are prerequisites)

Example: Course A ➝ prerequisite ➝ Course B Means: Course A requires Course B before a student can enroll. 2. Modeling Billing (for Students): New Entity: BILLING

Entities Involved: STUDENT (1) — (M) BILLING

Meaning: Each student can have multiple billing records (tuition, course fees, fines, etc.)

Structure:

Entity Name: BILLING

Attributes: Billing_ID (PK), Student_ID (FK),Amount,Due_Date,Payment_Status

Billing_Type (e.g., Tuition, Lab Fee, Late Fee)

Cardinality: One-to-Many (One student can have multiple billing records)
...

## Extension (Prerequisite / Billing)

## Design Choices:
Entities Chosen: STUDENT: Core entity representing individuals enrolled in programs. PROGRAM: Groups of courses forming academic paths like BSc, MSc. DEPARTMENT: Academic units managing programs and instructors.

COURSE: Units of instruction students register for.

INSTRUCTOR: Staff responsible for teaching courses.

Relationships Chosen: Enrolls: Links students to their academic programs. Catalogue: Shows which courses belong to which program.

Register: Connects students with the courses they take.

Teaching: Assigns instructors to courses.

Governing Department: Indicates which department runs a program.

Assumptions: Students enroll in one program.

Courses belong to programs and are taught by one instructor.

Students can take multiple courses, and each course can have many students.

## RESULT
Thus, to understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application has been done successfully.
