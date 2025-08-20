# Assignment1-Concepts-of-Operating-Systems-Linux-Commands-
Name: Ankita Yatin Kher
Institute: CDAC Mumbai

Problem 1: Read the instructions carefully and answer accordingly. If you need to insert data, do that as well.
a) Navigate and List:

a. Start by navigating to your home directory and list its contents. Then, move into a
directory named "LinuxAssignment" if it exists; otherwise, create it.

cd                         //change directory

ls                         //list files and directories

mkdir LinuxAssignment     // create directory if it doesn’t exist


cd LinuxAssignment       // navigate into directory

File Management:

b) Inside the "LinuxAssignment" directory, create a new file named "file1.txt". Display its
contents
cd LinuxAssignment        // change directory 

touch file1.txt          //creates an empty file

cat > file1.txt         //open file for writing

cat file1.txt          //display file contents

c) Directory Management:

a. Create a new directory named "docs" inside the "LinuxAssignment" directory.
cd LinuxAssignment    // change directory

makdir docs         // make directory with name docs



d) Copy and Move Files:

a. Copy the "file1.txt" file into the "docs" directory and rename it to "file2.txt".
touch file1.txt    // create an empty file

echo "This is file1 content" > file1.txt  // Write the string "This is file1 content" into 'file1.txt'

cat file1.txt                            // Display the contents of 'file1.txt' to verify the content

cp file1.txt docs/file2.txt             //Copy 'file1.txt' to the 'docs' directory and rename it as 'file2.txt'

ls docs                                // List the contents of the 'docs' directory to verify the copy


e) Permissions and Ownership:

a. Change the permissions of "file2.txt" to allow read, write, and execute permissions for
the owner and only read permissions for others. Then, change the owner of "file2.txt" to
the current user.

cd docs               // Navigate to the 'docs' directory where 'file2.txt' is stored

chmod 744 file2.txt  // Change file permissions: Owner gets rwx, others get r

ls -l               //verify that the permissions have been changed correctly

ls -l file2.txt  // Check the file's permissions to ensure they are set as expected

-rwxr--r-- 1 cdac cdac 22 Aug 18 17:30 file2.txt  this will look like this 

sudo chown $USER file2.txt  // Change the owner to the current user

ls -l file2.txt  # Verify the ownership change

f) Final Checklist:

a. Finally, list the contents of the "LinuxAssignment" directory and the root directory to
ensure that all operations were performed correctly.

cd                        //Navigate to your home directory, where 'LinuxAssignment' is located

ls -l  /LinuxAssignment  //List detailed contents of the 'LinuxAssignment' directory

ls -l /                 //List detailed contents of the root directory

g)File Searching:

a. Search for all files with the extension ".txt" in the current directory and its subdirectories.
cd ~/LinuxAssignment  // Change to the directory where you want to search

find . -name "*.txt"  // Search for all files with the .txt extension starting from the current directory

o/p ./file.txt
  ./file1.txt
./docs/file2.txt

b. Display lines containing a specific word in a file (provide a file name and the specific
word to search).
cat file1.txt           // Display the contents of 'file1.txt' to verify its content

grep "Line" file1.txt  //Search for the word "Line" in 'file1.txt' and display the matching lines
o/p Line 1
    Line 2
    Line 3

h) System Information:

a. Display the current system date and time.
date   //showing date and time with this command


i) Networking:

a. Display the IP address of the system.

1)ipconfig      //Display network interface configuration
2)hostname -I  //Displays the IP address on Linux

b. Ping a remote server to check connectivity (provide a remote server address to ping).
ping -c 4 google.com  // Ping google.com and send 4 packets

j)File Compression:

a. Compress the "docs" directory into a zip file. 
zip -r docs.zip docs  // Compress the 'docs' directory into 'docs.zip'

zip                  // This is  used to create zip files.

-r                  // The recursive flag tells zip to include all files and subdirectories within the docs directory.

docs.zip           // The name of the output zip file which i give.

docs              // directory which we use for compressing

ls               // List the files to verify that docs.zip exists

b. Extract the contents of the zip file into a new directory.
mkdir  docs         // make directory 

unzip docs.zip -d extracted_docs  // Extract the contents of 'docs.zip' to 'extracted_docs'

unzip                             //extract files from a .zip archive

docs.zip                        // zip file you want to extract.

-d extracted_docs              //  This option specifies the directory where the contents of the zip file will be extracted

k) File Editing:

a. Open the "file1.txt" file in a text editor and add some text to it.
nano file1.txt            // Open 'file1.txt' in the nano text editor

nano                     //  This is a terminal-based text editor that is simple to use.

file1.txt               //  edit this file if you want.


b. Replace a specific word in the "file1.txt" file with another word (provide the original
word and the word to replace it with.
cat file1.txt                                // Display the contents of file1.txt
nano file.txt                               // Open file.txt in the nano text editor
sed -i 's/Line/Sentence/g' file1.txt       // Replace Line with Sentence in 'file1.txt'
cat file1.txt                            // Display the updated contents of 'file1.txt'


# Challenges Faced
1) While creating LinuxAssignment folder, I forgot to use mkdir -p and the system gave an error saying the directory already exists. Learned to avoid this by adding -p.
2) After creating file1.txt with touch, it was completely empty. At first, I ran cat file1.txt and saw nothing, then realized I needed to open it with nano and add some text.
3) For checking IP address, I used ifconfig but the command was not found. After searching, I discovered that newer Linux systems use ip addr, which solved the issue.
4) While setting permissions with chmod, I first tried chmod 777 and gave unnecessary permissions. Later, I corrected it to chmod 744 to follow the requirement.
5)While using nano editor, I accidentally replaced the whole file content and struggled with saving/exiting. After a few tries, I learned the proper shortcut (CTRL+O and CTRL+X).


Problem 2: Read the instructions carefully and answer accordingly. If there is any need to insert some data then do that as well.
a. Suppose you have a file named "data.txt" containing important information. Display the first 10 lines of this file to quickly glance at its contents using a comman

ls                               // list the file check for data.txt file
head data.txt                  //display the first command file

b. Now, to check the end of the file for any recent additions, display the last 5 lines of "data.txt" using another command
ls                         // check file
tail -n5 data.txt         //with this command you can display last five lines

c. In a file named "numbers.txt," there are a series of numbers. Display the first 15 lines of this file to analyze the initial data set.

touch numbers.txt                                                               // make a file 
echo -e "1\n2\n3\n4\n5\n6\n7\n8\n9\n10\n11\n12\n13\n14\n15\n16" > numbers.txt  // via echo comand you can add 1 to 15 lines in numbers.txt file
head -n 15 numbers.txt                                                         // you can see the save 15 command which you add  txt file


d. To focus on the last few numbers of the dataset, display the last 3 lines of "numbers.txt".
ls // check file

tail -n3 nubers.txt       // last 3 line display


e. Imagine you have a file named "input.txt" with text content. Use a command to translate all lowercase letters to uppercase in "input.txt" and save the modified text in a new file named "output.txt."

touch input.txt                                // create file 
vi input.txt                                  // use vi editor for add content
esc                                         // for exit
wq                                         // save and quit from editor 
cat                                      // display content which i add on input.txt file
tr 'a-z' 'A-Z' < input.txt > output.txt //  tr for use character translate 
'a-z'                                  // which letter you need to convert 
'A-Z'                                 //uppercase letters to convert to 
< input.txt                          // This takes the content from input.txt.
> output.txt                        // This saves the converted content into output.txt.



f. In a file named "duplicate.txt," there are several lines of text, some of which are   duplicates. Use a command to display only the unique lines from "duplicate.txt."


cd LinuxAssignment            // Navigate to the LinuxAssignment dir

touch duplicate.txt          //Create an empty file named duplicate.txt

Ankita is a unique girl      // add content
this is the duplicate data
this is the duplicate data
esc

wq // save and quit

sort duplicate.txt | uniq -u   // Sort the content of duplicate.txt and pipe it to uniq -u to display only unique lines that occur once

g. In a file named "fruit.txt," there is a list of fruits, but some fruits are repeated. Use a command to display each unique fruit along with the count of its occurrences in "fruit.txt."

touch frouit.txt            //create file

vi fruit.txt               // add content

sort fruit.txt | uniq -c // Use a command to display each unique fruit along with the count of its occurrences in "fruit.txt."




#Repository Contents
1) Assignment1_Solution.pdf → Detailed documentation with commands and outputs
2) README.md → challenges, and repository note
   


































