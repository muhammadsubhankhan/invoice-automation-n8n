# Invoice Automation Workflow

## Overview

This n8n workflow automates the process of handling invoices and credit card statements. It monitors specific Google Drive folders for new files, processes them using AI, and organizes the data into Google Sheets while also managing email attachments.



![Screenshot from 2025-04-30 20-57-33](https://github.com/user-attachments/assets/b89bc84b-3ef1-4102-a684-352ed2251150)





## Features

-   Automated monitoring of Google Drive folders for new files
-   PDF text extraction and processing
-   AI-powered data parsing using OpenAI GPT-4
-   Automatic Google Sheets data entry
-   Gmail integration for invoice/transaction email monitoring
-   Automatic file organization in Google Drive
-   HTML to PDF conversion for email content

## Workflow Components

### 1. File Monitoring and Initial Processing

-   Google Drive Trigger watches for new files in specified folders
-   Downloads and processes new files for data extraction
-   Supports PDF file format

### 2. AI Processing

-   Uses OpenAI GPT-4 to extract structured data from documents
-   Specifically processes credit card statements and invoices
-   Converts unstructured text into tabular format with:
    -   Transaction dates
    -   Descriptions
    -   Locations
    -   Amounts

### 3. Data Management

-   Automatically updates Google Sheets with processed data
-   Maintains organized transaction records
-   Handles data formatting and validation

### 4. Email Integration

-   Monitors Gmail for invoice-related emails
-   Search keywords: "Rechnung", "Transaktion", "payment", "Invoice", "Bestellung", "RechnungOnline"
-   Processes both email attachments and HTML content
-   Converts HTML emails to PDF when necessary

## Required Credentials

-   Google Drive OAuth2 API
-   Google Sheets OAuth2 API
-   Gmail OAuth2 API
-   OpenAI API

## Dependencies

-   n8n platform
-   HTML2PDF API service
-   OpenAI GPT-4 API

## Flow Structure

1. **Trigger**: Monitors Google Drive for new files
2. **Data Extraction**: Extracts text from PDFs
3. **AI Processing**: Processes data using OpenAI
4. **Data Storage**: Updates Google Sheets
5. **Email Processing**: Handles incoming invoice emails
6. **File Organization**: Stores processed files in Google Drive

## Notes

-   The workflow runs on a minute-by-minute basis for email monitoring
-   Includes error handling and data validation
-   Supports multiple file formats and data sources
-   Maintains original files in designated Google Drive folders

## Configuration

Ensure the following are configured:

-   Google Drive folders for monitoring and storage
-   Google Sheets document for data storage
-   Gmail search parameters
-   OpenAI API credentials
-   HTML2PDF API key

## Error Handling

-   Validates input data formats
-   Handles missing or malformed data
-   Maintains workflow continuity even if individual steps fail
