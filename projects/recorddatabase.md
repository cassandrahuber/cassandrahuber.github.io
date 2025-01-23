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
summary: "I developed a record database system for managing customer account information with features for adding, finding, printing, and deleting records in my ICS 212 course.."
---

Bank Record Database is a console-based application that I developed for managing customer account information in my ICS 212 course. The project helped me learn how to design and implement a data-driven system using C++ and file handling.

The Bank Record Database system allows users to add, find, print, and delete customer records. It uses a linked list data structure to store records, with each record containing an account number, name, and address. Additionally, the system reads and writes data from/to a file to ensure data persistence.

In this project, I gained experience with linked list data structures, file I/O, and basic debugging. I used C++ for both the client-side logic and the implementation of all required functions, including those for reading and writing to files, managing customer records, and handling input from the user.

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

You can learn more at the [UH Micromouse News Announcement](https://manoa.hawaii.edu/news/article.php?aId=2857).
