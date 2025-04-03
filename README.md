# 🐍 YAML & Python: Managing Student Data

## 🌟 Introduction
Welcome to this hands-on project where we leverage YAML in Python to store, display, and filter student data efficiently. This application reads student records from a YAML file, showcases the data, and enables filtering based on GPA. A simple yet powerful way to manage structured information!

## 🛠️ Prerequisites
Before you get started, ensure you have the following set up:
- **Python** installed on your system.
- **PyYAML** package installed. You can install it using:

```sh
pip install pyyaml
```

## 📂 Project Structure
This project consists of two key files:
1. **`students.yaml`** – YAML file containing student data.
2. **`app.py`** – Python script to read, display, and filter students.

## 📜 Creating the YAML File
Create a file named `students.yaml` and populate it with student records:

```yaml
students:
  - name: Alice
    age: 21
    major: Computer Science
    gpa: 3.8
  - name: Bob
    age: 22
    major: Mathematics
    gpa: 3.5
  - name: Charlie
    age: 20
    major: Physics
    gpa: 3.9
  - name: David
    age: 23
    major: Chemistry
    gpa: 3.2
  - name: Eva
    age: 21
    major: Computer Science
    gpa: 3.7
```

## 🐍 Writing the Python Script
Create a file named `app.py` and add the following code:

```python
import yaml

def load_data(file_path):
    """Load student data from a YAML file."""
    with open(file_path, 'r') as file:
        return yaml.safe_load(file)

def display_students(students):
    """Display all students."""
    print("\n📋 All Students:")
    for student in students:
        print(f"👤 {student['name']} | Age: {student['age']} | Major: {student['major']} | GPA: {student['gpa']}")

def filter_students_by_gpa(students, min_gpa):
    """Filter students by GPA."""
    filtered = [s for s in students if s['gpa'] >= min_gpa]
    print(f"\n🎓 Students with GPA ≥ {min_gpa}:")
    if filtered:
        for student in filtered:
            print(f"✅ {student['name']} | Age: {student['age']} | Major: {student['major']} | GPA: {student['gpa']}")
    else:
        print("❌ No students found.")

def main():
    data = load_data('students.yaml')
    students = data['students']
    display_students(students)
    min_gpa = float(input("\nEnter minimum GPA to filter students: "))
    filter_students_by_gpa(students, min_gpa)

if __name__ == "__main__":
    main()
```

## 🚀 Running the Application
Ensure `students.yaml` and `app.py` are in the same directory, then execute the script:

```sh
python app.py
```

### 🎯 Expected Output
```sh
📋 All Students:
👤 Alice | Age: 21 | Major: Computer Science | GPA: 3.8
👤 Bob | Age: 22 | Major: Mathematics | GPA: 3.5
👤 Charlie | Age: 20 | Major: Physics | GPA: 3.9
👤 David | Age: 23 | Major: Chemistry | GPA: 3.2
👤 Eva | Age: 21 | Major: Computer Science | GPA: 3.7

Enter minimum GPA to filter students: 3.6

🎓 Students with GPA ≥ 3.6:
✅ Alice | Age: 21 | Major: Computer Science | GPA: 3.8
✅ Charlie | Age: 20 | Major: Physics | GPA: 3.9
✅ Eva | Age: 21 | Major: Computer Science | GPA: 3.7
```

## 📤 Uploading to GitHub
### 🔹 Initializing Git Repository
```sh
git init
git add .
git commit -m "Initial commit - Python YAML student manager"
```

### 🔹 Adding Remote Repository
Replace `<your-username>` and `<your-repo-name>` accordingly:

```sh
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git branch -M main
git push -u origin main
```

### 🔹 Handling Errors
If you encounter issues pushing to GitHub:
```sh
git pull origin main --rebase
git push origin main
```
If necessary, force push:
```sh
git push origin main --force
```

## 🎯 Enhancements & Next Steps
This is just the beginning! You can improve the project by:
- Adding **sorting features** (e.g., sort students by GPA, age, or name).
- Implementing **data update functionality** (e.g., adding or removing students dynamically).
- Saving **filtered results back to the YAML file**.
- Creating a **GUI version** using Tkinter or Flask for a more interactive experience.

🚀 **Happy coding & keep exploring!**

