# Financial Disclosure Data Extraction and Analysis

## Import Libraries
The project begins by importing necessary libraries such as csv, json, zipfile, requests, PyPDF2, and fitz. These libraries provide functionalities for handling CSV files, JSON data, zip files, HTTP requests, and PDF files.

## Define URLs
Two URLs are defined:

## zip_file_url
URL of a ZIP file containing financial disclosure data for the year 2024.

## pdf_file_url
Base URL for accessing individual PDF files containing financial disclosures.

## Download ZIP File
Using the requests library, the script sends an HTTP GET request to the zip_file_url and downloads the ZIP file containing financial disclosure data for the year 2024.

## Save ZIP File
The downloaded ZIP file is saved locally with the name "2024.zip".

## Extract ZIP File
The downloaded ZIP file is extracted, and its contents are saved in the current working directory.

## Process Financial Disclosure Data
The script opens the extracted CSV file "2024FD.txt" containing financial disclosure data. It iterates through each line of the file and checks if the second column (index 1) contains the name "Pelosi". If a line corresponds to Nancy Pelosi's financial disclosure, it extracts the date and document ID from specific columns.

## Download and Process PDF Files
For each financial disclosure related to Nancy Pelosi, the script constructs the URL for the corresponding PDF file using the pdf_file_url and the document ID. It then sends an HTTP GET request to download the PDF file and saves it locally with the document ID as the filename.

## Extract Text from PDF
Once the PDF file is downloaded, the script uses the fitz library (PyMuPDF) to open the PDF file and load its contents. It retrieves the text from the first page of the PDF using the get_text('json') method, which returns the text content in JSON format.

## Print JSON Data
Finally, the JSON data containing the text content of the first page of each PDF file is printed to the console for further processing or analysis.

This project demonstrates a workflow for downloading financial disclosure data, extracting relevant information, downloading associated PDF files, and extracting text content from the PDF files for further analysis.
