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
|2 |**Declaring the path of commands in variable** |I declared the path of commands in variables in the configuration file which i used in the script  |Path of command should be declare in the variable |**PASS** |
|3 |**DOWNLOADING THE GOOGLE SPREAD SHEETS IN CSV FORMAT** |I used **$WGET** with url of the google spread sheet to download in csv format |Google spreadsheet in csv format should be downloaded |**PASS** |![proof](https://user-images.githubusercontent.com/82143446/115991630-07b0fc80-a5e7-11eb-993b-fa45d0ca8ab7.png)|
|4 |**RENAME THE DOWNLOADED FILE** |Renamed  files which was downloading through 3 test case to sheet1.csv and sheet2.csv by using **$MV (DOWNLADED FILES NAME) (NEW FIES NAMES)** |Files should be renamed|**PASS** |
|5 |**EXTRACT THE REQUIRED COLUMN** |I used AWK command to get the required column |Script should be run |**PASS**|
|6 |**DISPLAY THE OUTPUT using configuration file** |I used the source of connfiguration file in the script and run the script  |Script should be run and display the output |**PASS**| 
|7 |**Adding the column in the spreadsheet** |Add the column in the spreadsheet and gives the word to all students |Output should be updated |**PASS**|
|8 |**Adding the row in the spreadsheet** |Add the row in the spreadsheet and gives the word in all the columns |Output should be updated |**PASS**|
|8 |**If Column and Row Value Null** |after add column and row in spreadsheet my output effected if column and row value null |Output should be updated with ignoring the null value |**Fail**|
 
 </details>
 
 
 <details>
  <summary> Implementation </summary>
  
In this script, first of all I copied the spreadsheet link to csv link through web publish option.
After that I downloaded the link to the spreadsheet with the wget command and rename the download file with the mv command.
Then I got the required output from awk command.
  
  </details>
  
  
  <details>
  <summary> Explanation Of Implementation </summary>
  
In this script, first of all I copied the spreadsheet link to csv link through web publish option.
After that I downloaded the link to the spreadsheet with the wget command and rename the download file with the mv command.
Then I got the required output from awk command.
  
  </details>
  
  
  
  <details>
  <summary> Configuration File </summary>
  
 This is the main configuration file of script

Here the declaration of the path of commands which used in script.

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


# URLS used to download the google spread sheet in csv foormat
# URL1 for spread sheet1
# URL2 for spread sheet2

URL1=https://docs.google.com/spreadsheets/d/e/2PACX-1vS7d8UCm5qMNKz4PmFvQTSOcsmf-pVwmeNL88oAU51rdAup_GpnWC6ASrCLb4oD5grzS97Xbxf4uXiH/pub?output=csv

URL2=https://docs.google.com/spreadsheets/d/e/2PACX-1vQU2lDfo3k2-d-bKmY48JNMTrZ7jah4AmhKD1ED-i9WG5_R7WqAx6h8uKZR7VwIebUajDVYjDtcTQK4/pub?output=csv

# Option with url

option=-q

# Rename the downloaded file

OLDFILE=/home/prarvesh/assignment/pub?output=csv

NEWFILE=/home/prarvesh/assignment/sheet1.csv
OLDFILE1=/home/prarvesh/assignment/pub?output=csv
NEWFILE1=/home/prarvesh/assignment/sheet2.csv


# Here the column of the spread sheet

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

# Directory of datafile

DIR=/home/prarvesh
name=DATAFILE

# Log file of script

LOG=/home/prarvesh/script.log

minus=2


  
  </details>
  
 
  
 <details>
  <summary> Script </summary>
  
In this script, first of all I copied the spreadsheet link to csv link through web publish option.
After that I downloaded the link to the spreadsheet with the wget command and rename the download file with the mv command.
Then I got the required output from awk command.
  
  </details>
  
  
  
 <details>
  <summary> Log File </summary>
  
In this script, first of all I copied the spreadsheet link to csv link through web publish option.
After that I downloaded the link to the spreadsheet with the wget command and rename the download file with the mv command.
Then I got the required output from awk command.
  
  </details> 

    
