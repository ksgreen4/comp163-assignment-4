student_name = "Kimoria Green" 
current_gpa = 3.00               
study_hours = 25
social_points = 50
stress_level = 30

def display_stats():
    print("Welcome to College Life Adventure!")
    print(f"Player:{student_name}")
    print("Starting statistics:")
    print(f"GPA:{current_gpa}")
    print(f"Study hours available:{study_hours}")
    print(f"Social points:{social_points}")
    print(f"Stress level:{stress_level}")

def course_planning():
    global study_hours, stress_level

    print("\nChoose your course load:")
    print("A) Light (12 credits)")
    print("B) Standard (15 credits)")
    print("C) Heavy (18 credits)")

    choice = input("Your choice: ")

    if choice == "A":
        if current_gpa >= 3.0:
            print("High GPA! Light load will keep you balanced.")
            study_hours += 5
            stress_level -= 5
        else:
            print("Lower GPA — Light load may not be enough to catch up.")
            study_hours += 2
            stress_level += 5

    elif choice == "B":
        if current_gpa >= 3.0:
            print("High GPA! Standard load is manageable.")
            study_hours += 3
            stress_level += 5
        else:
            print("Lower GPA — Standard load may be stressful.")
            study_hours += 1
            stress_level += 10

    elif choice == "C":
        if current_gpa >= 3.5:
            print("High GPA! You can handle a heavy load confidently.")
            study_hours -= 5
            stress_level += 10
        else:
            print("Lower GPA — Heavy load may overwhelm you.")
            study_hours -= 10
            stress_level += 20

    else:
        print("Invalid choice. Please select A, B, or C.")

if __name__ == "__main__": #AI was used here to understand what was wrong with my code, I didn't add this part
    display_stats()
    course_planning()

study_options = ["Programming", "Math", "English", "History"]

print("Choose a subject to focus on from:", study_options)
study_choice = input("Your choice: ")

if study_choice in study_options:
    print("Valid choice!")
    if study_choice == "Programming" and current_gpa < 3.0:
        current_gpa += 0.5
        print("Extra programming practice boosted your GPA!")
    elif study_choice == "Math" or study_choice == "English":
        social_points += 5
        print("Studying", study_choice, "helped you connect with classmates.")
    elif study_choice == "History" and not stress_level > 80:
        stress_level += 5
        print("History added some extra workload, but manageable.")
elif study_choice not in study_options:   #AI was used to figure out why my code wasn't working in line 79
    print("Not a valid study choice.")

print("\n--- Final Semester Assessment ---")

if type(current_gpa) is float:
    print("GPA is stored correctly as a float.")
else:
    print("GPA type is not float.")

if current_gpa >= 3.5:
    if stress_level < 40:
        print("You graduate with honors and low stress.")
    else:
        print("You graduate with honors, but stress impacted your health.")
elif current_gpa >= 2.0:
    if social_points > 60:
        print("You graduate with a balanced life and good social connections.")
    else:
        print("You graduate, but without strong social support.")
else:
    if stress_level is not 0:     #AI was used here because I didn't add "is not" it kept giving me an error
        print("You did not graduate this semester.")
    else:
        print("Unexpected outcome, please try again.")
