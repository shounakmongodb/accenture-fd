|Functional Design Header|Col2|Col3|Col4|Col5|Col6|Col7|Col8|
|---|---|---|---|---|---|---|---|
|Tech Goods|FT.F.012P - Customer Account Letter|||||Version|1.00|
|Description|Customer Account Letter|||||||
|Category|Finance|Target Region|North America|Industry|Consumer Goods and Services|||
|Contributor|Shubham Banerjee|||Reviewer||||

|Industrialization Factors|Col2|Col3|Col4|Col5|Col6|Col7|Col8|Col9|Col10|Col11|Col12|
|---|---|---|---|---|---|---|---|---|---|---|---|
|RICEFW|||Forms|||Complexity|||Medium|||
|Reduction Factor||Analyze||06h|Design|18h|Build|10h||Test|06h|
|Credential|n/a|||||||||||

|Obligatory Requirements|Col2|Col3|Col4|
|---|---|---|---|
|SAP Version|S/4 Release 756|Support Package|Release 756. SP Level 0000|
|Dependent Tech Goods|These other technical goods are used by this one and must be installed before it Technical Goods necessary. Inform the Code and Title with a link to this technical good at Portal|||

|Last Change Description|Col2|Col3|Col4|
|---|---|---|---|
|Version|Modified in|Responsible|Modification|
|1.00|06.April.2023|Shubham Banerjee|Initial Creation|


![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-0-1.png)

Functional Design v1 00 1


-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-1-1.png)

# Table of Contents

### 1. Objective 3

1.1 Reason and Business Purposes 3

1.2 Product Objective 3

1.3 Assumptions 3

### 2. Solution 4

2.1 Process Flow 4

2.2 Process Inputs 5

2.2.1 Selection Screen 5

2.2.2 Input File Layout 5

2.2.3 External System Integration 6

2.3 Solution Detail 6

2.3.1 SHDB or BAPI Description 6

2.3.2 Screen Layout 6

2.3.3 Processing Type 7

2.4 Process Output 7

2.4.1 Report or Form Layout 7

2.4.2 Output File Layout 8

2.5 Error Handling 8

### 3. Product Configuration 9

3.1 Necessary SAP Standard Configuration 9

3.2 Technical Goods Configuration 9

### 4. Appendix 10

4.1 Translation 10

4.2 Reference Documents 10

### 5. Version Change Log 11

Functional Design v1 00 2


-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-2-1.png)

# 1. Objective

## 1.1 Reason and Business Purposes

The purpose of this functional design document is to define the form for Customer individual letter - free to define
letter via standard texts.
The text to be printed in the standard letter must be created in the required language using transaction SO10.
The standard letter can only be printed in one language for each report run. The customers must therefore be
selected accordingly, and the report started for each language required.

## 1.2 Product Objective

Customer Individual/Account Letter allows to print and choose different letter as long as the content is saved in
the SAP standard texts configuration. This form is a flexible report which can be used for different functions other
than payment advice, balance confirmation and account statement.

For individual letters, business can enter a user-defined text during the dialog. For standard letters, a text is
stored in the form or in a standard text, that can only be extended by certain variables but cannot be changed
interactively. Forms must be defined and activated in the system so that business can print the required letters.
The standard system provides a form you can copy and correspondingly adapt to business requirements. The
standard form F140_IND_TEXT_01 is used in the standard system for Customer individual letter. The creation of
individual letters and standard letters is not possible for one-time customers.

## 1.3 Assumptions

  - Supports English and French only.

  - Standard SAP Account statement will be leveraged – form F140_IND_TEXT_01

  - Standard Texts should be maintained defined before running the correspondence.

Functional Design v1 00 3


-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-3-2.png)

# 2. Solution

## 2.1 Process Flow

Functional Design v1 00 4


![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-3-0.png)

-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-4-1.png)

## 2.2 Process Inputs

Execute t-code F.65 fill the Below given details and execute to generate the Customer Account Letter Form:

� Customer Account

� Company Code

� Inside Output Control enter the Text Name,

� Text ID

� Language

� Correspondence values.

### 2.2.1 Selection Screen

Below is the SAP screen where the Correspondence Customer Account Letter Form can be triggered in F.66
Tcode.

Functional Design v1 00 5


-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-5-0.png)

### 2.2.2 Input File Layout

Not Applicable

### 2.2.3 External System Integration

Not Applicable.

## 2.3 Solution Detail

o An Adobe form Layout is developed as per the requirement.

o An Adobe form Layout is developed as per the requirement.

o In "SFP" T-Code we have created the Layout of Adobe Form ZAD_FI_ACLTRFM and Form Interface
ZAD_FI_ACCOUNTLETTERFORM_INT.

o We have used standard form “F140_IND_TEXT_01” to design the adobe form layout, created and added
the SO10 texts and modified it according to the provided template design.

o Adobe form to design the layout for Customer Account letter.

Functional Design v1 00 6


-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-6-2.png)

o Form Interface which required to declare variables, constants and global variables used within the form.

o Execute the (F.65), t-code, by giving the Customer Account and Company Code, Inside Output Control
enter the Text Name, Text ID, Language and Correspondence values and execute.

o Then t-code SP01 is executed by entering Created by, Created on and Client field values.

o The adobe form “Customer Account Letter” is printed with the desired customer details.

### 2.3.1 SHDB or BAPI Description

Not Applicable.

### 2.3.2 Screen Layout

This is the layout of F.65 (Customer Account Letter) after filling the necessary details.

### 2.3.3 Processing Type

It can be executed Online / Batch.

## 2.4 Process Output

### The form will be generated as a spool then sent to an available printer in the system. This form will be generated in DIN A4 portrait format, printed and/or mailed to the vendor. Document could be sent via e-mail or fax if required. The adobe form “Customer Account Letter” is printed with the desired customer
details.

### 2.4.1 Report or Form Layout

Functional Design v1 00 7


![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-6-0.png)

-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-7-3.png)

This is the form generated for Customer Account Letter after giving the necessary inputs in F.65 transaction.

Form generated in English.

Form generated in French.

### 2.4.2 Output File Layout

Functional Design v1 00 8


![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-7-0.png)

-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-8-0.png)

## 2.5 Error Handling

Standard error messages of t-code: F.65.

Functional Design v1 00 9


-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-9-1.png)

# 3. Product Configuration

## 3.1 Necessary SAP Standard Configuration

� Define Period Types for Customers (SPRO).

� Define Correspondence Type (OB77).

� Assign program to Correspondence type (OB78).

� Define Form Names for Correspondence Print (SPRO).

## 3.2 Technical Goods Configuration

Not Applicable.

Functional Design v1 00 10


-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-10-1.png)

# 4. Appendix

## 4.1 Translation

Not Applicable.

## 4.2 Reference Documents

Not applicable.

Functional Design v1 00 11


-----

![](outputFT.F.012P - Customer Account Letter - Functional Design - v1.00/FT.F.012P---Customer-Account-Letter---Functional-Design---v1.00.docx.pdf-11-1.png)

# 5. Version Change Log

**Version** **Modified in** **Responsible**

**1.00** 06-April-2023 Shubham Banerjee

Functional Design v1 00 12

|Version|Modified in|Responsible|Modification|
|---|---|---|---|
|1.00|06-April-2023|Shubham Banerjee|Initial Creation|


-----

