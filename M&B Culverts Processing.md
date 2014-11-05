Culverts Processing
=====================

Here are the steps I took to process the 2014 WACR M&B field inspection data for data entry into GIS

Start time: 9:15am

Break: 10:15am

Back: 1:30

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

- Do this for `Town`, `VAL Page`, and `Inspection Date`  
- Split out the `WARNING DEVICE` column into `Signaled` and `Crossbucks`  
  - These are both Yes/No fields
  - Remove `WARNING DEVICE` column when done
- Re-order the fields to reflect the order they appear on the inspection sheet

#####Removed:
1. VAL Update - not noted on any sheet
2. Culvert # - not noted on any sheet

#####Changed:
1. Length - in word doc, but still needs typed in blue for some sheets
2. Insp Date - in word doc (blue to green)
3. VAL Station - in word doc (blue to green)

The new order:

1. GPS
2. Town
3. VAL Sheet
4. VAL Station
5. MP
6. Insp Date
7. Length
 
- Add some additional fields at the beginning
  
1. Inspector
2. VRLID

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

1. Culvert Type
2. Culvert Description
3. Height From Rail
4. Length
5. Width
6. Depth
7. Culvert Condition
7. Number of Photos
8. Remedial action
9. Additional Notes
9. Other Notes (Handwritten)
11. Data entry notes
12. DPR Hyperlink

- Add Validation columns

1. Word Doc
2. Photos
3. ~~On Track Chart~~ _No culverts on M&B track chart_  
4. ~~Track Chart Type~~
5. ~~On VAL sheet~~ _No culverts on VAL sheets_
6. ~~VAL sheet station~~
7. ~~Matches VAL type~~

- Add QC results columns

1. Match Count
  - Formula: `=COUNTIF($AB2:$AJ2,"Y")`  
2. Mismatch Count
  - Formula: `=COUNTIF($AB2:$AJ2,"N")`  

[Write the data entry instructions documentation](https://github.com/VTrans-Rail/inspection-processing/blob/master/M%26B%20Culverts%20Instructions.md)

Highlight on the form which fields will have to be entered

Do the data entry on 3 forms to check the process for completion

Finish: 3:00pm (3 hours total)
