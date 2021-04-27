<h1 align="center">OBJECTIVE</h1>
Make a script to download the google spreadsheet in csv format by using link and extract the required output from the file in the format
Name :
Sum :
Average :


<TEST CASES>
<h1 align="center">TEST CASES</h1> 

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
 <TEST CASES/>        
            

    
