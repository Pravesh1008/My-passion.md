# **Objective:-**
---------------
- _Evaluate the self and other student's on the basis of their performance_.
- _Create the evaluation sheet and give them rating in the words (Excellent,very good,good,satisfactory,fair and poor. Value of these words (5,4,3,2,1,0) for different points_.
- _find the average value of self and other's student by using formulae/logic_.
- _Apply the condition_.
------------------

# **How to write formulae ?**
```sh
   The way of write the formulae according to the our  requirements what i want in the output.
   ````
```sh
    =SUM(COUNTIF(C7:J7,"Excellent")*5,COUNTIF(C7:J7,"Very Good")*4,COUNTIF(C7:J7,"Good")*3,COUNTIF(C7:J7,"Satisfactory")*2,COUNTIF(C7:J7,"Fair")*1,COUNTIF(C7:J7,"Poor")*0)/COUNTA(C7:J7)
```
-------------

# **How does the formulae work ?**
```diff
+ Formula is an expression that work on value in a specific range of cell.
+ In the formulae which i mentioned above it taking the value we have given to word and adding them and divided by the total no of column according to the range i set. 
```
---------------
## **TEST CASES:-**



| **SNO.**| **Test Case**| **Test Case Description**| **Expected Result**| **Actual Result**|
| :---    | :---:        |:---                   | :---:              |  :-----:         |
|1|Sum |I put the formaule in the  average column{=SUM(COUNTIF(C4:J4,"Excellent")*5, COUNTIF(C4:J4,"Very Good")*4,COUNTIF(C4:J4,"Good")*3,COUNTIF(C4:J4,"Satisfactory")*2,COUNTIF(C4:J4,"Fair")*1,COUNTIF(C4:J4,"Poor")) }| Expected output should be there|**PASSED** |
|2|Average Value |I put the formaule in the  average column{=SUM(COUNTIF(C4:J4,"Excellent")*5, COUNTIF(C4:J4,"Very Good")*4,COUNTIF(C4:J4,"Good")*3,COUNTIF(C4:J4,"Satisfactory")*2,COUNTIF(C4:J4,"Fair")*1,COUNTIF(C4:J4,"Poor"))/COUNTA | Expected average value should be there  |**FAILED** |
|3|Average Value |I modify the formaule in the  average column{=SUM(COUNTIF(C4:J4,"Excellent")*5, COUNTIF(C4:J4,"Very Good")*4,COUNTIF(C4:J4,"Good")*3,COUNTIF(C4:J4,"Satisfactory")*2,COUNTIF(C4:J4,"Fair")*1,COUNTIF(C4:J4,"Poor"))/COUNTA(C4:J4) | Expected average value should be there  |**PASSED** |




---------------


# **How it was implemented ?**
- Implemented rules:-
```sh

During implementation i used =SUM
During implementation i used COUNTIF
During implementation i used COUNTA
```
# **Explanation of implementation**:-
```sh
=SUM: The SUM function adds values. You can add individual values, cell references or ranges or a mix of all.
COUNTIF:COUNTIF is an Excel function to count cells in a range that meet a single condition. COUNTIF can be used to count cells that contain dates, numbers, and text. 
COOUNTA: The COUNTA function counts the number of cells that are not empty in a range.
```
# **Test Result**
```sh
The test ressult were successfull,when i changed in the sheet then it gives output according. to changes.
```
# **Conclusion**
```diff
+ I have completed the given task with the help of google.
```
```sh
Thankyou
Pravesh
```
