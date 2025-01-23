---
layout: project
type: project
image: img/records.png
title: "Bank Record Database"
date: 2024-11-23
published: true
labels:
  - C++
  - Data Structures
  - File Handling
summary: "I developed a record database system for managing customer account information with features for adding, finding, printing, and deleting records in my ICS 212 course."
---

Bank Record Database is a console-based application developed as part of my ICS 212 course. The project aimed to create a system that could manage customer account information using a linked list data structure. The system allowed users to perform operations such as adding, finding, printing, and deleting records, where each record consisted of a customer’s account number, name, and address. The application also included functionality to read and write records to a file, ensuring data persistence between sessions.

For this project, I was responsible for the design and implementation of the entire system. I developed the linked list data structure, wrote functions to manage customer records, and implemented file handling to save and retrieve records from a file. Additionally, I integrated debugging capabilities to make the development and testing process easier. The entire project was done individually, and I handled all aspects from coding to testing the application.

From this experience, I learned a lot about data structures, particularly linked lists, and how they can be applied to manage dynamic data in memory. I also gained valuable experience with file I/O in C++, which was crucial for ensuring that the records were stored and retrieved correctly. This project also helped me improve my problem-solving skills as I worked to implement features like handling user input and ensuring the application ran smoothly. Overall, it reinforced my understanding of how to build functional software from scratch and gave me a deeper understanding of C++ and its application in real-world scenarios.

Here is some example code that illustrates how I add a new record to the database:

```cpp
int llist::addRecord(int accountno, char name[], char address[])
{
    int return_val = 0;
    record *new_record = new record;
    record *current = start;
    record *prev = NULL;

    if (start == NULL || start->accountno > accountno)
    {
        start = new_record;
        new_record->accountno = accountno;
        strcpy(new_record->name, name);
        strcpy(new_record->address, address);
        new_record->next = current;
    }
    else
    {
        while (current != NULL && current->accountno < accountno)
        {
            prev = current;
            current = current->next;
        }
        if (current != NULL && accountno == current->accountno)
        {
            return_val = -1;  // Record already exists
        }
        else
        {
            prev->next = new_record;
            new_record->accountno = accountno;
            strcpy(new_record->name, name);
            strcpy(new_record->address, address);
            new_record->next = current;
        }
    }
    return return_val;
}
```
This code ensures that new records are added in a sorted order without duplicating existing account numbers.
