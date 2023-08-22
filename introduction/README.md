Ω#This is my Moringa School Repository

I will appreciate your input from all the codes I will be generating. It 
contains the basics to programs coding

INDEPENDENT PROJECT ON TO DO LIST MANAGER

#TO DO LIST

print ("To-Do List Manager")

instruction = "\n1: Enter add_task to add new To-Do. \n2: Enter mark_task to complete. \n3: Enter list_tasks to list. \n4: Enter remove_task to remove. \n5: Enter quit_todo_list to exit"
print(instruction)

#add to do information on items to be executed


task_list=[]

def to_do_list():
    for task in task_list:
        print(task)
    return task
        
    

running= True
while running:
    #user input for the items to be executed
    user_input=input("\n What do you want to do? (add_task, mark_tasks, list_tasks, remove_task, quit_todo_list) : ")
    if user_input == "add_task":
        new_task= input("\n Please enter your new To-Do: ")
        print(f"\n Your current To-Do is {new_task}.")
        #append to the task_list
        task_list.append(new_task)
   
    #code of updating tasks as complete
    elif user_input == "mark_tasks":
        while True:
            item_name = input("\n Please enter name of task completed.")
            try:
                if item_name in task_list:
                    choice = input(f"Do you want to update {item_name} as complete?: ")
                    if choice == "yes":
                        update_list = (f"{item_name} in the to-do list is complete")
                        index = task_list.index(item_name)
                        task_list[index] = update_list
                        print("Your updated to-do list")
                        to_do_list()
                        break
                else:
                    print("item not found")
            except Exception:
                print("not valid")
    #listing tasks added to the to do list code
    elif user_input == "list_tasks":
        for task in task_list:
            print(task)
            
    #code to delete task
    elif user_input == "remove_task":
        while True:
            item_name = input("\n Please enter name of task to remove.")
            try:
                if item_name in task_list:
                    choice =  input(f"Are you sure you want to remove {item_name}?: ")
                    if choice == "yes":
                        task_list.remove(item_name)
                        print("Your updated tasks")
                        to_do_list()
                        break
                else:
                    print("item not found")
            #except block here
            except Exception:
                print ("not valid") 
    
    #code to quit to do list
    elif user_input == "quit_todo_list":
        ask_user = input("\n Are you sure you want to Quit?: ")
        if ask_user == "yes":
            running = False
            
    elif user_input == "" or user_input == " ":
        print("please enter task.")
    else:
        print("Please enter a task to continue.")

