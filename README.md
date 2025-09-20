# WhatsInsideUSB_V1
Agamya Tech Summit Hackathon problem 
USB Malware Scanner
Overview
This project is a Python-based USB Malware Scanner that detects inserted USB drives on Windows, scans all files on the inserted USB for malware by checking their SHA256 hashes through the VirusTotal API, and provides a graphical user interface (GUI) for users to see scanning results and delete detected malicious files.

Features
Automatic USB Detection: The application monitors Windows system events to detect when a USB drive is inserted.
Malware Scanning: Scans every file on the USB drive by computing its SHA256 hash and querying the VirusTotal API for malware detection.
Graphical User Interface (GUI): Built with tkinter, shows live scan status and file results.
Dynamic Results Display: Files appear in the interface as they are scanned, with malicious files flagged in red.
Multi-Select Deletion: Users can select and delete one or more malicious files directly from the USB drive through the GUI.
Status Updates: Displays dynamic status messages guiding the user through scanning and deletion processes.

Requirements
Python 3.8 or later

Windows operating system (due to usage of WMI for USB detection)

Internet connection to access VirusTotal API

Python packages:

pywin32

requests

Install dependencies with:

bash
pip install pywin32 requests
Setup
VirusTotal API Key:
Obtain a free API key by creating an account at VirusTotal. Replace your API key in the backend scanning file:

python
VT_API_KEY = 'YOUR_VIRUSTOTAL_API_KEY'
Code Structure:

start.py
Contains backend scanning functions that calculate file hashes and query VirusTotal API.

ui.py
Contains the graphical user interface code that detects USB insertion, displays scanning progress, lists files, and enables file deletion.

How to Run
Ensure your USB drive is connected or connect it while the program runs.

Run the UI:

bash
python ui.py
The GUI will:

Automatically detect USB insertion.
Begin scanning files and show dynamic status.
Display all files with scan results: green for clean files, red for malicious.
Allow selecting malicious files and deleting them from the USB through the interface.

File Descriptions
start.py
Functions to calculate SHA256 hashes of files.
Sends hash queries to VirusTotal API.
Returns list of malicious files detected on the USB.

ui.py
Runs a Tkinter application.
Monitors USB insertion using Windows WMI events.
Displays dynamic scanning progress and file status.
Supports multi-selection and deletion of malicious files.

Notes & Limitations
VirusTotal API Free Limits: The free API allows roughly 500 requests per day; scanning many files may hit limits.
Windows-only: The app relies on Windows-specific WMI for USB detection.
Permissions: Running as administrator may be required to delete some files from USB.
File Access: Files in use or protected may not be deletable.
Performance: Scanning large USB drives can take significant time due to API calls.

Future Improvements

Implement caching to avoid repeated scanning of unchanged files.
Add support for unknown malware detection via heuristic or machine-learning.
Extend OS compatibility beyond Windows.
Add a progress bar and more responsive UI elements.
Handle API rate limiting more gracefully.

License
This project is open-source and free to use for educational and personal purposes.

Contact
For questions or contributions, please contact the developer.
