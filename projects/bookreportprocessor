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

The Book Report Processor is a program written in C that consolidates student and book report assignment data from two CSV files into a new file. The program reads `students.csv` containing student details and `book_report_assignments.csv` containing book assignment and report submission status, then creates two output files: `full_information.csv` and `pending_reports.csv`.

In this project, I gained experience in handling CSV files, linked list manipulation, and memory management in C. I used clean coding practices, including modular functions, detailed comments, and memory cleanup. The program efficiently processes and organizes the data, allowing for easy access to both complete and pending book report assignments.

Here is some example code of 'write_file' function to illustrate linked list usage and file handling:
```c
/* Writes the linked list in heap space to a specified csv filename. Creates a table
 * with a header and each student's data that is in the list. */
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
