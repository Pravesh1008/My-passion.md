# This is the main configuration file of script

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


# URLS used to download the google spread sheet in csv foormat
# URL1 for spread sheet1
# URL2 for spread sheet2

URL1=https://docs.google.com/spreadsheets/d/e/2PACX-1vS7d8UCm5qMNKz4PmFvQTSOcsmf-pVwmeNL88oAU51rdAup_GpnWC6ASrCLb4oD5grzS97Xbxf4uXiH/pub?output=csv

URL2=https://docs.google.com/spreadsheets/d/e/2PACX-1vQU2lDfo3k2-d-bKmY48JNMTrZ7jah4AmhKD1ED-i9WG5_R7WqAx6h8uKZR7VwIebUajDVYjDtcTQK4/pub?output=csv

# Option with wget

option=-q

# Rename the downloaded file for sheet 1

OLDFILE=/home/prarvesh/assignment/pub?output=csv
NEWFILE=/home/prarvesh/assignment/sheet1.csv

# Rename the downloaded file for sheet 2

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

DIR=/home/prarvesh/datafile


# Log file of script

LOG=/home/prarvesh/script.log

# set the required value to calculate the sum

minus=2
