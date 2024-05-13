erDiagram
    DATABASE EDUCATIONDB {
        Student {
            id INT
            grade INT
            first_name VARCHAR(50)
            other_name VARCHAR(50)
            sur_name VARCHAR(50)
            address VARCHAR(100)
        }
        Course_offered {
            section VARCHAR(20)
            day VARCHAR(20)
            time TIME
            location VARCHAR(100)
        }
        Employee {
            id INT
            first_name VARCHAR(50)
            other_name VARCHAR(50)
            surname VARCHAR(50)
            salary DECIMAL(10, 2)
            designation VARCHAR(50)
        }
        Department {
            id INT
            name VARCHAR(50)
            description TEXT
        }
        Course {
            title VARCHAR(100)
            credits INT
            level VARCHAR(20)
            semester INT
            year INT
        }
        Semester {
            semester_number INT
            year INT
        }
        Faculty {
            qualification VARCHAR(100)
            type VARCHAR(50)
        }
        Class {
            type VARCHAR(50)
            location VARCHAR(100)
            number INT
        }
    }
    Student ||--|{ Course_offered: takes
    Student ||--|{ Course: enrolled
    Employee }--| Department: belongs_to
    Course_offered }--| Course: offered
    Course }--| Semester: offered_in
    Employee }--| Faculty: employs
    Faculty }--| Department: teaches
    Course_offered }--| Class: scheduled
