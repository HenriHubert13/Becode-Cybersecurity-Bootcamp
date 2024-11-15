# Text_Manipulation

- Search all sequences containing "Loxondota" in /home/student/lorem.txt

`grep "Loxondota" lorem.txt`

- Copy the file /etc/passwd to your home directory. Display the line starting with student name.

`cp /etc/passwd ~`

`grep "^student" ~passwd`

- Display the lines in the passwd file starting with login names of 3 or 4 characters.

`grep "^[a-zA-Z0-9]\{3,4\}:" /etc/passwd`

- In the file /home/student/sample.txt how many different values are there in the first column? in the second?

`cut -d "," -f 1 sample.txt | sort | uniq | wc -l`

- In the file /home/student/sample.txt sort the values in the second column by frequency of occurrence. (uniq -c can be useful)

`cut -d "," -f 2 sample.txt | sort | uniq -c`

- In the file /home/student/iris.data Change the column separator (comma) to tab (make sure that the changes are applied to the file)

`sed 's/,/\t/g' iris.data`

- In the file /home/student/iris.data, extract from this file the column 3 (petal length in cm) (use cut )

`cut -d "," -f 2 iris.data`

- In the file /home/student/iris.data, count the number of flower species (cut and uniq)

`sed '/^$/d' iris.data | cut -d "," -f 5 | uniq | wc -l`

-In the file /home/student/iris.data, sort by increasing petal length (see sort options)

`cut -d "," -f 3 iris.data | sort`

- In the file /home/student/iris.data, show only lines with petal length greater than the average size

`awk '{ sum += $3 ; av = sum / NR ; if ($3 > av) print }' iris.data`

- Using /etc/passwd, extract the user and home directory fields for all users on your student machine for which the shell is set to /bin/false.

`awk -F ':' ' $7 == "/bin/false" { print } ' /etc/passwd`
