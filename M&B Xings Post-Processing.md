inspection-post-processing
=====================

Here are the steps I took to process the 2014 WACR M&B field inspection data for data entry into GIS

Start time: 11:25am

Lunch: 12-12:30

###Copying files

Initially moved the completed spreadsheet and MXD from the V:\ drive to the F:\ drive for processing

Copied the _done folder and renamed it _import

**Issues**

- There was a copy problem and Atchinson had to Save As the XLS. I renamed this to the original since it was the latest file

###Processing the Excel document

- Print out the completed spreadsheet to markup
- Unhide all columns
- Disable word wrap
- Auto-fit column width
- Begin scanning all columns to look for anomolies 
- Hyperlinks point to internal DPR link. Find/Replaced to public facing hyperlink

_Replaced 42_
` http://aotdpr/diphotowebstore/Rail_GradeXing_Inspection_Photos/documenttoc.asp?AID=Rail%5FGradeXing%5FInspection%5FPhotos&PID= `

with

` http://vtransmap01.aot.state.vt.us/rp/dpr/diphotowebstore//Rail_GradeXing_Inspection_Photos/documenttoc.asp?AID=Rail_GradeXing_Inspection_Photos&PID= `

**Issues**

- "Waiting on Photos" note: shouldn't have talked to Demers w/o permission  
- 53 QC questions not answered - replaced with "n"  
- 14 don't have a DPR hyperlink, 13 don't have DOT Num (OK). One missing DPR hyperlink (wating on photos for 900-600M)

**Save As CSV for GIS import**

## GIS import process

**Working in CSV now:**

- Migrate all DOT numbers to one column
- Make the column names identical to GMRC crossing inspection FC
- Re-sort the columns to match the GIS FC
- Match DOT Number not present in FC
- Duplicate DOT numbers will have to be "moved" for the sidings
- Check the DOT number list against GIS

**Match Problems**
- 18 don't match GIS to Frenchy
- 4 in GIS and not inspected
- 1: Didn't inspect first Xing - Montpelier Junction Rd
- 3: not inspected, but closed or questionable 
- 



**


Worked all the way until 5:30pm