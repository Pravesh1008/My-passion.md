<h1 align="center">OBJECTIVE</h1>

Make a script to download the google spreadsheet in csv format by using link and extract the required output from the file in the format

Name    : 

Sum     :

Average :




<details>
  <summary> Test Cases </summary>

|S.NO|Test Cases|Test Case Description|Expected Result|Test Status|Output|
|:----:|:-----:|:-----:|:-----:|:-----:|:----:|
|1 |**Published Url** |Spread sheet link published by using publish to web option from file of spreadsheet and select the .csv format |Url should be published|**PASS** |![web publishing](https://user-images.githubusercontent.com/82143446/115991250-4e9df280-a5e5-11eb-827e-d3c267165e33.png)|
|2 |**Declaring the path of commands in variable** |I declared the path of commands in variables in the configuration file which i used in the script  |Path of command should be declare in the variable |**PASS** |![variable](https://user-images.githubusercontent.com/82143446/116283206-3e367500-a7a9-11eb-9c8f-11058d759b37.png)|
|3 |**DOWNLOADING THE GOOGLE SPREAD SHEETS IN CSV FORMAT** |wget -q url|I used **$WGET** with url of the google spread sheet to download in csv format |Google spreadsheet in csv format should be downloaded |**PASS** |![proof](https://user-images.githubusercontent.com/82143446/115991630-07b0fc80-a5e7-11eb-993b-fa45d0ca8ab7.png)|
|4 |**RENAME THE DOWNLOADED FILE** |Renamed  files which was downloading through 3 test case to sheet1.csv and sheet2.csv by using **$MV (DOWNLADED FILES NAME) (NEW FIES NAMES)** |Files should be renamed|**PASS** |output|
|6 |**DISPLAY THE OUTPUT using configuration file** |I used the source of configuration file in the script and run the script  |Script should be run and display the output |**PASS** |output| 
|7 |**Adding the column in the spreadsheet** |Add the column in the spreadsheet and gives the word to all students |Output should be updated |**PASS** |output|
|8 |**Adding the row in the spreadsheet** |Add the row in the spreadsheet and gives the word in all the columns |Output should be updated |**PASS** |output|
|9 |**If Column and Row Value Null** |after add column and row in spreadsheet my output effected if column and row value null |Output should be updated with ignoring the null value |**Fail** |output|
|10 |**log file** |when script run all logs genrate in log file |log should be genrated successfully in log file |**pass** |![log](https://user-images.githubusercontent.com/82143446/116284029-3f1bd680-a7aa-11eb-8c85-fbadf7400252.png)|
 
 </details>
 
 
 <details>
  <summary> Configuration File </summary>
<h2 align="center">This is Configuration file.</h2>  
This is the main configuration file of script

##Here the declaration of the path of commands which used in script.

ECHO=/usr/bin/echo

WGET=/usr/bin/wget

MV=/usr/bin/mv

CAT=/usr/bin/cat

AWK=/usr/bin/awk

TAIL=/usr/bin/tail

TR=/usr/bin/tr

RM=/usr/bin/rm

MKDIR=/usr/bin/mkdir

GREP=/usr/bin/grep

WC=/usr/bin/wc

#URLS used to download the google spread sheet in csv foormat

#URL1 for spread sheet1

#URL2 for spread sheet2

URL1=https://docs.google.com/spreadsheets/d/e/2PACX-1vS7d8UCm5qMNKz4PmFvQTSOcsmf-pVwmeNL88oAU51rdAup_GpnWC6ASrCLb4oD5grzS97Xbxf4uXiH/pub?output=csv

URL2=https://docs.google.com/spreadsheets/d/e/2PACX-1vQU2lDfo3k2-d-bKmY48JNMTrZ7jah4AmhKD1ED-i9WG5_R7WqAx6h8uKZR7VwIebUajDVYjDtcTQK4/pub?output=csv

#Option with wget

option=-q

#Rename the downloaded file for sheet 1

OLDFILE=/home/prarvesh/assignment/pub?output=csv

NEWFILE=/home/prarvesh/assignment/sheet1.csv

#Rename the downloaded file for sheet 2

OLDFILE1=/home/prarvesh/assignment/pub?output=csv

NEWFILE1=/home/prarvesh/assignment/sheet2.csv


#Here the column of the spread sheet

COLUMN1=name

COLUMN2=Average

COLUMN3=punctuality

#COLUMN4=Time management

#COLUMN5=Attendance

#COLUMN6=Communication

#COLUMN7=Requirement analysis

#COLUMN8=Self Learning

#COLUMN9=Grammatical error

#COLUMN10=Creativity

#COLUMN11=Grammatical error

#COLUMN12=S.NO

COLUMN13=Intern Name

#Directory of datafile

DIR=/home/prarvesh/datafile

#Log file of script

LOG=/home/prarvesh/script.log

#set the required value to calculate the sum

minus=2

  
  </details>
  
 
  
 <details>
  <summary> Script </summary>
<h2 align="center">This is Script file.</h2>  
#!/bin/bash

#here we give the source of configuration file

source /home/prarvesh/assignment/script.conf

$ECHO "=================================="

$ECHO "Output of first sheet"

$ECHO "=================================="

#wget is used with url to download the google spread sheet in csv format

if [ $URL1 = $0 ]      # if condition is true then print error in sheet otherwise go to the else

then

$ECHO "Error in sheet1"  

else

$WGET $option $URL1
 
$ECHO "$(date) $PWD [wget command] download the csv file using wget command $WGET $option $URL1" >> "$LOG"  # storing logs in specified file

#$ECHO "successfully downloded" 


#mv command is used to rename the file

$MV $OLDFILE $NEWFILE  

$ECHO "$(date) $PWD [mv command] It rename the downloaded file using mv command $MV $OLDFILE $NEWFILE" >> "$LOG" # storing logs in the specified file

#here for getting the exact column of Intern Name

#here $CAT is used to read the file... $GREP is used to extract the row of specific name and -i is used for case insensitive (specific name either in small letter or either in capital is extract by usiing -i )

#$TR is used to show the only commas

#$WC -c is used ko count the character 

#below command gives the total no commas in the row of  specific name

count=$($CAT $NEWFILE | $GREP -i $COLUMN1 | $AWK -F "$COLUMN13" '{print $1}' | $TR -cd , | $WC -c) 

$ECHO "$(date) $PWD [count commas] count the no of commas before the Intern name$count" >> "$LOG" #storing logs in the specified file

#add is used to add the 2 in the total no of commas

add=2

$ECHO "$(date) $PWD [add 2 in the previous result of commas] $add" >> "$LOG" #storing logs in the specified file

#plus is used to get the exact column no

plus=$((count+add))

$ECHO "$(date) $PWD [total commas for extract the intern name column ] $plus" >> "$LOG" #storing logs in the specified file
#=============================================================================== 

#here for getting the exact column of Average

#here $CAT is used to read the file... $GREP is used to extract the row of specific name and -i is used for case insensitive (specific name either in small letter or either in capital is extract by usiing -i )

#$TR is used to show the only commas

#$WC -c is used ko count the character 

#below comand gives the total no commas in the row of  specific name
 
count1=$($CAT $NEWFILE | $GREP -i $COLUMN2 | $AWK -F "$COLUMN2" '{print $1}'| $TR -cd , | $WC -c)

$ECHO "$(date) $PWD [count total no of commas before average column] $count1" >> "$LOG" #storing logs in the specified file

#add1 is used to add the 1 in the total no of commas

add1=1

$ECHO "$(date) $PWD [add 1 in the total no of commas before average column to get the exact average column] $count1" >> "$LOG" #storing logs in the specified file

#plus is used to get the exact column no

plus1=$((count1+add1))

$ECHO "$(date) $PWD [commas for extract the average column] $plus1" >> "$LOG" #storing logs in the specified file 
#===========================================================================

#sum  is used to store the value of total no of commas in row of specific name

sum=`$CAT $NEWFILE |$GREP -i $COLUMN3 | $TR -cd , | $WC -c`

$ECHO "$(date) $PWD [value of total no of commas in a row] $sum" >> "$LOG" #storing logs in the specified file

#total is used to store the value of total commas minus 2 commas

TOTAL=`expr $sum - $minus`

$ECHO "$(date) $PWD [give the required value of the number of commas] $TOTAL" >> "$LOG" #storing logs in the specified file
#==================================================

#cat is used to read the file

#$TAIL -n+4 neglects the upper 4 lines of the file

#$AWK is used to extract the column and print the Name Sum and Average

#average1 extract  the value from the $c and name1 extract the value from the $f and m extract the value from the $TOTAL 

#$CAT $NEWFILE | $TAIL -n+4 | $AWK -F "," '{print "Name :  "$name1,  "\n" , "Sum :  "$average1*m,  "\n" , "Average :  "$average1,  "\n"}' name1=$plus average1=$plus1 m=$TOTAL

cat $NEWFILE|$TAIL -n+4|$AWK -F "," '{print "Name :",$name1, "\n", "Sum :",$average1*m, "\n", "Average :",$average1, "\n"}' name1=$plus average1=$plus1 m=$TOTAL  

$ECHO "$(date) $PWD"[output] successfully print the required output >> "$LOG" 

fi

$ECHO "=========================================="

$ECHO "Output of second sheet"

$ECHO "==========================================="

#wget is used with url to download the google spread sheet in csv format

if [ $URL2 = $0 ]

then

$ECHO "Error in sheet2"  # if condition is true then print error in sheet otherwise go to the else

else

$WGET $option $URL2

$ECHO "$(date) $PWD [wget command] download the csv file using wget command $WGET $option $URL2" >> "$LOG"  # storing logs in specified file

$ECHO "successfully downloded" 

#mv command is used to rename the file

$MV $OLDFILE1 $NEWFILE1

$ECHO "$(date) $PWD [mv command] It rename the downloaded file using mv command $MV $OLDFILE1 $NEWFILE1" >> "$LOG" # storing logs in the specified file

#here for getting the exact column of Intern Name

#here $CAT is used to read the file... $GREP is used to extract the row of specific name and -i is used for case insensitive (specific name either in small letter or either in capital is extract by usiing -i )

#$TR is used to show the only commas

#$WC -c is used ko count the character 

#below command gives the total no commas in the row of  specific name

count2=$($CAT $NEWFILE1|$GREP -i $COLUMN1|$AWK -F "$COLUMN13" '{print $1}'|$TR -cd , | $WC -c)

$ECHO "$(date) $PWD [count commas] count the no of commas before the Intern name for sheet 2 $count2" >> "$LOG" #storing logs in the specified file

#$ECHO "TOTAL NO OF COMMAS IN A ROW IS $count" 

#add is used to add the 2 in the total no of commas

add2=2

$ECHO "$(date) $PWD [add 2 in the previous result of commas] $add2" >> "$LOG" #storing logs in the specified file

#plus is used to get the exact column no

plus2=$((count2+add2))

$ECHO "$(date) $PWD [total commas for extract the intern name column for sheet 2 ] $plus2" >> "$LOG" #storing logs in the specified file

#=================================================== 

#here for getting the exact column of Average

#here $CAT is used to read the file... $GREP is used to extract the row of specific name and -i is used for case insensitive (specific name either in small letter or either in capital is extract by usiing -i )

#$TR is used to show the only commas

#$WC -c is used ko count the character 

#below comand gives the total no commas in the row of  specific name

count3=$($CAT $NEWFILE1 | $GREP -i $COLUMN2 | $AWK -F "$COLUMN2" '{print $1}'| $TR -cd , | $WC -c)

$ECHO "$(date) $PWD [count total no of commas before average column for sheet 2] $count3" >> "$LOG" #storing logs in the specified file

#add1 is used to add the 1 in the total no of commas

add3=1

$ECHO "$(date) $PWD [add 1 in the total no of commas before average column to get the exact average column] $add3" >> "$LOG" #storing logs in the specified file

#plus is used to get the exact column no

plus3=$((count3+add3))

$ECHO "$(date) $PWD [commas for extract the average column for sheet 2] $plus3" >> "$LOG" #storing logs in the specified file
#================================================

#sum  is used to store the value of total no of commas in row of specific name

sum1=`$CAT $NEWFILE1 |$GREP -i $COLUMN3 | $TR -cd , | $WC -c`

$ECHO "$(date) $PWD [value of total no of commas in a row for sheet 2] $sum1" >> "$LOG" #storing logs in the specified file

#total is used to store the value of total commas minus 2 commas

TOTAL1=`expr $sum1 - $minus`

$ECHO "$(date) $PWD [give the required value of the number of commas for sheet 2] $TOTAL1" >> "$LOG" #storing logs in the specified file
#===================================

#cat is used to read the file

#$TAIL -n+4 neglects the upper 4 lines of the file

#$AWK is used to extract the column and print the Name Sum and Average

#average1 extract  the value from the $c and name1 extract the value from the $f and m extract the value from the $TOTAL 

#$CAT $NEWFILE | $TAIL -n+4 | $AWK -F "," '{print "Name :  "$name1,  "\n" , "Sum :  "$average1*m,  "\n" , "Average :  "$average1,  "\n"}' name1=$plus average1=$plus1 m=$TOTAL

cat $NEWFILE1|$TAIL -n+4|$AWK -F "," '{print "Name :",$name1, "\n", "Sum :",$average1*n, "\n", "Average :",$average1, "\n"}' name1=$plus2 average1=$plus3 n=$TOTAL1

$ECHO "$(date) $PWD"[output] successfully print the required output >> "$LOG"

fi
  
 </details>
  
  
  
 <details>
  <summary> Log File </summary>
<h2 align="center">This is log file.</h2>

  Tue Apr 27 21:41:36 IST 2021 /home/prarvesh/assignment [wget command] download the csv file using wget command /usr/bin/wget -q https://docs.google.com/spreadsheets/d/e/2PACX-1vS7d8UCm5qMNKz4PmFvQTSOcsmf-pVwmeNL88oAU51rdAup_GpnWC6ASrCLb4oD5grzS97Xbxf4uXiH/pub?output=csv

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/prarvesh/assignment/pub?output=csv /home/prarvesh/assignment/sheet1.csv

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [count commas] count the no of commas before the Intern name0

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [add 2 in the previous result of commas] 2

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [total commas for extract the intern name column ] 2

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [count total no of commas before average column] 10

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [add 1 in the total no of commas before average column to get the exact average column] 10

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [commas for extract the average column] 11

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [value of total no of commas in a row] 10

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment [give the required value of the number of commas] 8

Tue Apr 27 21:41:37 IST 2021 /home/prarvesh/assignment[output] successfully print the required output

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [wget command] download the csv file using wget command /usr/bin/wget -q https://docs.google.com
/spreadsheets/d/e/2PACX-1vQU2lDfo3k2-d-bKmY48JNMTrZ7jah4AmhKD1ED-i9WG5_R7WqAx6h8uKZR7VwIebUajDVYjDtcTQK4/pub?output=csv

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [mv command] It rename the downloaded file using mv command /usr/bin/mv /home/prarvesh/assignment/pub?output=csv /home/prarvesh/assignment/sheet2.csv

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [count commas] count the no of commas before the Intern name for sheet 2 0

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [add 2 in the previous result of commas] 2

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [total commas for extract the intern name column for sheet 2 ] 2

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [count total no of commas before average column for sheet 2] 10

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [add 1 in the total no of commas before average column to get the exact average column] 1

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [commas for extract the average column for sheet 2] 11

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [value of total no of commas in a row for sheet 2] 10

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment [give the required value of the number of commas for sheet 2] 8

Tue Apr 27 21:41:39 IST 2021 /home/prarvesh/assignment[output] successfully print the required output

  
  </details> 

<details>
  <summary> Conclusion </summary>
  
  I would like to share my experience while doing this work. The given script is doing its job correctly.
  
  </details>
    
