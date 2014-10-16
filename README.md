inspection-processing
=====================

Here are the steps I took to process the 2014 WACR M&B field inspection data for data entry into GIS

###Copying files

Copied 5 CD's of photos to my network drive (30 mins)

**Issues**

- Crossings Disk A contained a subfolder with duplicate files for crossing at MP 0 - 4 and Y 0
- Crossings Disk A & B both contained a folder with photos for MP 5
- There are 3 crossings which use a different MP series letter that I'm not sure how I'll locate using linear referencing

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

The new order:

1. GPS
2. Town
3. VAL Sheet
4. VAL Station
5. MP
6. Crossing Name
7. Crossing Type
8. DOT Number
9. Signaled
10. Crossbucks  
11. Rail Type  
 
- Add some additional fields 
  
1. Inspector
2. VRLID

- VAL Sheet needs to be processed to be more useful

- Old: 2
- New: V.8a-2

- The mile post has a "M" prefix that has to be removed

- Old: M 0.70
- New: 0.70

- VAL Update `X` should be replaced with `Yes`

- Create a numerical field called `Orig` to store the original order they appeared in the Word document

**Now bring this table into the Excel document

###Processing the Excel document

- Add columns for inspection sheet fields

1. Crossing Location
2. Road Surface
3. Flangeway
4. Overall Condition
5. Rail Condition
6. Line of Sight
7. Number of Photos
8. Remedial action
9. Other Notes (Handwritten)
10. Private DOT Number
11. Data entry notes
12. DPR Hyperlink

- Add Validation columns

1. Word Doc
2. Photos
3. On Track Chart
4. Track Chart Type
5. On VAL sheet
6. VAL sheet station
7. GIS symbol present
8. Match DOT number?

- Add QC results columns

1. Match Count
  - Formula: `=COUNTIF($AB2:$AJ2,"Y")`  
2. Mismatch Count
  - Formula: `=COUNTIF($AB2:$AJ2,"N")`  


