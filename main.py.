# 📝 Simple To-Do List Project (Python)

class ToDoList:
    def __init__(self):
        self.tasks = []
        self.load_tasks()

    def show_tasks(self):
        if not self.tasks:
            print("📭 No tasks yet.")
        else:
            print("\n📋 Your To-Do List:")
            for i, task in enumerate(self.tasks, start=1):
                print(f"{i}. {task}")

    def add_task(self, task):
        self.tasks.append(task)
        print(f"➕ Task '{task}' added!")

    def delete_task(self, index):
        if 0 <= index < len(self.tasks):
            removed = self.tasks.pop(index)
            print(f"❌ Task '{removed}' deleted!")
        else:
            print("⚠ Invalid task number.")

    def save_tasks(self):
        with open("tasks.txt", "w") as f:
            for task in self.tasks:
                f.write(task + "\n")

    def load_tasks(self):
        try:
            with open("tasks.txt", "r") as f:
                self.tasks = [line.strip() for line in f.readlines()]
        except FileNotFoundError:
            self.tasks = []

def main():
    todo = ToDoList()
    while True:
        print("\n==== MENU ====")
        print("1. Show tasks")
        print("2. Add task")
        print("3. Delete task")
        print("4. Exit")
        choice = input("Choose (1-4): ")

        if choice == "1":
            todo.show_tasks()
        elif choice == "2":
            task = input("Enter a new task: ")
            todo.add_task(task)
        elif choice == "3":
            num = int(input("Enter task number to delete: ")) - 1
            todo.delete_task(num)
        elif choice == "4":
            todo.save_tasks()
            print("👋 Goodbye! Tasks saved in tasks.txt")
            break
        else:
            print("⚠ Invalid choice. Try again.")

if __name__ == "__main__":
    main()
