# Assignment1-Concepts-of-Operating-Systems-Linux-Commands-
Name: Ankita Yatin Kher
Institute: CDAC Mumbai

# Overview

This repository contains my solution for Assignment 1 of the Concepts of Operating Systems course.
The complete step-by-step solution is documented in the attached PDF file.
Focus areas of the assignment:
1) Directory navigation and listing
2) File and directory management
3) Copying and moving files
4) Permissions and ownership
5) File searching
6) System information and networking
7) File compression and extraction
8) File editing

# Challenges Faced
1) While creating LinuxAssignment folder, I forgot to use mkdir -p and the system gave an error saying the directory already exists. Learned to avoid this by adding -p.
2) After creating file1.txt with touch, it was completely empty. At first, I ran cat file1.txt and saw nothing, then realized I needed to open it with nano and add some text.
3) For checking IP address, I used ifconfig but the command was not found. After searching, I discovered that newer Linux systems use ip addr, which solved the issue.
4) While setting permissions with chmod, I first tried chmod 777 and gave unnecessary permissions. Later, I corrected it to chmod 744 to follow the requirement.
5)While using nano editor, I accidentally replaced the whole file content and struggled with saving/exiting. After a few tries, I learned the proper shortcut (CTRL+O and CTRL+X).

#Repository Contents
1) Assignment1_Solution.pdf → Detailed documentation with commands and outputs
2) README.md → Summary, challenges, and repository notes

