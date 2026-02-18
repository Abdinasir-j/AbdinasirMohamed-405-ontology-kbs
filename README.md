# University Advising Ontology KBS

## Description
This project implements a small Knowledge-Based System (KBS) for university course advising. It uses an ontology to define students, courses, and their prerequisites to determine enrollment eligibility and suggest future learning paths.

## Ontology Concepts
- **Classes**: Student, Course
- **Relationships**: 
  - `requires`: Maps a course to its necessary prerequisites.
  - `completed`: Maps a student to the courses they have successfully passed.
  - `eligibleFor`: An inferred relationship determining if a student can enroll in a course.

## Inference Logic
The system uses forward-chaining logic:
1. It retrieves the required prerequisite set for a target course.
2. It retrieves the student's set of completed courses.
3. It performs a set difference (`prerequisites - completed`).
4. If the resulting set is empty, the student is `eligibleFor` the course.

## How to Run
1. Open `AbdinasirMohamed-405-ontology-kbs.ipynb` in VS Code.
2. Ensure you have the Jupyter extension installed.
3. Click **Run All Cells**.
4. The unit tests will execute in the final cell.

## Example Output
```text
Abdinasir -> SWE2040: Eligible
Mohamed -> Java_SWE3040: Not Eligible (Missing: {'Intro_Programming'})
Next courses for Abdinasir: ['Cloud_Computing', 'Database_Systems', 'Frameworks_SWE2040']
Ran 6 tests in 0.005s
OK