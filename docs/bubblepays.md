# BubblePays Project Explanation

## 1. Project Overview

BubblePays is an innovative electronic card payment system designed
specifically for laundromats. It is an Australian-owned and operated
solution that helps modernise laundromat operations through a
centralised, cashless payment system.

BubblePays is more than a payment method. It also serves as a marketing
platform and a tool for customer engagement and business growth. It
helps laundromat owners manage transactions and use real-time data and
feedback to make informed operational decisions.

The platform serves multiple regions and supports organisations and
individuals who use laundromat services, including:

-   Hotels
-   Hostels
-   Hospitals
-   Other businesses and individuals

Customers use a BubblePays card to access laundromat services. The card
is associated with information such as the card ID, subscription
details, and user information.

## 2. How the BubblePays Service Works

1.  A customer uses their BubblePays card at a laundromat machine.
2.  The machine records the usage transaction.
3.  A transaction file containing machine and usage details is generated
    and sent to an FTP server.
4.  A scheduled process picks up the file for processing.
5.  The system extracts information such as machine ID, card ID, service
    ID, usage date, start time, end time, and job details.
6.  The file is validated to check whether it contains sufficient
    information.
7.  Valid consumption and usage information is saved in the system.
8.  The saved usage data is used as the basis for monthly billing.
9.  Monthly invoices are calculated using customer consumption, service
    type, usage duration, subscription or plan details, and applicable
    offers.
10. The generated billing information is forwarded to the pricing
    component/team for final processing.

## 3. BubblePays Billing System

The BubblePays billing system automates the processing of laundromat
usage transactions.

Whenever a customer swipes a card, the machine generates a transaction
file. The file captures important information about the transaction.

  Information   Description
  ------------- -----------------------------------------------------
  Card ID       Identifies the BubblePays card used
  Service ID    Identifies the laundromat service used
  Machine ID    Identifies the machine that processed the usage
  Usage date    Date on which the service was used
  Start time    Time when machine usage began
  End time      Time when machine usage ended
  Job status    Status of the machine transaction or processing job
  Job message   Additional information associated with the job

### 3.1 File Validation and Consumption Capture

The system processes the transaction file and checks whether the
required information is available. If the file contains sufficient
information, the system saves the consumption data and usage details.

The consumption information is used to determine how much of each
service a customer has used. Incomplete or invalid files should be
handled through the system's validation and exception-handling process.

### 3.2 Monthly Invoice Generation

Monthly invoices are generated based on the customer's recorded
consumption. Billing takes into account relevant information such as:

-   Services used
-   Usage duration
-   Customer subscription and plan details
-   Applicable offers or pricing rules

The resulting invoice information is then passed to the pricing
component/team for final processing.

## 4. File Processing and Invoice Workflow

The file-processing workflow connects laundromat machines with the
BubblePays billing system.

``` mermaid
flowchart TD
    A[Customer swipes BubblePays card] --> B[Laundromat machine records transaction]
    B --> C[Transaction file is generated]
    C --> D[File is sent to FTP server]
    D --> E[Scheduled job picks up file]
    E --> F[Read and extract transaction details]
    F --> G{Required information available?}
    G -- No --> H[Handle invalid or incomplete file]
    G -- Yes --> I[Save consumption and usage data]
    I --> J[Calculate monthly consumption]
    J --> K[Apply subscription, plan and offer rules]
    K --> L[Prepare monthly invoice information]
    L --> M[Send information to pricing component/team]
```

*This diagram represents the business workflow described for the
project. Exact implementation details, such as the scheduling interval
and the pricing component's interface, depend on the deployed system.*

## 5. My Role and Responsibilities

I worked on backend REST API development and was involved in the
following areas.

### 5.1 File Processing

-   Worked on processing transaction files received from laundromat
    machines through the FTP-based workflow.
-   Extracted transaction information, including card ID, service ID,
    machine ID, usage date, start time, end time, and job details.
-   Worked on validating transaction information before saving it.
-   Supported the storage of valid consumption and usage records.

### 5.2 Consumption Management

-   Worked on backend APIs used to manage consumption information.
-   Supported the storage and retrieval of customer usage data.
-   Used service and duration information as inputs to the billing
    process.

### 5.3 Monthly Invoice Generation

-   Worked on generating monthly invoice information based on recorded
    consumption.
-   Considered service type, usage duration, subscriptions, plans, and
    applicable offers in the billing workflow.
-   Supported forwarding the generated information to the pricing
    component/team for further processing.

### 5.4 REST API Development

-   Developed REST APIs for the project's backend microservices.
-   Worked on the file-processing and consumption-related modules.
-   Supported integration between transaction data, consumption records,
    and monthly billing.

## 6. Business Benefits

BubblePays is intended to help laundromat businesses move away from
cash-based operations and adopt a centralised electronic payment
solution.

Key benefits include:

-   **Cashless convenience:** Customers can use a BubblePays card
    instead of relying on cash.
-   **Centralised payments:** Payment and usage information can be
    managed through a central system.
-   **Operational visibility:** Transaction and usage data help
    businesses monitor operations.
-   **Automated billing:** Recorded consumption can be used to prepare
    monthly invoices.
-   **Customer engagement:** The platform can also support marketing and
    customer-engagement activities.
-   **Business growth:** Transaction information and operational
    feedback can help laundromat owners plan and improve their
    businesses.

BubblePays emphasises innovation, responsiveness to business needs, and
the importance of real-time data and feedback for planning and
operational control.

## 7. Project Summary

BubblePays is a centralised electronic card payment and billing solution
for laundromats. Customers use BubblePays cards to access services, and
laundromat machines generate transaction files containing card, machine,
service, and usage details.

The backend processes these files, validates the transaction
information, and stores valid consumption records. The consumption data
is then used to prepare monthly invoices based on service usage,
duration, subscriptions, plans, and applicable offers. The billing
information is subsequently sent to the pricing component/team for final
processing.

My contribution focused on backend REST API development,
transaction-file processing, consumption-data handling, and the monthly
invoice-generation workflow.

## 8. Short Explanation for Interviews

BubblePays is an Australian-owned electronic card payment and billing
platform designed specifically for laundromats. Customers use BubblePays
cards to access laundromat machines. Whenever a card is swiped and a
service is used, the machine generates a transaction file containing
details such as card ID, machine ID, service ID, usage date, start time,
end time, and job status.

The files are transferred to an FTP server and picked up by scheduled
processing jobs. The backend validates the files and stores the
consumption details when the required information is available. This
consumption data is then used to calculate monthly usage and prepare
invoices based on service type, duration, subscription plans, and
applicable offers. The invoice information is passed to the pricing
component for final processing.

I was involved in developing REST APIs for the backend microservices,
particularly the file-processing, consumption-management, and monthly
invoice-generation modules.
