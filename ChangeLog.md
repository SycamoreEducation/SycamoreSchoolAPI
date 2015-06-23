# Change Log

Any additions, subtractions, multiplications or divisions of the API will be recorded here as a living history of the 
API

---

### 06/23/2015 
**Endpoints edited**
 - [School/:SchoolID/Documents](Endpoints/School/Documents.md) *(new)*
 - [School/:SchoolID/Documents/:DocumentID](Endpoints/School/Document.md) *(new)*
 - [Student/:StudentID/Attendance](Endpoints/Students/Attendance.md) *(new)*
 - [Student/:StudentID/Classes/:ClassID/Attendance](Endpoints/Students/Class_Attendance.md) *(new)*

**Changes made**
 - Added new endpoint that returns a list of the documents uploaded to the school
 - Added new endpoint that returns details about a specific document
 - Added new endpoint that returns overview of a students attendance records
 - Added new endpoint that returns details about a specific student's attendance records in a particular class

---

### 05/26/2015 
**Endpoints edited**
 - [School/:SchoolID/Students](Endpoints/School/Students.md) *(new)*
 - [Student/:StudentID](Endpoints/Student/Student.md) *(new)*

**Changes made**
 - Added new endpoint that returns a list of the students that are currently enrolled in a school
 - Added new endpoint that returns details about a specific student

---

### 05/18/2015
**Endpoints edited**
- [School/:SchoolID/Years](Endpoints/School/Years.md) *(new)*
- [School/:SchoolID/Years/:YearID](Endpoints/School/Year.md) *(new)*
- [School/:SchoolID/Classes/:ClassID](Endpoints/Student/Grades.md)

**Changes made**
- Two new endpoints added to give more information about School Years
- Updated documentation to reflect new data being returned. New data includes: "PrimaryTeacherID", "PrimaryTeacher", "Category", "CategoryID", "DepartmentID", "Department", and "TermLength". 

---

### 04/09/2015
**Endpoints edited**
- [Student/:StudentID/Grades](Endpoints/Student/Grades.md)
- [Student/:StudentID/Class/:ClassID/Grades](Endpoints/Student/Assignment_Grades.md)

**Changes made**
- If a classroom is been set up for "Semester Grading" inside of the system, these end points will adjust the value for `Quarter` to look for Posted and Assignment grades in the correct locations

---

### 03/26/2015
**Endpoints edited**
- none

**Changes made**
- When looking up the current quarter, if today's date is not assigned to a quarter, the API will look backwards in time to the first date that does have a quarter and return that value instead of a 0.

---

### 03/25/2015
**Endpoints edited**
 - [Student/:StudentID/Statistics](Endpoints/Student/Statistics.md)
 - [Student/:StudentID/Statistics/:StatisticID](Endpoints/Student/Statistic.md)

**Changes made**
 - Added the check for District/Diocese and State level statistics and included them in the returned results
 - Modified returned values: added arrays for Local, District and State that will contain their respective statistics for the student

---

### 02/17/2015
**Endpoints edited**
 - [Class/:ClassID/Attendance](Endpoints/Class/Attendance.md#post)
 - [Student/:StudentID/Statistics](Endpoints/Students/Statistics.md)
 - [Student/:StudentID/Statistics/:StatisticID](Endpoints/Students/Statistic.md)

**Changes made** 
 - Edited notes on POST requests to specify that POSTed data for a student that already has attendance records in the system will update their existing records
 - Student Statistics and Student Statistic endpoints added
 
---

### 02/06/2015
**Endpoints edited**
 - [Class/:ClassID/Attendance](Endpoints/Class/Attendance.md#post)

**Changes made** 
 - Added a 'Comments' field (string) that can be included on each student's object when POSTing attendance. 
 - Edited Class Activity message to relay that attendance was taken from the API and not the 'app'
 - Only insert Class Activity record if a creation or update of attendance records was successful
 
---

### 02/04/2015
**Endpoints edited**
 - [School/:SchoolID/News/:NewsID](Endpoints/School/News_Article.md)

**Changes made** 
 - When viewing an article with the option `nohtml=1`, we now convert content of news article to UTF-8 to better strip the formatting

---
