# email-scraper-google-sheets
A robust Python scraper that extracts contact emails, LinkedIn &amp; Facebook URLs from websites, syncing results into Google Sheets.

# PLEASE NOTE THAT THE CODE IS WRITTEN ON GOOGLE COLAB.

# Email Scraper with Google Sheets Integration

A powerful Python web scraper that extracts contact emails, Facebook and LinkedIn profile links, and source URLs from websites — then syncs everything into Google Sheets using a service account.

##  Features

-  Multi-phase scraping: homepage, contact pages, and subpages
-  Smart email extraction: handles obfuscation and scores matches based on domain, keywords, and frequency
-  Social media detection: identifies relevant Facebook & LinkedIn links while skipping generic ones
-  Google Sheets sync: writes results directly to a specified sheet with retry and validation logic
-  Timeout control and interruption support for long-running processes
-  Real-time logging with timestamped outputs for easy traceability

##  Setup Instructions

### 1. Google Colab or Local Jupyter Notebook

This scraper is designed to run in [Google Colab](https://colab.research.google.com) or any Python notebook environment. If you're using a restricted device (e.g., admin-controlled macOS), Colab is ideal.

### 2. Service Account Setup

To authenticate with Google Sheets and Drive:

- Go to Google Cloud Console → create a **Service Account**
- Enable the **Google Sheets API** and **Google Drive API**
- Download credentials and name the file exactly:  
  **`service-account.json`**
- Upload it to your Colab environment or place it in your working directory

> 🔐 Your script specifically looks for the file at `/content/service-account.json`, so do not rename it!

### 3. Google Sheet Structure

Your sheet should have these columns (headers starting from the first row):

 | Column Name         | Description                                     |
 |---------------------|-------------------------------------------------|
A| `Website`           | Website URL to analyze                          |
B| `Emails`            | Valid domain-matching email                     |
C| `Suspicious Email`  | Valid email that doesn't match the domain       |
D| `Facebook URL`      | Scraped Facebook profile link                   |
E| `LinkedIn URL`      | Scraped LinkedIn page/company profile           |
F| `Email Source URL`  | Page where the email was found                  |

> 📝 If any column is missing, the script will automatically create and populate it with default values.

### 4. Paste Your Google Sheet ID

Inside the `main()` function, there is a variable called:
sheet_id = "PASTE-YOUR-ID-HERE"


5. **Run the Script**: Start the main function to launch threaded scraping.

## 📦 Dependencies

Make sure these packages are installed (the script handles it automatically):


## 🧑‍💻 Author

Built by [LevonHak](https://github.com/LevonHak) — automation enthusiast & web scraping architect.


---

## ⚖️ LICENSE

MIT License

Copyright (c) 2025 LevonHak

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
In the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...

[Full license text continues — GitHub autofills this if you select MIT during repo creation]



