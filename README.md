# Function to create an empty stack
def create_stack():
   stack = list()
   return stack




# Function to check if a stack is empty
def is_empty(stack):
   return len(stack) == 0




# Function to push an item onto the stack
def push(stack, item):
   stack.append(item)




# Function to pop an item from the stack
def pop(stack):
   if is_empty(stack):
       return "Stack is empty"
   else:
       return stack.pop()




# Function to peek at the top element of the stack
def peek(stack):
   if is_empty(stack):
       return "Stack is empty"
   return stack[-1]




# Function to display the stack elements
def show(stack):
   print(f"Stack Name: {enter}\nThe stack elements are: {stack}")




# Initialize stack and enter variables
stack = None
enter = None


# Display a welcome message and enter a loop for user input
print("Welcome, Please enter the following operations")
while True:
   # Get user input for stack operations and convert to uppercase
   user = str(input(
       "\n[C] - Create Stack\n[A] - Append element to Stack\n[D] - Remove on Stack\n[P] - Peek the top Element of Stack\n[S] - Show the Stack Element\n[E] - Exit\n\nChoose a stack operation: ")).upper()


   # Check the user's choice and execute the corresponding operation
   if user == "C":
       # Prompt the user for a stack name and create an empty stack
       while True:
           enter = input("Enter name of stack: ")
           if len(enter) > 0:
               stack = create_stack()
               print(f"\nYou have now created {enter} stack")
               break
           else:
               print("Please enter a name for the stack.")
   elif user == "A":
       if stack is None:
           print("\nYou must create a stack first to use other features")
           continue
       else:
           # Prompt the user for an element to push onto the stack
           ask = input("Enter an element: ")
           push(stack, ask)
           print(f"\nPushed item: {ask}\n{enter} {stack}")
   elif user == "D":
       if stack is None:
           print("\nYou must create a stack first to use other features")
           continue
       else:
           # Pop an item from the stack
           popped = pop(stack)
           print("\nThe word popped is:", popped)
           print(enter, stack)
   elif user == "P":
       if stack is None:
           print("\nYou must create a stack first to use other features")
           continue
       if is_empty(stack):
           print(f"\nThe stack is empty. There are no elements to peek. \n{enter} {stack}")
       else:
           # Peek at the top element of the stack
           print(f"\nThe peek of the word:", peek(stack))
           print(enter, stack)
   elif user == "S":
       if stack is None:
           print("\nYou must create a stack first to use other features")
           continue
       if is_empty(stack):
           print(f"\nThe stack is empty. There are no elements to show \n{enter} {stack}")
       else:
           # Display the stack elements
           show(stack)
   elif user == "E":
       # Exit the program
       break
   else:
       print("\nPlease enter only the following operations")
