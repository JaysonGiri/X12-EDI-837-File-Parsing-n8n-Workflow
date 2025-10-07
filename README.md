# X12-EDI-837-File-Parsing-n8n-Workflow

# Workflow Image:
<img width="1518" height="877" alt="image" src="https://github.com/user-attachments/assets/05c44f18-bc91-4803-b79e-cf48b6b67188" />

# What It Does
Automates the processing of healthcare claims in three formats:

X222: Professional claims (doctor/provider services)
X223: Institutional claims (hospital/facility claims)
X224: Dental claims

Takes uploaded EDI files, parses them, validates the data, and outputs results to Google Sheets and HTML reports.

# How It Works

Upload - Submit an EDI 837 file via the form
Parse - Extract claim data from the EDI format
Validate - Check for errors and data quality issues
Route - Send valid claims to processing, invalid ones to error reporting
Output - Store data in Google Sheets and generate HTML reports


# What Gets Extracted

Claim dates and amounts
Patient and subscriber info
Provider details
Diagnosis and procedure codes
Service line items
Payer information

# Validation
The workflow checks for:

Missing required fields
Valid NPI format (10 digits)
Proper address formatting
Claim amounts and service line totals
Control number matches
Diagnosis code format

Errors are categorized and logged with details about what went wrong.


# Setting Up
You'll need:

An n8n instance
Google Sheets API credentials
A Google Sheet with tabs for each claim type (Professional/Institutional, Dental, Error Report)

Update the workflow with your Google Sheet ID and tab references.


# Using It

Go to the form submission URL
Upload your EDI file (filename should start with X222, X223, or X224)
The workflow processes it automatically
Check your Google Sheet for results

Valid claims get added to the appropriate sheet. Invalid claims get logged in the Error Report sheet.


# Version Compatibility

X12 5010 format variants (005010X222A1, 005010X223A2, 005010X224A2)
Professional claims (837P)
Institutional claims (837I)
Dental claims (837D)
