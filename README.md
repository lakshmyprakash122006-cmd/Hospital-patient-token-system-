# Hospital-patient-token-system-
Data structure practical program 
# Hospital Patient Queue

class Node:
    def __init__(self, name):
        self.name = name
        self.next = None

front = None
rear = None

def add_patient():
    global front, rear
    name = input("Enter patient name: ")
    newnode = Node(name)

    if rear is None:
        front = rear = newnode
    else:
        rear.next = newnode
        rear = newnode

def serve_patient():
    global front, rear
    if front is None:
        print("No patients in queue")
    else:
        print("Serving patient:", front.name)
        front = front.next
        if front is None:
            rear = None

def display():
    temp = front
    print("Patients in queue:")
    while temp:
        print(temp.name)
        temp = temp.next

while True:
    print("\n1.Add Patient 2.Serve Patient 3.Display Queue 4.Exit")
    ch = int(input("Enter choice: "))

    if ch == 1:
        add_patient()
    elif ch == 2:
        serve_patient()
    elif ch == 3:
        display()
    elif ch == 4:
        break
    else:
        print("Invalid choice")
  output:
  1.Add Patient 2.Serve Patient 3.Display Queue 4.Exit
Enter choice: 1
Enter patient name: Ravi

Enter choice: 1
Enter patient name: Anu

Enter choice: 3
Patients in queue:
Ravi
Anu

Enter choice: 2
Serving patient: Ravi
