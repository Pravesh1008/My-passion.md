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
| :---:    | :---:        |:---                   | :---:              |  :-----:         |
|**1**|**Average Value** |**Give the rating excellent for all points**| **AVerage value should be 5** |**PASSED** |
|**2**|**Average Value** |**Give the rating Very Good for all points**| **AVerage value should be 4** |**PASSED** |
|**3**|**Average Value** |**Give the rating Good for all points**| **AVerage value should be 3** |**PASSED** |
|**4**|**Average Value** |**Give the rating Satisfactory for all points**| **AVerage value should be 2** |**PASSED** |
|**5**|**Average Value** |**Give the rating Fair for all points**| **AVerage value should be 1** |**PASSED** |
|**6**|**Average Value** |**Give the rating Poor for all points**| **AVerage value should be 0** |**PASSED** |
|**7**|**Average Value** |**Give the rating different word in all points**| **AVerage value should be there acc. to which point we have givenwichword**|**PASSED** |
|**8**|**Condition** |**Applied the condition when average value is less then 2.5 the colour will be red of the average column**| **colour should be red*|**PASSED** |
