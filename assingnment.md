<h1 align="center">OBJECTIVE</h1>
* _Make a script to download the google spreadsheet in csv format by using link and extract the required output from the file in the format


|NAME|SUM|AVERAGE|
|:---:|:---:|:---:|
|XYZ |AA |BB|

<h1 align="center">TEST CASES</h1> 

|S.NO|Test Cases|Test Case Description|Expected Result|Test Status|Output|
|:----:|:-----:|:-----:|:-----:|:-----:|:----:|
1 |**WEB PUBLISHING** |Spread sheet link published by using publish to web option from file of spreadsheet and select the .csv format |Spreadsheet should be published|**PASS** |![web publishing](https://user-images.githubusercontent.com/82143446/115991250-4e9df280-a5e5-11eb-827e-d3c267165e33.png)|
|1 |**Declaring the path of commands in variable** |I declared the path of commands in variable which i used in the script and i ran the script by using **$variable name** |Script should be run |**PASS** |
|2 |**DOWNLOADING THE GOOGLE SPREAD SHEETS IN CSV FORMAT** |I used **$WGET** with url of the google spread sheet to download in csv format |Google spreadsheet in csv format should be downloaded |**PASS** |![proof](https://user-images.githubusercontent.com/82143446/115991630-07b0fc80-a5e7-11eb-993b-fa45d0ca8ab7.png)|
|1 |**RENAME THE DOWNLOADED FILE** |Renamed  files which was downloading through 3 test case to my.csv and second.csv by using **$MV (DOWNLADED FILES NAME) (NEW FIES NAMES)** |Files should be renamed|**PASS** |

                  
         
            

    
