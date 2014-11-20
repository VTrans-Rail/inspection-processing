Switches Processing
=====================

Here are the steps I took to process the 2014 WACR M&B field inspection data for data entry into GIS

Start time: 8:30am

Other work: 10:00am
Lunch: 12:00


###Processing Word document "table"

Each asset inspected included a table in a Word document with basic information about all the assets inspected.

- Copy into Excel
- Change font and border, turn off word wrap, auto-fit columns to increase legibility
- Merge stacked cells and delete spare rows

|Rail|  
|----|
|Type|

Changes to

|Rail Type|
|---------|
|         |

- Delete the rows that appear at the top of each Word document page
- Replace each ditto mark " with the value at the top

|Town|
|:---:|
|Montpelier|
|"|
|"|
|"|

Changes to

|Town|
|:---:|
|Montpelier|
|Montpelier|
|Montpelier|
|Montpelier|

- Do this for `Town`, `VAL Page`, , `Update`, and `Inspection Date`  
- Re-order the fields to reflect the order they appear on the inspection sheet

#####Removed:
1. VAL Update - because all VAL sheets need updated (we don't have them)
2. GIS Symbol - because there are none for the M&B

#####Changed:


The new order:

6. Insp Date  
1. GPS  
2. Town  
3. VAL Sheet  
4. VAL Station  
5. MP  
7. Switch Name  
8. Rail Size/Type  
 
- Add some additional fields at the beginning
  
1. Inspector
2. VRLID
3. Orig Order
4. VAL Update

- VAL Sheet needs to be processed to be more useful

- Old: 2
- New: V.8a-2

- The mile post has a "M" prefix that has to be removed

- Old: M 0.70
- New: 0.70

- Create a numerical field called `Orig` to store the original order they appeared in the Word document

**Now bring this table into the Excel document

###Processing the Excel document

- Add columns for inspection sheet fields

1. Switch Type
2. Rail Condition
3. Turnout Type
4. Hand
5. Switch Point Length
6. Tie Condition
7. Frog Type
7. Frog Length
8. Frong condition
9. Switch stand
10. Guardrail Type
11. Signaled
12. Security
13. Number of Photos
14. Remedial action
9. Other Notes (Handwritten)
11. Data entry notes
12. DPR Hyperlink

- Add Validation columns

1. Word Doc
2. Photos (MP)
3. On Track Chart
4. Track Chart MP
4. Track Chart Type
5. Track Chart Hand
5. On VAL sheet
6. VAL sheet station
7. Horizontal Clearance

- Add QC results columns

1. Match Count
  - Formula: `=COUNTIF($AB2:$AJ2,"Y")`  
2. Mismatch Count
  - Formula: `=COUNTIF($AB2:$AJ2,"N")`  

[Write the data entry instructions documentation](https://github.com/VTrans-Rail/inspection-processing/blob/master/M%26B%20Switches%20Instructions.md)

Make a copy of a form

Highlight on the form which fields will have to be entered

Do the data entry on 3 forms to check the process for completion

Finish: 2:15pm (3.25 hours total)
