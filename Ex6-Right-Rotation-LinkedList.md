# Ex6 Right Rotation LinkedList
## DATE: 21-07-2026
## AIM:
To write a Java  program to:
Create a singly linked list.
Rotate the linked list to the right by k positions.
Display the rotated linked list.
## Algorithm

    1. Start the program.
    2. Handle edge cases.
    3. Find the length of the linked list.
    4. Connect the last node to the head (make the list circular).
    5. Normalize `k` and find the new tail position.
    6. Break the circle to form the new linked list and return `newHead`.
    7. Stop the program.

## Program:

    /*
    Program to  Right Rotation LinkedList
    Developed by: VESHWANTH .
    RegisterNumber: 212224230300
    */
    
    import java.util.Scanner;
    public class RotateLinkedList {
        public static Node rotate(Node head, int k) {
            if (head == null || head.next == null || k == 0) {
                return head;
            }
            Node current = head;
            int length = 1;
            while (current.next != null) {
                current = current.next;
                length++;
            }
            current.next = head;
            k = k % length;
            int stepsToNewHead = length - k;
            Node newTail = current;
            while (stepsToNewHead-- > 0) {
                newTail = newTail.next;
            }
            Node newHead = newTail.next;
            newTail.next = null;
            return newHead;
        }
        public static void display(Node head) {
            Node current = head;
            System.out.print("LinkedList: ");
            while (current != null) {
                System.out.print(current.data + " ");
                current = current.next;
            }
            System.out.println();
        }
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            Node head = null, tail = null;
            int n = scanner.nextInt();
            for (int i = 0; i < n; i++) {
                Node newNode = new Node(scanner.nextInt());
                if (head == null) {
                    head = tail = newNode;
                } else {
                    tail.next = newNode;
                    tail = newNode;
                }
            }
            int k = scanner.nextInt();
            head = rotate(head, k);
            display(head);
            scanner.close();
        }
    }
    class Node {
        int data;
        Node next;
        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }
    
    
## Output:

<img width="1118" height="302" alt="image" src="https://github.com/user-attachments/assets/535be678-ab9b-4eb3-8f9d-9ba68ad0172f" />


## Result:
Thus, the C program to perfom right rotation on linked list is implemented successfully.
