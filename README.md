# Simple-To-Do-List-Application
Create a Python program for adding, completing, and removing tasks—a simple introduction to Python programming.
Creating a simple Python program for managing tasks (adding, completing, and removing) is a great way to learn basic Python programming concepts. Below, I’ll provide a step-by-step guide to building a command-line-based task manager. This program will use a dictionary to store tasks, with each task having a status indicating whether it’s completed or not.

Here’s a simple outline of the program:

Display Menu: Show options to the user.
Add Task: Add a new task.
Complete Task: Mark a task as completed.
Remove Task: Remove a task.
List Tasks: List all tasks with their status.
Exit: Exit the program.
Let’s implement each part step-by-step.

Step 1: Display Menu
First, we’ll create a function to display the menu options.

python
Copy code
def display_menu():
    print("\nTask Manager Menu")
    print("1. Add Task")
    print("2. Complete Task")
    print("3. Remove Task")
    print("4. List Tasks")
    print("5. Exit")
Step 2: Add Task
Next, we’ll write a function to add a new task to our task dictionary.

python
Copy code
def add_task(tasks):
    task_name = input("Enter the task name: ")
    tasks[task_name] = False  # Task is initially not completed
    print(f"Task '{task_name}' added.")
Step 3: Complete Task
Now, let’s create a function to mark a task as completed.

python
Copy code
def complete_task(tasks):
    task_name = input("Enter the task name to complete: ")
    if task_name in tasks:
        tasks[task_name] = True
        print(f"Task '{task_name}' marked as completed.")
    else:
        print(f"Task '{task_name}' not found.")
Step 4: Remove Task
This function will allow us to remove a task from the dictionary.

python
Copy code
def remove_task(tasks):
    task_name = input("Enter the task name to remove: ")
    if task_name in tasks:
        del tasks[task_name]
        print(f"Task '{task_name}' removed.")
    else:
        print(f"Task '{task_name}' not found.")
Step 5: List Tasks
We’ll write a function to list all tasks along with their completion status.

python
Copy code
def list_tasks(tasks):
    if not tasks:
        print("No tasks available.")
    else:
        for task, completed in tasks.items():
            status = "Completed" if completed else "Not Completed"
            print(f"{task}: {status}")
Step 6: Main Program Loop
Finally, we’ll put everything together in a main loop to allow user interaction.

python
Copy code
def main():
    tasks = {}  # Dictionary to store tasks
    while True:
        display_menu()
        choice = input("Choose an option: ")
        
        if choice == '1':
            add_task(tasks)
        elif choice == '2':
            complete_task(tasks)
        elif choice == '3':
            remove_task(tasks)
        elif choice == '4':
            list_tasks(tasks)
        elif choice == '5':
            print("Exiting the program. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
Complete Code
Here’s the complete code for the task manager:

python
Copy code
def display_menu():
    print("\nTask Manager Menu")
    print("1. Add Task")
    print("2. Complete Task")
    print("3. Remove Task")
    print("4. List Tasks")
    print("5. Exit")

def add_task(tasks):
    task_name = input("Enter the task name: ")
    tasks[task_name] = False  # Task is initially not completed
    print(f"Task '{task_name}' added.")

def complete_task(tasks):
    task_name = input("Enter the task name to complete: ")
    if task_name in tasks:
        tasks[task_name] = True
        print(f"Task '{task_name}' marked as completed.")
    else:
        print(f"Task '{task_name}' not found.")

def remove_task(tasks):
    task_name = input("Enter the task name to remove: ")
    if task_name in tasks:
        del tasks[task_name]
        print(f"Task '{task_name}' removed.")
    else:
        print(f"Task '{task_name}' not found.")

def list_tasks(tasks):
    if not tasks:
        print("No tasks available.")
    else:
        for task, completed in tasks.items():
            status = "Completed" if completed else "Not Completed"
            print(f"{task}: {status}")

def main():
    tasks = {}  # Dictionary to store tasks
    while True:
        display_menu()
        choice = input("Choose an option: ")
        
        if choice == '1':
            add_task(tasks)
        elif choice == '2':
            complete_task(tasks)
        elif choice == '3':
            remove_task(tasks)
        elif choice == '4':
            list_tasks(tasks)
        elif choice == '5':
            print("Exiting the program. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
How to Run the Program
Save the code to a file, e.g., task_manager.py.
Open a terminal or command prompt.
Navigate to the directory containing task_manager.py.
Run the program with python task_manager.py.
This program demonstrates basic concepts such as dictionaries, loops, functions, and user input. You can expand on it by adding features like saving tasks to a file or improving the user interface.





