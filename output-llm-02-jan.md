# Document History

## 1.1 Standard Information
The project is intended for the Chemicals industry, specifically under the CFO & Enterprise
Value function utilizing the SAP ERP Central Component module. The primary objective is to
generate a report to display AP documents processed through Open Text VIM, IC4S, and
other e-invoicing channels. It will categorize these documents based on whether they were
manually processed by a user or automatically posted by the system. The standard
operating procedures, baseline configurations, and guidelines relevant to this SAP module
and process are to be followed in the creation and execution of this Functional Design.

## 1.2 Change History
| Ver. | Date       | Summary Of Changes | Author             | Transport Number |
|------|------------|--------------------|--------------------|------------------|
| 1.00 | 27.MAR.2023| Draft Version      | Abhishek Kulkarni  |                  |

## 1.3 Approval Details
| Review No. | Date | Name Of Approver | Signature |
|------------|------|------------------|-----------|
|            |      |                  |           |

## 1.4 Other Related Documents
Relevant documentation includes the following:
1. Project Charter Document: Provides an overview and scope of the project.
2. User Manual: Describes the user interface and provides guidance on how to interact with
the report.
3. Technical Specifications: Contains technical details and system architecture relevant to
the SAP configuration.
4. Business Process Document: Details the business processes involved in the handling of AP
documents through various channels.

## 1.5 RASCI
| Rasci Role | Name | Contact |
|------------|------|---------|
|            |      |         |

-----

# Functional Overview

## 2.1 Functional Summary
The system meets all functional requirements to generate a comprehensive report for AP
documents processed through various channels, including Open Text VIM, IC4S, and other
e-invoicing systems. Key functionalities of the report include categorization of documents
based on manual or automatic processing, and display of overall counts for Automatically
Posted, Manually Posted, Not Posted, and Rejected documents.

## 2.2 Functional Requirements

- The system must capture AP documents from sources such as Open Text VIM, IC4S, and
other e-invoicing channels.

- The report must categorize documents based on whether they were manually processed
by a user or automatically posted by the system.

- The report must display the overall count of documents categorized as Automatically
Posted, Manually Posted, Not Posted, and Rejected.

- Users must be able to filter the report based on date range, document type, and
processing status.

- The report must be exportable in formats such as PDF and Excel.

## 2.3 Reason and Business Purposes
The report is required to gain visibility into the processing of AP documents and to ensure
compliance with financial regulations. By categorizing documents based on their processing
status, the accounting team can identify areas for process improvement and ensure the
accuracy of financial records. The capability to filter and export the report allows for better
analysis and reporting to management.

## 2.4 In/Out of Scope

- In Scope:

  - Capturing AP documents from Open Text VIM, IC4S, and other e-invoicing channels.

  - Categorizing documents based on manual or automatic processing.

  - Displaying counts for Automatically Posted, Manually Posted, Not Posted, and
Rejected documents.

- Out of Scope:

  - Integration with third-party financial systems.

  - Real-time processing of AP documents.

## 2.5 Assumptions

- A Payment advice is a notice of a payment to be made.  
- A Payment advice may cover one or more commercial trade transactions (and related financial
transactions), such as invoices, credit notes, debit notes, etc.  
- A Payment advice may include a cross reference to a Payment Order.  
- A single Payment advice may relate to both national and international settlements.  
- Each Payment advice shall be calculated in only one currency, even though the related transaction is
denominated in different currencies.  
- Each Payment advice shall relate to only one settlement date.  
- Either SAP User login language or vendor master communication language will derive the language in
which Remittance Form will be generated.  
- Client will ensure that a variant of the standard SAP program or custom program is created in the system
to conform to the Client format requirements.  

-----

- The SAP system and channels like Open Text VIM and IC4S are functioning correctly.

## 2.6 Dependencies and Constraints
| Dependency | Constraint | Impact | Mitigation | Owner | Status |
|------------|------------|--------|------------|-------|--------|
|            |            |        |            |       |        |

## 2.7 Risks & Issues

**2.7.1 Risks**
| Risk Log Id | Description | Migration Plan |
|-------------|-------------|----------------|
|             |             |                |

**2.7.2 Issues**
| Issue Log Id | Description | Remarks |
|--------------|-------------|---------|
|              |             |         |

# Functional Design

## 3.1 Functional Design Overview
The functional design involves creating a report for AP documents processed through Open
Text VIM, IC4S, and other e-invoicing channels. The design aims to categorize the documents
based on whether they were manually or automatically processed, and display counts for
Automatically Posted, Manually Posted, Not Posted, and Rejected documents. The design
ensures accuracy, user accessibility, and compliance with financial regulations.

## 3.2 Existing process
The current process for handling AP documents involves multiple channels such as Open
Text VIM and IC4S, with varying degrees of automation. These differences can lead to
inconsistencies and difficulties in tracking the processing status of documents. The existing
system lacks a consolidated report to categorize and count these documents, limiting the
ability to identify areas for improvement and ensure compliance.

## 3.3 Sub Process Flow and Activity
| Sub Process Flow Id | Description | Activity Id | Description |
|---------------------|-------------|-------------|-------------|
|                     |             |             |             |

## 3.4 Necessary SAP Standard Configuration

- Configure user roles and permissions.

- Set up data extraction from Open Text VIM and IC4S channels.

- Configure report generation and scheduling within SAP.

- Ensure proper data validation and consistency checks.

## 3.5 Define Use Case or test case
| Use Case | Test Case | Test Scenario | Process Hierarchy |
|----------|-----------|---------------|-------------------|
|          |           |               |                   |

## 3.6 Detailed Requirement
The system must support the extraction and categorization of AP documents from multiple
channels, including Open Text VIM and IC4S. The detailed requirements include:

- Categorize AP documents based on their processing status (Automatically Posted,
Manually Posted, Not Posted, and Rejected).

- Provide a user-friendly interface to filter and view the report based on date range,
document type, and processing status.

- Ensure the report can be exported to formats such as PDF and Excel for further analysis.

## 3.6.1 Initiating/Triggering Process

- User initiates a report request from the SAP interface.

- System extracts data from Open Text VIM and IC4S channels.

- System categorizes the extracted data based on processing status.

- System generates the report and displays it to the user.

## 3.6.2 Detailed field mapping
| Legacy Field | SAP Field | SAP Name | Table-Field | Field Length | Type | Mapping Logic |
|--------------|-----------|----------|-------------|--------------|------|---------------|
|              |           |          |             |              |      |               |

## 3.6.3 Input files/data samples
| Input File / Data Sample Name | File Attachment / Link |
|-------------------------------|-------------------------|
|                               |                         |

## 3.6.4 Error Handling
| Error Code | Description | Type Of Error | Resolution |
|------------|-------------|---------------|------------|
|            |             |               |            |

-----

## 3.6.5 Custom Tables
The project requires the creation of custom tables to store the extracted AP document data,
processing status, and user interaction logs. These custom tables ensure data integrity and
facilitate the categorization and reporting process.

## 3.7 Report Input Specification
The input for the report will include data extracts from Open Text VIM, IC4S, and other
e-invoicing channels. The data must be extracted daily and encompass all relevant document
fields, such as document ID, date, type, and processing status. Additional filters can be
applied based on user-selected criteria, such as date range and document type.

## 3.8 Report Output Specification
| Report Fields | Data Type | Format | Frequency | Remarks |
|---------------|-----------|--------|-----------|---------|
|               |           |        |           |         |

## 3.9 Other Considerations

- Ensure data privacy and security by implementing role-based access control.

- Provide comprehensive user training and support to facilitate report usage.

- Maintain system performance by optimizing the data extraction and report generation
process.

**3.9.1 Selection Screen**

- Date range picker to select the start and end date for the report.

- Dropdown to select document type (e.g., Invoice, Credit Memo).

- Checkboxes to filter by processing status (Automatically Posted, Manually Posted, Not
Posted, Rejected).

**3.9.2 Frequency and Timing**

- Daily data extraction at 12:00 AM.

- Report generation on-demand by the user.

- Scheduled batch jobs to update the report data every 24 hours.

**3.9.3 Batch job details**
The batch jobs required for the project include a daily data extraction job that runs at 12:00
AM, fetching data from Open Text VIM, IC4S, and other e-invoicing channels. Additionally,
scheduled batch jobs will update the report data every 24 hours to ensure the report reflects
the latest processing status of AP documents.

**3.9.4 Transaction volumes**

- Expected daily processing of approximately 2000 AP documents.

- Monthly transaction volume estimated at 60,000 AP documents.

- Peak load handling of up to 5000 AP documents in a single day.

-----

**3.9.5 Security requirements**

- Implement password encryption for user accounts.

- Enforce role-based access control to restrict report access.

- Conduct regular security audits to identify and mitigate vulnerabilities.

**3.9.6 Language and translation requirements**

- Support for English and local language (e.g., Spanish) in the report interface.

- Translate user interface elements and error messages.

- Provide multilingual help documentation and user guides.

**3.9.7 Performance considerations**

- Page load time should be under 2 seconds for the report interface.

- System should handle up to 100 concurrent users without performance degradation.

- Ensure optimized data extraction and report generation to minimize processing time.

**3.9.8 Non-functional requirements**

- System uptime of 99.9% to ensure availability of the report.

- Regular data backup and recovery procedures to prevent data loss.

- Compliance with industry standards and regulatory requirements.

# Fiori Functional

## 4.1 Screen and Logic Design
The design for the SAP Fiori application includes wireframes for different screens and their
respective logic. The screens are designed to capture user input and display data effectively,
providing a seamless user experience.

**4.1.1 Application wireframe screens**
The application screens include:

- 1. Dashboard Screen: Displays key metrics and quick links to various report sections.

- 2. Reports Screen: Allows users to generate and view reports based on selected criteria.

- 3. Filter Screen: Enables users to apply filters to narrow down the results in the reports.

**4.1.2 Screen and Field Elements logic/Mapping**
| Screen And Field Elements | Mapping Logic |
|---------------------------|---------------|
|                           |               |

**4.1.3 Controls, Actions, Buttons**
| Control/Action Buttons | Description | Logic |
|------------------------|-------------|-------|
|                        |             |       |

-----

## 4.2 Embedded analytics Reporting Specification

**4.2.1 Indicators/Dimensions**
The key performance indicators (KPIs) and dimensions for the analytics report include
document count, processing status, manual vs. automatic processing, and rejection rates.
These indicators provide insights into the efficiency and accuracy of the AP document
processing system, enabling better decision-making and process improvements.

**4.2.2 Selection Screen input filters**
| Filter Name | Description | Type |
|-------------|-------------|------|
|             |             |      |

**4.2.3 Row/Columns details**
The report will include rows for each AP document processed, with columns providing
details such as document ID, date, type, processing status (Automatically Posted, Manually
Posted, Not Posted, Rejected), and user information (if manually processed). This detailed
breakdown allows users to analyze the data at a granular level.

## 4.3 KPI, Filter Layer Data and Data extraction details
| KPI Layer Data | Filter Layer Data | Data Extraction |
|----------------|-------------------|-----------------|
|                |                   |                 |

# Testing

## 5.1 Unit Test
| Test No | Test Case / Scenario | Test Data | Expected Result | Object Developed / Functionality |
|---------|----------------------|-----------|-----------------|----------------------------------|
|         |                      |           |                 |                                  |

# Appendix

## 6.1 Glossary of Terms

- API: Application Programming Interface.

- SAP: Systems, Applications, and Products.

- ERP: Enterprise Resource Planning.

- AP: Accounts Payable.

- IC4S: Inbound Channel for SAP.

- VIM: Vendor Invoice Management.

## 6.2 Additional Supporting/Reference Documentation

- SAP Fiori Guidelines.

- User Experience Design Document.

- Technical Specification Document.

- Previous Project Documentation related to AP processing.

-----
