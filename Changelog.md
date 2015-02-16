# Change Log

Any additions, subtractions, multiplications or divisions of the API will be recorded here as a living history of the API

Format:

---

### 02/06/2015
**Endpoints edited**
 - [Class/:ClassID/Attendance](Endpoints/Class/Attendance.md#post)

**Changes made** 
 - Added a 'Comments' field (string) that can be included on each student's object when POSTing attendance. 
 - Edited Class Activity message to relay that attendance was taken from the API and not the 'app'
 - Only insert Class Activity record if a creation or update of attendance records was successful
 
---
