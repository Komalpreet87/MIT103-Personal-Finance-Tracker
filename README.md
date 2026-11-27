# Personal Finance Tracker -- Phase 2

## Project information

**Unit:** MIT103 -- Building Blocks of Coding\
**Assessment:** Assessment 3 -- Software Development Project, Phase 2\
**Project:** Personal Finance Tracker

## 1. About the project

This project is a small Personal Finance Tracker developed in Python. It
is used to record income and expenses and to manage transaction details.
The program stores transaction information in a CSV file.

This version builds on the earlier tracker by adding CSV file handling,
Admin and Viewer roles, input validation, password verification and
category-wise totals.

## 2. Main features

-   Add a transaction.
-   Display all transactions.
-   Search for a transaction by transaction ID or category.
-   Delete a transaction.
-   Load transaction records from a CSV file.
-   Save changes to a separate working CSV file.
-   Show category-wise totals using a dictionary.
-   Provide different access for Admin and Viewer users.
-   Verify passwords using a salted password hash.
-   Display messages for some invalid inputs and file errors.

## 3. User roles

### Admin

The Admin can:
- Add transactions.
- Display transactions.
- Search transactions.
- Delete transactions.

### Viewer

The Viewer can:
- Display transactions.
- Search transactions.

The Viewer cannot add or delete transactions. The program checks permissions in the protected operations as well as in the menu.

## 4. Project files

The repository contains these main files:

-   `MIT103_A3_Revised_T3_2026_Starter_Notebook.ipynb` -- the completed
    Google Colab notebook. If the notebook is renamed before upload, use
    the actual uploaded filename.
-   `MIT103_A3_Revised_T3_2026_Sample_Transactions.csv` -- the supplied
    sample transaction data.
-   `README.md` -- project information and instructions.

The notebook also uses `my_transactions.csv` as a separate working file.
This file is created from the sample CSV when it does not already exist.
The original sample CSV should not be changed.

## 5. How to run the notebook

1.  Open the notebook in Google Colab.
2.  Run the setup cell at the beginning.
3.  When the upload window appears, select
    `MIT103_A3_Revised_T3_2026_Sample_Transactions.csv`.
4.  Run the remaining notebook cells in order.
5.  When asked, enter demonstration passwords for the Admin and Viewer
    accounts.
6.  Run the main program and log in using the username for the role you
    want to test.
7.  Follow the menu options shown on the screen.

Use fictional transaction details for testing. Do not enter real
financial information or personal passwords.

## 6. CSV data and saving changes

The sample CSV uses these column headings:

`transaction_id, date, category, description, amount`

The program reads transaction records from the CSV and creates
Transaction objects. It saves changes to `my_transactions.csv`, which is
separate from the original sample file.

Google Colab runtime storage is temporary. If the runtime is reset,
files saved only in the runtime may be lost. To continue with previously
saved changes, download and keep a copy of `my_transactions.csv`. In a
new runtime, upload both the original sample CSV and the saved working
CSV, keeping their filenames unchanged. The setup code uses the working
file if it is already present; otherwise, it creates a new working copy
from the sample file.

## 7. Python libraries

The notebook uses Python libraries and modules including:

-   `csv` -- reads and writes CSV records.
-   `pathlib` -- works with file paths.
-   `hashlib` -- creates password hashes.
-   `hmac` -- compares password hash values.
-   `os` -- provides operating-system functions.
-   `shutil` -- copies the sample CSV to create the working file.
-   `secrets` -- creates a random salt for password verification.
-   `getpass` -- accepts password input without displaying it.
-   `google.colab.files` -- uploads files into Google Colab.

## 8. Password and access security

The notebook creates demonstration Admin and Viewer accounts. It uses a
random salt and `hashlib.pbkdf2_hmac` to create a password verifier.
During login, the entered password is checked against the stored
verifier using `hmac.compare_digest`.

The password hash is not encryption. It is used to verify a password
without storing the plain password in the account data. These accounts
are for classroom demonstration only.

Do not upload passwords, password-generation output, real financial
records or other private information to the repository.

## 9. Limitations

This is a learning project for an assessment. It is not a complete
banking or financial service. It uses CSV files rather than a database
and does not include features such as multi-factor authentication,
account recovery or production-level account management. Colab runtime
files are temporary, so the working CSV must be kept separately if the
data is needed after a runtime reset.

## 10. Assessment use

This project was prepared for MIT103 Assessment 3 -- Software
Development Project, Phase 2. The sample transactions are fictional and
are provided for learning and testing.

## 11. Testing

The program was checked using different test cases:

- Admin login and transaction management.
- Viewer login and access restrictions.
- Searching for a transaction by ID.
- Handling an invalid menu choice.
- Checking transaction deletion when an ID is not found.

These tests helped check the main functions and user permissions of the tracker.
