---
layout: project
type: project
image: img/books.jpg
title: "Book Report Processor"
date: 2024-12-10
published: true
labels:
  - C
  - CSV Files
  - Linked Lists
summary: "A C program that consolidates student book report data from two CSV files and filters pending submissions."
---

The Book Report Processor is a C program designed to handle student book report assignments. It consolidates data from two CSV files—one containing student information and the other detailing book assignments and report submission statuses. The program then creates two output files: full_information.csv, which contains all student and assignment data, and pending_reports.csv, which filters out students who have not yet submitted their reports.

As the sole developer, I was responsible for designing and implementing the entire program. I wrote all the functions to read and process the input files, manage the linked list of student records, and output the final files. I ensured the program followed clean coding practices, including modular functions, error handling, and memory management.

Through this project, I gained valuable experience in working with file I/O, linked lists, and memory management in C. I learned how to process and manipulate CSV files, as well as how to manage dynamic memory effectively. The project also reinforced the importance of clean, maintainable code and the need for careful error handling when dealing with file operations and memory allocation.

Here is some example code of 'write_file' function to illustrate linked list usage and file handling:
```c
/* Writes linked list data to a specified CSV file. Used to write both .csv output files. */
int write_file(struct student *start, char filename[])
{
    FILE *outfile;
    int return_val;
    struct student *current;

    outfile = fopen(filename, "w");

    if (!outfile)
    {
        printf("Error!  File failed to open.\n");
        return_val = -1;
    }
    else
    {
        current = start;
        fprintf(outfile, "Student_ID,Last_Name,First_Name,Book_ID,Book_Title,Report_Submitted\n");

        while (current != NULL)
        {
            fprintf(outfile, "%d,%s,%s,%d,%s,%s\n",
                    current->Student_ID,
                    current->Last_Name,
                    current->First_Name,
                    current->Book_ID,
                    current->Book_Title,
                    current->Report_Submitted);

            current = current->next;
        }
        fclose(outfile);
        return_val = 0;
    }
    return return_val;
}
```
Link to my code: <a href="https://github.com/cassandrahuber/Book-Report-Processor"><i class="large github icon "></i>cassandrahuber/cassandrahuber-Book-Report-Processor</a>
