# Student Exam and Results Management System

A command-line Python application for registering students, recording examination marks, calculating academic results, and monitoring class performance.

The system was developed using **Object-Oriented Programming (OOP)** principles. It provides a simple menu-driven interface with coloured terminal output to make student records and examination results easier to read.

## Features

- **Student registration** — register a student with a student ID, full name, programme, and examination marks.
- **Input validation** — prevent empty student details, duplicate student IDs, non-numeric marks, and marks outside the `0–100` range.
- **Automatic result calculation** — calculate each student's average across Programming, Mathematics, and Communication.
- **Grade assignment** — assign a grade automatically based on the student's average.
- **Pass/fail evaluation** — a student passes only when the overall average is at least 50% and every subject mark is at least 50%.
- **Student search** — find a student's record using their student ID.
- **Student records and results** — display all registered students and their examination results.
- **Performance dashboard** — show the total number of students, pass and fail counts, pass rate, class average, and top-performing student.
- **Student ranking** — rank students from the highest to the lowest average.
- **Mark updates** — update a registered student's examination marks and recalculate the result.
- **Terminal formatting** — use ANSI colour codes, headings, and progress bars for a clearer user experience.

## Technologies Used

- **Python 3** — application logic and object-oriented programming.
- **ANSI escape codes** — coloured terminal output without an external colour library.
- **Python standard library** — no third-party packages are required.

## Requirements

- Python 3.8 or later is recommended.
- A terminal or command prompt that supports ANSI escape codes.

No external dependencies or package installation are required.

## Getting Started

### 1. Clone the repository

```bash
git clone <repository-url>
```

### 2. Open the project directory

```bash
cd <project-directory>
```

### 3. Run the application

If the Python file is named `main.py`, run:

```bash
python main.py
```

If your file has a different name, replace `main.py` with its actual filename.

On some systems, you may need to use:

```bash
python3 main.py
```

## How to Use

When the application starts, it displays the main menu:

| Option | Action |
|---|---|
| 1 | Register a new student |
| 2 | Display all students and results |
| 3 | Search student by ID |
| 4 | View the student management dashboard |
| 5 | Rank students |
| 6 | Update examination marks |
| 7 | Exit the application |

Enter the number corresponding to the action you want to perform, then follow the prompts.

### Registering a student

Provide the student's:
- Student ID
- Full name
- Programme
- Programming mark
- Mathematics mark
- Communication mark

Each examination mark must be a number between `0` and `100`. Student IDs must be unique.

### Understanding grades

The application calculates the average of the three subject marks and assigns a grade using the following scale:

| Average | Grade |
|---:|:---:|
| 80–100 | A |
| 70–79.99 | B |
| 60–69.99 | C |
| 50–59.99 | D |
| Below 50 | F |

**Pass requirement:** The student must have an average of at least 50% and score at least 50 in each of the three subjects. Otherwise, the result is **FAIL**.

## Object-Oriented Design

The application uses two main classes:

### `Student`

The `Student` class represents an individual student.

It stores:
- `student_id`
- `name`
- `program`

It also provides:
- `display_info()` — displays the student's details.
- `university_name()` — a class method that returns the university name.

The class-level university attribute is set to **Limkokwing University**.

### `Result`

The `Result` class stores a student's examination marks and calculates their academic performance.

It stores:
- The associated `Student` object
- `programming`
- `mathematics`
- `communication`

Its methods handle:
- Average calculation
- Grade calculation
- Pass/fail evaluation
- Result display

Each `Result` object is linked to its corresponding `Student` object. This demonstrates object composition: a result contains a reference to the student whose marks are being recorded.

## Main Program Functions

| Function | Purpose |
|---|---|
| `register_student()` | Collects student details and marks, validates the input, and registers the student. |
| `display_all_students()` | Displays all registered students and their results. |
| `search_student()` | Searches for a student by ID. |
| `display_dashboard()` | Summarises class performance. |
| `rank_students()` | Sorts students by average mark in descending order. |
| `update_marks()` | Updates a student's marks. |
| `find_student()` | Finds a registered student record by ID. |
| `get_mark()` | Validates an examination mark. |
| `main()` | Runs the application's menu and controls program flow. |

## Data Storage

Student records are stored in an in-memory Python list while the application is running.

**Important:** The application does not currently use a database or save records to a file. Registered students and updated marks are therefore lost when the program closes.

## Project Structure

```text
student-exam-results-management/
│
├── main.py
└── README.md
```

The filename `main.py` is an example. Use the actual Python filename in your project if it is different.

## Possible Future Improvements

The application could be extended with:
- File or database storage so records remain available after closing the program.
- Student record deletion.
- More subjects and configurable grading scales.
- Exportable student reports.
- Login and role-based access for administrators and lecturers.
- A graphical user interface or web-based dashboard.

## Author

**Michael Tucker**  
Software Engineering Student  
Limkokwing University of Creative Technology

## License

This project is intended for educational and academic use. Add a separate `LICENSE` file if you decide to distribute it under a specific open-source licence.
