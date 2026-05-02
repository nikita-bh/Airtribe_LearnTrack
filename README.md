# LearnTrack - Student Course Management System

## Project Description

LearnTrack is a console-based Java application designed to manage students, courses, and enrollments in a simple and efficient way.

---

## Functionalities

### Student Management
- Add new students
- View all students
- Search student by ID
- Deactivate a student

## Course Management
- Add new courses
- View all courses


## Enrollment Management
- Enroll a student in a course
- View active enrollments
- Update enrollment status (ACTIVE, COMPLETED, CANCELLED)

---

## Features
- Uses ArrayList 
- Implements OOP principle
- Includes custom exception handling
- Menu-driven console UI for user interaction


## Objective
This project demonstrates basic Java application design, clean code practices, and separation of concerns.



## Class Diagram


## ================= ENTITY LAYER =================

class Student {
-int id
-String fName
-String lName
-String email
-String batch
-boolean isActive
+getId()
+getfName()
+getlName()
+getEmail()
+getBatch()
+isActive()
}

class Course {
-int id
-String courseName
-String description
-int durationInWeeks
-boolean active
+getId()
+getCourseName()
+getDescription()
+getDurationInWeeks()
+isActive()
}

class Enrollment {
-Long id
-Long studentId
-Long courseId
-String enrollmentDate
-String status
+getId()
+getStudentId()
+getCourseId()
+getStatus()
}

## ================= SERVICE LAYER =================

class StudentService {
-ArrayList~Student~ students
+addStudent()
+removeStudent()
+updateStudent()
+getAllStudents()
}

class CourseService {
-ArrayList~Course~ courses
+addCourse()
+removeCourse()
+updateCourse()
+getAllCourses()
}

class EnrollmentService {
-ArrayList~Enrollment~ enrollments
+addEnrollment()
+getActiveEnrollments()
+findEnrollmentById()
+updateEnrollmentStatus()
+cancelEnrollment()
}

## ================= UTIL =================

class IdGenerator {
-static int studentIdCounter
-static int courseIdCounter
-static int enrollmentIdCounter
+generateStudentId()
+generateCourseId()
+generateEnrollmentId()
}

## ================= RELATIONSHIPS =================

StudentService --> Student : manages
CourseService --> Course : manages
EnrollmentService --> Enrollment : manages

Enrollment --> Student : references (studentId)
Enrollment --> Course : references (courseId)

Student --> IdGenerator : uses
Course --> IdGenerator : uses
EnrollmentService --> IdGenerator : uses
