# Document History

## 1.1 Standard Information
The project is intended for the purpose of sending Payment Advice to suppliers/vendors in a specific format via email. The primary objective is to inform the supplier/vendor that their invoices have been paid, easing the process of matching invoices and payments. This document outlines the functional design for generating and sending Payment Advice using SAP ERP.

## 1.2 Change History
| Ver. | Date       | Summary Of Changes | Author              | Transport Number |
|------|------------|--------------------|---------------------|------------------|
| 1.00 | 27.MAR.2023| Draft Version      | Abhishek Kulkarni   | N/A              |

## 1.3 Approval Details
| Review No. | Date | Name Of Approver | Signature |
|------------|------|------------------|-----------|
| N/A        | N/A  | N/A              | N/A       |

## 1.4 Other Related Documents
Relevant documentation includes the following:
1. Vendor Master Data: Contains vendor contact details and email addresses.
2. SAP Configuration Guide: Details the setup for email communication in SAP.
3. Payment Process Documentation: Describes the end-to-end process of payment execution and advice generation.

## 1.5 RASCI
| Rasci Role | Name | Contact |
|------------|------|---------|
| Responsible| Abhishek Kulkarni | [Contact Info] |
| Accountable| [Name] | [Contact Info] |
| Support    | [Name] | [Contact Info] |
| Consulted  | [Name] | [Contact Info] |
| Informed   | [Name] | [Contact Info] |

-----

# Functional Overview

## 2.1 Functional Summary
The system is designed to generate and send Payment Advice to vendors/suppliers via email. The Payment Advice serves as proof of payment and assists in reconciling invoices with payments. The process involves executing payment runs in SAP, generating the Payment Advice in PDF format, and emailing it to the vendor's address stored in the Vendor Master data.

## 2.2 Functional Requirements

- The system must execute payment runs using transactions F110 and FBZ5.
- Payment Advice must be generated in PDF format and sent via email.
- The email should be sent to the vendor's email address as maintained in the Vendor Master data.
- If the vendor's email is not available, the Payment Advice should be generated as a spool.
- The system should log email sending status for traceability.

## 2.3 Reason and Business Purposes
The Payment Advice is required to provide vendors with confirmation of payment, facilitating the reconciliation of invoices and payments. It serves as a proof of payment and enhances the efficiency of the accounts payable process.

## 2.4 In/Out of Scope

- In Scope:
  - Generating Payment Advice in PDF format.
  - Sending Payment Advice via email to vendors.
  - Logging email status for traceability.

- Out of Scope:
  - Integration with third-party email systems.
  - Real-time payment processing.

## 2.5 Assumptions

- Vendor email addresses are correctly maintained in the Vendor Master data.
- The SAP system is configured to send emails.
- Users have the necessary permissions to execute payment runs and generate Payment Advice.

-----

## 2.6 Dependencies and Constraints
| Dependency | Constraint | Impact | Mitigation | Owner | Status |
|------------|------------|--------|------------|-------|--------|
| Vendor Master Data | Accurate email addresses | Email delivery | Regular data audits | [Owner] | Active |

## 2.7 Risks & Issues

**2.7.1 Risks**
| Risk Log Id | Description | Migration Plan |
|-------------|-------------|----------------|
| R001        | Incorrect email addresses | Regular audits and updates |

**2.7.2 Issues**
| Issue Log Id | Description | Remarks |
|--------------|-------------|---------|
| I001         | Email not sent | Check job log and retrigger |

# Functional Design

## 3.1 Functional Design Overview
The functional design involves generating Payment Advice for processed payments and sending them to vendors via email. The design ensures that the Payment Advice is generated in the required format and sent to the correct email address, with logging for traceability.

## 3.2 Existing process
The current process involves executing payment runs in SAP, generating Payment Advice, and manually sending it to vendors. The new design automates the email sending process, reducing manual effort and errors.

## 3.3 Sub Process Flow and Activity
| Sub Process Flow Id | Description | Activity Id | Description |
|---------------------|-------------|-------------|-------------|
| SP001               | Payment Run Execution | A001 | Execute F110 |

## 3.4 Necessary SAP Standard Configuration

- Configure email settings in SAP.
- Set up user roles for executing payment runs.

-----

## 3.5 Define Use Case or test case
| Use Case | Test Case | Test Scenario | Process Hierarchy |
|----------|-----------|---------------|-------------------|
| UC001    | TC001     | Email Sending | Payment Process   |

## 3.6 Detailed Requirement
The system must support the generation and emailing of Payment Advice. Detailed requirements include:

- Generate Payment Advice in PDF format.
- Send email to vendor's address from Vendor Master data.
- Log email status for traceability.

## 3.6.1 Initiating/Triggering Process

- User executes payment run in SAP.
- System generates Payment Advice.
- System sends email to vendor.

## 3.6.2 Detailed field mapping
| Legacy Field | SAP Field | SAP Name | Table-Field | Field Length | Type | Mapping Logic |
|--------------|-----------|----------|-------------|--------------|------|---------------|
| N/A          | ADRC-INTAD| Email    | Vendor Master| 50           | CHAR | Direct Mapping|

## 3.6.3 Input files/data samples
| Input File / Data Sample Name | File Attachment / Link |
|-------------------------------|------------------------|
| Vendor Master Data            | [Link]                 |

## 3.6.4 Error Handling
| Error Code | Description | Type Of Error | Resolution |
|------------|-------------|---------------|------------|
| E001       | Email not sent | System Error | Check job log |

-----

## 3.6.5 Custom Tables
No custom tables are required for this process.

## 3.7 Report Input Specification
The input for the Payment Advice includes data from the executed payment run, such as vendor details, payment amount, and invoice references.

## 3.8 Report Output Specification
| Report Fields | Data Type | Format | Frequency | Remarks |
|---------------|-----------|--------|-----------|---------|
| Payment Advice| PDF       | Email  | On Payment Run | N/A   |

## 3.9 Other Considerations

- Ensure data privacy by securing email communications.
- Provide user training for executing payment runs and handling errors.

**3.9.1 Selection Screen**

- Not Applicable.

**3.9.2 Frequency and Timing**

- Payment Advice is generated and sent upon successful payment run execution.

**3.9.3 Batch job details**
Batch jobs are not applicable as the process is triggered by user action.

**3.9.4 Transaction volumes**

- Expected daily processing of payment advices based on payment runs.

-----

**3.9.5 Security requirements**

- Secure email communication.
- Role-based access control for payment run execution.

**3.9.6 Language and translation requirements**

- Support for multiple languages based on vendor master data.

**3.9.7 Performance considerations**

- Ensure timely generation and sending of Payment Advice.

**3.9.8 Non-functional requirements**

- System uptime to ensure availability of payment processing.

# Fiori Functional

## 4.1 Screen and Logic Design
Not Applicable.

## 4.2 Embedded analytics Reporting Specification
Not Applicable.

# Testing

## 5.1 Unit Test
| Test No | Test Case / Scenario | Test Data | Expected Result | Object Developed / Functionality |
|---------|----------------------|-----------|-----------------|----------------------------------|
| T001    | Email Sending        | [Sample Data] | Email Sent | Payment Advice Generation |

# Appendix

## 6.1 Glossary of Terms

- SAP: Systems, Applications, and Products.
- AP: Accounts Payable.

## 6.2 Additional Supporting/Reference Documentation

- SAP Configuration Guide.
- Vendor Master Data Documentation.

-----