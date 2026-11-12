# Algorithm Battle – Which Data Structure Wins?

## Project overview

This project implements a **Student Record Management System in C** and compares three data structures:

- **Binary Search Tree (BST)** – stores student records by Student ID.
- **AVL Tree** – a self-balancing binary search tree.
- **Hash Table with Linear Probing** – maps Student IDs to table positions and resolves collisions by checking the next available slot.

Each student record contains a Student ID, name, department, and marks.

## Dataset used by `student.c`

The program starts with 30 student records. Student IDs are in ascending order from **2101 to 2130**.

| Student ID | Name | Department | Marks |
|---:|---|---|---:|
| 2101 | Arun | CSE | 88 |
| 2102 | Bharath | ECE | 76 |
| 2103 | Charan | IT | 91 |
| 2104 | Deepak | EEE | 83 |
| 2105 | Ezhil | AIML | 95 |
| 2106 | Farhan | CSE | 79 |
| 2107 | Gokul | ECE | 86 |
| 2108 | Hari | IT | 92 |
| 2109 | Ishaan | EEE | 81 |
| 2110 | Jeeva | AIML | 89 |
| 2111 | Karthik | CSE | 74 |
| 2112 | Lokesh | ECE | 97 |
| 2113 | Madhan | IT | 85 |
| 2114 | Naveen | EEE | 90 |
| 2115 | Pranav | AIML | 78 |
| 2116 | Rahul | CSE | 93 |
| 2117 | Sanjay | ECE | 82 |
| 2118 | Tarun | IT | 87 |
| 2119 | Udhay | EEE | 96 |
| 2120 | Varun | AIML | 80 |
| 2121 | Yuvan | CSE | 84 |
| 2122 | Adithya | ECE | 94 |
| 2123 | Balaji | IT | 77 |
| 2124 | Dinesh | EEE | 89 |
| 2125 | Elango | AIML | 91 |
| 2126 | Ganesh | CSE | 75 |
| 2127 | Harish | ECE | 88 |
| 2128 | Kavin | IT | 92 |
| 2129 | Manoj | EEE | 86 |
| 2130 | Nithin | AIML | 98 |

The performance experiment uses **2115** as the successful-search key and **2199** as the unsuccessful-search key.

## Features and menu options

When the program runs, it displays the following menu:

| Option | Operation |
|---:|---|
| 1 | Search using BST |
| 2 | Search using AVL Tree |
| 3 | Search using Hashing |
| 4 | Display BST traversals |
| 5 | Display AVL traversals |
| 6 | Display Hash Table |
| 7 | Insert a new student |
| 8 | Run performance experiment |
| 9 | Display all student records |
| 0 | Exit |

The BST and AVL Tree support inorder, preorder, and postorder traversals. The program also reports search comparisons/probes, tree heights, and hash-table insertion collisions.

## Data structure configuration

| Parameter | Value |
|---|---|
| Initial number of records | 30 |
| Student ID range | 2101–2130 |
| Maximum student capacity | 100 |
| Hash table size | 47 |
| Hash function | `h(id) = id % 10` |
| Collision handling | Linear Probing |
| Successful search key | 2115 |
| Unsuccessful search key | 2199 |

## Compile and run

A C compiler such as GCC is required.

**Linux / macOS / Windows terminal with GCC (MinGW):**

```bash
gcc -std=c99 -Wall -Wextra student.c -o student
./student
```

On Windows, run:

```bash
gcc -std=c99 -Wall -Wextra student.c -o student.exe
student.exe
```

## Performance experiment

The following values are produced by running option **8** with the initial 30-record dataset:

| Measurement | BST | AVL Tree | Hash Table |
|---|---:|---:|---:|
| Tree height (nodes) | 30 | 5 | Not applicable |
| Successful search (ID 2115) | 15 comparisons | 5 comparisons | 10 probes |
| Unsuccessful search (ID 2199) | 30 comparisons | 5 comparisons | 22 probes |
| Insertion collisions | Not applicable | Not applicable | 300 |

The results are specific to the supplied insertion order and hash function. Since the records are inserted in ascending Student ID order, the ordinary BST becomes right-skewed. The AVL Tree balances itself during insertion. Linear probing experiences clustering with the configured hash function.

## Repository structure

```text
algorithm-Battle/
├── student.c
├── README.md
├── report.docx
└── Screenshots/
    ├── avl_inorder_traversal.png
    ├── avl_postorder_traversal.png
    ├── avl_preorder_traversal.png
    ├── avl_successful_search_2115.png
    ├── avl_unsuccessful_search_2199.png
    ├── bst_inorder_traversal.png
    ├── bst_postorder_traversal.png
    ├── bst_preorder_traversal.png
    ├── bst_successful_search_2115.png
    ├── bst_unsuccessful_search_2199.png
    ├── dataset_after_insertion_2131.png
    ├── hash_successful_search_2115.png
    ├── hash_table_display.png
    ├── hash_unsuccessful_search_2199.png
    ├── initial_dataset_30_students.png
    ├── insert_student_2131.png
    └── performance_comparison.png
```

The PNG files are **terminal-style renders of actual program output**, captured by running the compiled `student.c` with the documented inputs. They are not photographs or direct captures of a VS Code terminal. The insertion demonstration adds ID 2131 (Suresh, CSE, 85) in a separate run; the performance comparison uses the original 30 records.

## GitHub repository

https://github.com/nperern/Algorithm_Battle.git

## Report

The project report is stored as `report.docx` in the repository.
