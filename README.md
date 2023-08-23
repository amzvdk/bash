# <img src="https://camo.githubusercontent.com/8e07b66826c73417854e06eb5fbe60f6ad6da87a423a8a0bb8e9340e83f246b3/68747470733a2f2f75706c6f61642e77696b696d656469612e6f72672f77696b6970656469612f636f6d6d6f6e732f7468756d622f342f34622f426173685f4c6f676f5f436f6c6f7265642e7376672f3130323470782d426173685f4c6f676f5f436f6c6f7265642e7376672e706e673f3230313830373233303534333530"  width="40" height="40"> Bash 

As part of the course, I learned the fundamental commands for handling files and sections, as well as conducting HTTP requests

I'd like to present my solutions to the assignments I successfully completed during the course:
- [Working with files and directories](#task-1)
- [Editing files, checking and killing processes, sending requests](#task-2)









## Task 1
```
1. Open home directory
2. Determine the name of the folder you are in
             $pwd

3. Create a directory inside this folder called test1
              $ mkdir test1

4. Go to folder test1
             $ cd test1

5. Create file 1,2 and 3 inside test1 directory
              $ touch 1.txt 2.txt 3.txt


6. Check the contents of the directory test1
              $ls
1.txt 2.txt 3.txt

7. Go to your home directory
$cd..

8. Create folder test2 inside your home directory
$ mkdir test2

9. Delete folder test2
$ rmdir test2


10. Delete file 2 from folder test1
$ rm test1/2.txt


11. Create a folder in the test3 home directory and add two files to it
$ mkdir test3 && touch test3/4.txt test3/5.txt


12. Delete folder test3
$ rm -r test3

13. Create folder test4 in your home directory
$ mkdir test4

14. Move files 1 and 3 from folder test1 to folder test4
$ mv test1/1.txt test1/3.txt test4

15. Add to file 1 three lines with the words line
$ echo line >> test4/1.txt
$ echo line >> test4/1.txt
$ echo line >> test4/1.txt

16. View the contents of file 1
$ cat test4/1.txt
line
line
line

17. Add three lines to file 3 with the words line
$ echo line >> test4/3.txt
$ echo line >> test4/3.txt
$ echo line >> test4/3.txt

18. View the contents of two files (1 and 3) at once
$ cat test4/1.txt test4/3.txt
line
line
line
line
line
line

19. Using one of the editors, replace all lines in file 1
$ nano test4/1.txt

$ cat test4/1.txt
row
row
row
```

## Task 2

```
1. Go to your home directory

2. Create folder test 3
$ mkdir test3

3. Add three files 4, 5 and 6 to the test 3 folder, each of which should contain 4 lines row1, row2, row3, row4


$ echo "row1" > test3/4.txt
$ echo "row2" >> test3/4.txt
$ echo "row3" >> test3/4.txt
$ echo "row4" >> test3/4.txt

$ echo "row1" > test3/5.txt
$ echo "row2" >> test3/5.txt
$ echo "row3" >> test3/5.txt
$ echo "row4" >> test3/5.txt

$ echo "row1" > test3/6.txt
$ echo "row2" >> test3/6.txt
$ echo "row3" >> test3/6.txt
$ echo "row4" >> test3/6.txt

4. Find the line row2 in file 5
$ grep "row2" test3/5.txt
row2
5. Find the row row in the test3 folder
$ grep -r "row" test3
test3/4.txt:row1
test3/4.txt:row2
test3/4.txt:row3
test3/4.txt:row4
test3/5.txt:row1
test3/5.txt:row2
test3/5.txt:row3
test3/5.txt:row4
test3/6.txt:row1
test3/6.txt:row2
test3/6.txt:row3
test3/6.txt:row4

6. Count how many lines with row content in file 6
$ grep "row" test3/6.txt -c
4

7. Find file 5 inside test3 folder
$ find test3 -name "5.txt"
test3/5.txt

8. Using find command delete file 5
$ find test3 -name "5.txt" -delete

9. Using the echo command, add the word test to file 4
$ echo test >> test3/4.txt

10. Replace the word test in file 4 with fail
$ sed 's/test/fail/g' test3/4.txt -i

11. Add the word test to file 4 so that the contents are preserved
$ echo test >> test3/4.txt

12. View all processes for users, not only in the console, that occur in the system

$ ps aux
       PID PPID PGID WINPID TTY UID STIME COMMAND
      1490 1 1490 4716 cons0 197609 12:13:05 /usr/bin/bash
      1878 1490 1878 14768 cons0 197609 13:29:07 /usr/bin/ps$ ps aux
       PID PPID PGID WINPID TTY UID STIME COMMAND
      1490 1 1490 4716 cons0 197609 12:13:05 /usr/bin/bash
      1878 1490 1878 14768 cons0 197609 13:29:07 /usr/bin/ps

13. Kill process 666 in the console
$ kill 666

14. Find out the availability of the artsiomrusau.com resource using ping
$ ping artsiomrusau.com

Packet exchange with artsiomrusau.com [185.215.4.92] with 32 bytes of data:
Timed out request.
Timed out request.
Timed out request.
Timed out request.

Ping stats for 185.215.4.92:
     Packets: Sent = 4, Received = 0, Lost = 4
     (100% loss)

Windows as always does not want to work correctly :(

Other resources (google.com, for example) ping without problems :(

15. Send 5 packages to artsiomrusau.com
$ ping artsiomrusau.com -n 5

Packet exchange with artsiomrusau.com [185.215.4.92] with 32 bytes of data:
Timed out request.
Timed out request.
Timed out request.
Timed out request.
Timed out request.

Ping stats for 185.215.4.92:
    Packets: Sent = 5, Received = 0, Lost = 5
     (100% loss)

16. Using GET and curl command, get information about registered pets at https://petstore.swagger.io/
$ curl -X 'GET' \
> 'https://petstore.swagger.io/v2/store/inventory' \
> -H 'accept: application/json'
{"{{PetStatus-Updated}}":1,"sold":9,"string":496,"unavailable":4,"pending":3,"available":424,"peric":2}


17. Using POST and curl command, create a new user on https://petstore.swagger.io/

$ curl -X 'POST' \
> 'https://petstore.swagger.io/v2/user' \
> -H 'accept: application/json' \
> -H 'Content-Type: application/json' \
> -d '{
> "id": 265,
> "username": "Stone",
> "firstName": "Rock",
> "lastName": "Stones",
> "email": "test@mail.ru",
> "password": "35453555!",
> "phone": "84545468684",
> "userStatus": 1
>}'
```
