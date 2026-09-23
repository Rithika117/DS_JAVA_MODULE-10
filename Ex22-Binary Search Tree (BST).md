# Ex22 Searching for a Book ID in a Binary Search Tree (BST)
## DATE:3/09/2026
## AIM:
To design and implement java program that constructs a Binary Search Tree (BST) using given Book IDs and checks whether a specific Book ID exists in the BST.
## Algorithm
  Start the program.
Read integer.
Initialize root equals to null.
Repeat n times.
Insert(root, key).
Searching Book ID.
Search(root, key).
Stop the program. 

## Program:
```
/*
Program to constructs a Binary Search Tree (BST) using given Book IDs 
Developed by: Rithika K
RegisterNumber: 212224230230
*/
import java.util.*;

public class BookIDSearch {
    static class Node {
        int data;
        Node left, right;
        Node(int data) {
            this.data = data;
        }
    }

    public static Node insert(Node root, int key) {
        if (root == null) return new Node(key);
        if (key < root.data) root.left = insert(root.left, key);
        else root.right = insert(root.right, key);
        return root;
    }

    public static boolean search(Node root, int key) {
        if (root == null) return false;
        if (root.data == key) return true;
        if (key < root.data) return search(root.left, key);
        else return search(root.right, key);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Node root = null;
        for (int i = 0; i < n; i++) {
            root = insert(root, sc.nextInt());
        }
        int q = sc.nextInt();
        while (q-- > 0) {
            int key = sc.nextInt();
            System.out.println(search(root, key) ? "Found" : "Not Found");
        }
    }
}
```

## Output:
<img width="602" height="455" alt="image" src="https://github.com/user-attachments/assets/ad3d650a-4c19-40e7-9301-24792b65a5cd" />



## Result:
The program has been successfully implemented and executed.
It constructs a Binary Search Tree from the given Book IDs and accurately determines whether a queried Book ID exists in the library system.
