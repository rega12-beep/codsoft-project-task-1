# codsoft-project-task-1
def main():
    works = []

    while True:
        print("\n===== To-Do List =====")
        print("1. Add work")
        print("2. Show work")
        print("3. Mark work as Done")
        print("4. Exit")

        choice = input(" Please Enter your choice: ")

        if choice == '1':
            print()
            n_works = int(input("How many work would you like to add: "))

            for i in range(n_works):
                work = input(" Please Enter the work: ")
                works.append({"work": work, "done": False})
            print("work added!")

        elif choice == '2':
            print("\n Current works:")
            for index, work in enumerate(works):
                status = "Done" if work["done"] else "Not Done"
                print(f"{index + 1}. {work['work']} - {status}")

        elif choice == '3':
            work_index = int(input(" Please Enter the work number to mark as done: ")) - 1
            if 0 <= work_index < len(works):
                works[work_index]["done"] = True
                print("work has been marked as done!")
            else:
                print("Invalid work number.")

        elif choice == '4':
            print("Exiting the To-Do List. Thank you")
            break

        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
