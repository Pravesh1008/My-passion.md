#!/bin/bash
# here we give the source of configuration file
source /home/prarvesh/assignment/script.conf
$ECHO "==================================================================================================================" > $DIR

$ECHO "Output of first sheet" >> $DIR

$ECHO "=================================================================================================================" >> $DIR

# wget is used with url to download the google spread sheet in csv format
$WGET $option $URL1
if [ $? = 0 ]      # if condition is true then print error in sheet otherwise go to the else
then
$ECHO "$(date) $PWD [wget command] download the csv file using wget command $WGET $option $URL1" >> "$LOG"  # storing logs in specified file

#mv command is used to rename the file
$MV $OLDFILE $NEWFILE 
$CP $NEWFILE $DIR1 
$ECHO "$(date) $PWD [mv command] It rename the downloaded file using mv command $MV $OLDFILE $NEWFILE" >> "$LOG" # storing logs in the specified file

# here for getting the exact column of Intern Name
# here $CAT is used to read the file... $GREP is used to extract the row of specific name and -i is used for case insensitive (specific name either in small letter or either in capital is extract by using -i )
# $TR is used to show the only commas
# $WC -c is used ko count the character 
# below command gives the total no commas in the row of  specific name


count=$($CAT $NEWFILE | $GREP -i $COLUMN1 | $AWK -F "$COLUMN13" '{print $1}' | $TR -cd , | $WC -c) 
$ECHO "$(date) $PWD [count commas] count the no of commas before the Intern name$count" >> "$LOG" #storing logs in the specified file


# add is used to add the 2 in the total no of commas

add=2
$ECHO "$(date) $PWD [add 2 in the previous result of commas] $add" >> "$LOG" #storing logs in the specified file
# plus is used to get the exact column no

plus=$((count+add))
$ECHO "$(date) $PWD [total commas for extract the intern name column ] $plus" >> "$LOG" #storing logs in the specified file
#==================================================================================================================================================== 

# here for getting the exact column of Average
# here $CAT is used to read the file... $GREP is used to extract the row of specific name and -i is used for case insensitive (specific name either in small letter or either in capital is extract by usiing -i )
# $TR is used to show the only commas
# $WC -c is used ko count the character 
# below comand gives the total no commas in the row of  specific name
 

count1=$($CAT $NEWFILE | $GREP -i $COLUMN2 | $AWK -F "$COLUMN2" '{print $1}'| $TR -cd , | $WC -c)
$ECHO "$(date) $PWD [count total no of commas before average column] $count1" >> "$LOG" #storing logs in the specified file
#add1 is used to add the 1 in the total no of commas

add1=1
$ECHO "$(date) $PWD [add 1 in the total no of commas before average column to get the exact average column] $count1" >> "$LOG" #storing logs in the specified file
# plus is used to get the exact column no

plus1=$((count1+add1))
$ECHO "$(date) $PWD [commas for extract the average column] $plus1" >> "$LOG" #storing logs in the specified file 
#====================================================================================================================================================

# sum  is used to store the value of total no of commas in row of specific name

sum=`$CAT $NEWFILE |$GREP -i $COLUMN3 | $TR -cd , | $WC -c`
$ECHO "$(date) $PWD [value of total no of commas in a row] $sum" >> "$LOG" #storing logs in the specified file
# total is used to store the value of total commas minus 2 commas

TOTAL=`expr $sum - $minus`

$ECHO "$(date) $PWD [give the required value of the number of commas] $TOTAL" >> "$LOG" #storing logs in the specified file
#=====================================================================================================================================================

# cat is used to read the file
# $TAIL -n+4 neglects the upper 4 lines of the file
# $AWK is used to extract the column and print the Name Sum and Average
# average1 extract  the value from the $c and name1 extract the value from the $f and m extract the value from the $TOTAL 

#$CAT $NEWFILE | $TAIL -n+4 | $AWK -F "," '{print "Name :  "$name1,  "\n" , "Sum :  "$average1*m,  "\n" , "Average :  "$average1,  "\n"}' name1=$plus average1=$plus1 m=$TOTAL
test1=`cat $NEWFILE|$TAIL -n+4|$AWK -F "," '{print "Name :",$name1, "\n", "Sum :",$average1*m, "\n", "Average :",$average1, "\n"}' name1=$plus average1=$plus1 m=$TOTAL`  
$ECHO "$test1" >> $DIR

$ECHO "$(date) $PWD"[output] successfully print the required output >> "$LOG" 
else
echo "Script has some error"
fi

$ECHO "=======================================================================================================================" >> $DIR

$ECHO "Output of second sheet" >> $DIR

$ECHO "=======================================================================================================================" >> $DIR


# wget is used with url to download the google spread sheet in csv format
$WGET $option $URL2

if [ $? = 0 ]
then
        
$ECHO "$(date) $PWD [wget command] download the csv file using wget command $WGET $option $URL2" >> "$LOG"  # storing logs in specified file
 

#mv command is used to rename the file
$MV $OLDFILE1 $NEWFILE1
$CP $NEWFILE1 $DIR1
$ECHO "$(date) $PWD [mv command] It rename the downloaded file using mv command $MV $OLDFILE1 $NEWFILE1" >> "$LOG" # storing logs in the specified file

# here for getting the exact column of Intern Name
# here $CAT is used to read the file... $GREP is used to extract the row of specific name and -i is used for case insensitive (specific name either in small letter or either in capital is extract by usiing -i )
# $TR is used to show the only commas
# $WC -c is used ko count the character 
# below command gives the total no commas in the row of  specific name


count2=$($CAT $NEWFILE1|$GREP -i $COLUMN1|$AWK -F "$COLUMN13" '{print $1}'|$TR -cd , | $WC -c)
$ECHO "$(date) $PWD [count commas] count the no of commas before the Intern name for sheet 2 $count2" >> "$LOG" #storing logs in the specified file

 

# add is used to add the 2 in the total no of commas
add2=2
$ECHO "$(date) $PWD [add 2 in the previous result of commas] $add2" >> "$LOG" #storing logs in the specified file


# plus is used to get the exact column no
plus2=$((count2+add2))
$ECHO "$(date) $PWD [total commas for extract the intern name column for sheet 2 ] $plus2" >> "$LOG" #storing logs in the specified file

#==================================================================================================================================================== 

# here for getting the exact column of Average
# here $CAT is used to read the file... $GREP is used to extract the row of specific name and -i is used for case insensitive (specific name either in small letter or either in capital is extract by usiing -i )
# $TR is used to show the only commas
# $WC -c is used ko count the character 
# below comand gives the total no commas in the row of  specific name


count3=$($CAT $NEWFILE1 | $GREP -i $COLUMN2 | $AWK -F "$COLUMN2" '{print $1}'| $TR -cd , | $WC -c)
$ECHO "$(date) $PWD [count total no of commas before average column for sheet 2] $count3" >> "$LOG" #storing logs in the specified file

#add1 is used to add the 1 in the total no of commas
add3=1
$ECHO "$(date) $PWD [add 1 in the total no of commas before average column to get the exact average column] $add3" >> "$LOG" #storing logs in the specified file

# plus is used to get the exact column no
plus3=$((count3+add3))
$ECHO "$(date) $PWD [commas for extract the average column for sheet 2] $plus3" >> "$LOG" #storing logs in the specified file
#====================================================================================================================================================

# sum  is used to store the value of total no of commas in row of specific name

sum1=`$CAT $NEWFILE1 |$GREP -i $COLUMN3 | $TR -cd , | $WC -c`
$ECHO "$(date) $PWD [value of total no of commas in a row for sheet 2] $sum1" >> "$LOG" #storing logs in the specified file

# total is used to store the value of total commas minus 2 commas
TOTAL1=`expr $sum1 - $minus`
$ECHO "$(date) $PWD [give the required value of the number of commas for sheet 2] $TOTAL1" >> "$LOG" #storing logs in the specified file
#=====================================================================================================================================================

# cat is used to read the file
# $TAIL -n+4 neglects the upper 4 lines of the file
# $AWK is used to extract the column and print the Name Sum and Average
# average1 extract  the value from the $c and name1 extract the value from the $f and m extract the value from the $TOTAL 

#$CAT $NEWFILE | $TAIL -n+4 | $AWK -F "," '{print "Name :  "$name1,  "\n" , "Sum :  "$average1*m,  "\n" , "Average :  "$average1,  "\n"}' name1=$plus average1=$plus1 m=$TOTAL

#$CAT $NEWFILE1|$TAIL -n+4|$AWK -F "," '{print "Name :",$name1, "\n", "Sum :",$average1*n, "\n", "Average :",$average1, "\n"}' name1=$plus2 average1=$plus3 n=$TOTAL1
test=`cat $NEWFILE1|$TAIL -n+4|$AWK -F "," '{print "Name :",$name1, "\n", "Sum :",$average1*n, "\n", "Average :",$average1, "\n"}' name1=$plus2 average1=$plus3 n=$TOTAL1`
$ECHO "$test" >> $DIR
$ECHO "$(date) $PWD"[output] successfully print the required output >> "$LOG"
$CAT $DIR
	else
	$ECHO "script has some problem"
fi
