# Versioning

The Sycamore API will certainly evolve over time. As we get feedback from developers who use it and customers who want to consume it we'll make changes and tweak it. We will aim to never break the API and always keep it backwards compatible. We will, however, make additions to the API which will not affect applications already written. The version will only be incremented when 'breaking' changes need to be made that would interrupt backwards compatibility.

## Current (Stable)

API Version: v1
Release Date: Summer 2014

## Future (Unstable)

API Version: v2
Release Date: TBD

### Breaking changes slated for next version:

- Moving of the School/:schoolID/Classes/:classID endpoint to Class/:classID as it makes more sense for the details to rest at a class level and not a school level
- Removing the "Students" object from the Class/:classID/Cafeteria endpoint, as the same data can be accessed from the Class Directory endpoint
- Removing the "Meals" object from the Class/:classID/Cafeteria endpoint, as the same data can be accessed from the School Cafeteria endpoint
- Merging of the School/:schoolID/Directory/:familyID endpoint to Family/:familyID as it makes more sense for the details to rest at the family level and not the school level
- Standardizing case on parameters and return values. (Either all will be capital or all will be lowercase)
- Standardize date format for User/:userID/Journals and User/:userID/Journal/:journalID to YYYY-MM-DD
- Make the Student ID the key for the objects in the 'Grades' object returned in Class/:classID/Assignments/:assignmentID if there are grades present
- In the case where an ID for an item is returned with the alphanumeric value and there is no endpoint in the API that you can use the ID on, the ID field will be removed. If the ID field can be used to look up additional information, it will be nested in a newly created object for the item with "ID" and "Name/Title" fields. I.E. DepartmentID and Department are returned with the `School/:id/Classes/:id` data but DepartmentID is not used anywhere else in the API. 
