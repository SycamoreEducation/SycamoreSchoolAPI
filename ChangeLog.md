# Change Log

Any additions, subtractions, multiplications or divisions of the API will be recorded here as a living history of the API

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
