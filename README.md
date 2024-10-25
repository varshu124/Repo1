class Student:
    def __init__(self, name):
        self.name = name
        self.grades = []
    def add_grade(self, grade):
        self.grades.append(grade)
    def average_grade(self):
        return sum(self.grades) / len(self.grades)
    def highest_grade(self):
        return max(self.grades)
    def lowest_grade(self):
        return min(self.grades)
def main():
    students = {}
    while True:
        print("1. Add student")
        print("2. Add grade")
        print("3. Compute average, highest, and lowest scores")
        print("4. Exit")
        choice = input("Enter your choice: ")
        if choice == "1":
            name = input("Enter student name: ")
            students[name] = Student(name)
        elif choice == "2":
            name = input("Enter student name: ")
            grade = float(input("Enter grade: "))
            students[name].add_grade(grade)
        elif choice == "3":
            name = input("Enter student name: ")
            student = students[name]
            print("Average grade:", student.average_grade())
            print("Highest grade:", student.highest_grade())
            print("Lowest grade:", student.lowest_grade())
        elif choice == "4":
            break
        else:
            print("Invalid choice. Please try again.")
if __name__ == "__main__":
    main()
