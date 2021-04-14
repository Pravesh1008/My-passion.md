# **Objective:-**
---------------
- **_Evaluate the self and other student's on the basis of their paerformance_**
- **_Create the evaluation sheet and give them rating in the words (Excellent,very good,good,satisfactory,fair and poor. Value of these words (5,4,3,2,1,0) for different points_**.
- **_find the average value of self and other's student by using formulae/logic_**.
- **_Apply the condition_**
------------------

# **How to write formulae**:-
```sh
=SUM(COUNTIF(C7:J7,"Excellent")*5,COUNTIF(C7:J7,"Very Good")*4,COUNTIF(C7:J7,"Good")*3,COUNTIF(C7:J7,"Satisfactory")*2,COUNTIF(C7:J7,"Fair")*1,COUNTIF(C7:J7,"Poor"))/COUNTA(C7:J7)
```
-------------

## **TEST CASES:-**



| **SNO.**| **Test Case**| **Test Case Description**| **Expected Result**| **Actual Result**|
| :---     | :---                   | :---         | ---  |  -----                |
|**1**|**Average Value** |**<ul><li>**Give the rating excellent for all points**</li><li>**Give the rating very good for all points**</li><li>**Give the rating good for a points**</li></ul>
**|**2013-2014** |**73%** |
|**2**|**Intermediate School** |**[C.B.S.E Board Delhi](http://cbseacademic.nic.in/)**|**2014-2015** |**73%** |
