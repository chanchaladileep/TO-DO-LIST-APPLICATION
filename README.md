# TO-DO-LIST-APPLICATION
def add_task(tasks, task):
    tasks.append(task)
    print(f"Task '{task}' added.")

def view_tasks(tasks):
    if not tasks:
        print("No tasks in the list.")
        return
    for index, task in enumerate(tasks):
        print(f"{index + 1}. {task}")

def delete_task(tasks, task_number):
    try:
        index = task_number - 1
        deleted_task = tasks.pop(index)
        print(f"Task '{deleted_task}' deleted.")
    except IndexError:
        print("Invalid task number.")

def main():
    tasks = []

    while True:
        print("\nOptions:")
        print("1. Add task")
        print("2. View tasks")
        print("3. Delete task")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            task = input("Enter task to add: ")
            add_task(tasks, task)
        elif choice == '2':
            view_tasks(tasks)
        elif choice == '3':
            task_number = int(input("Enter task number to delete: "))
            delete_task(tasks, task_number)
        elif choice == '4':
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
