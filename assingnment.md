<h1 align="center">OBJECTIVE</h1>
* _Make a script to download the google spreadsheet in csv format by using link and extract the required output from the file in the format


|NAME|SUM|AVERAGE|
|:---:|:---:|:---:|
|XYZ |AA |BB|

<h1 align="center">TEST CASES</h1> 

|S.NO|Test Cases|Test Case Description|Expected Result|Test Status|Output|
|:----:|:-----:|:-----:|:-----:|:-----:|:----:|
|1 |**Published Url** |Spread sheet link published by using publish to web option from file of spreadsheet and select the .csv format |Url should be published|**PASS** |![web publishing](https://user-images.githubusercontent.com/82143446/115991250-4e9df280-a5e5-11eb-827e-d3c267165e33.png)|
|2 |**Declaring the path of commands in variable** |I declared the path of commands in variables in the configuration file which i used in the script  |Path of command should be declare in the variable |**PASS** |
|3 |**DOWNLOADING THE GOOGLE SPREAD SHEETS IN CSV FORMAT** |I used **$WGET** with url of the google spread sheet to download in csv format |Google spreadsheet in csv format should be downloaded |**PASS** |![proof](https://user-images.githubusercontent.com/82143446/115991630-07b0fc80-a5e7-11eb-993b-fa45d0ca8ab7.png)|
|4 |**RENAME THE DOWNLOADED FILE** |Renamed  files which was downloading through 3 test case to sheet1.csv and sheet2.csv by using **$MV (DOWNLADED FILES NAME) (NEW FIES NAMES)** |Files should be renamed|**PASS** |

|5 |**EXTRACT THE REQUIRED COLUMN** |I used AWK command to get the required column |Script should be run |**PASS**|
|6 |**DISPLAY THE OUTPUT** |I used cat command to display the output |Script should be run |**PASS**                
         
            

    
