# SmartPOS

**A web-based Point of Sale and Inventory Management System built with Python, Flask and SQLite.**

SmartPOS lets a small shop manage products and stock, scan product QR codes with a normal laptop webcam (or search manually), process cash sales, and review sales history, all without dedicated POS hardware such as barcode scanners or receipt printers.

> Semester project for **Software Construction and Development Lab (5th Semester)**
> Instructor: Engr. Muhammad Umer Haroon

## Project Status

| | |
|---|---|
| **Current version** | v0.1.0 (initial development) |
| **Stage** | Requirements documented; repository set up; implementation starting |


Requirements are agile and will evolve. See the [requirements document](docs/requirements.pdf) for the full list.

## Group Members

| Member | GitHub | Initial responsibility |
|---|---|---|
| Asma Saqib | [Asma-saqib] | Project lead, repo maintainer, documentation |
| Sidra Noor | [Sidra-noor0303] | Flask backend / database |
| Muskan Iqbal | [MUSKAN-IQBAL] | Frontend / checkout interface |

## Problem Statement

Manual billing and stock tracking in small shops is slow and error-prone, and many POS solutions require specialised equipment. SmartPOS provides a locally runnable web application that works on an ordinary laptop with a browser.

## Planned Features

**Must have (first release)**
- Secure login and logout with administrator and cashier roles
- Product management (add, edit, search, deactivate) with unique SKUs and stock quantities
- QR code generation for product SKUs
- Product lookup by manual search or webcam QR scanning
- Cart with quantity editing, subtotal, discount and tax calculation
- Cash checkout with change calculation and atomic stock updates
- Sales history and transaction details
- Clear errors for unknown QR codes and unavailable cameras
- Automated tests for core business rules

**Should have:** printable receipts, sales summaries and low-stock list  
**Could have:** shop settings, low-stock threshold, CSV report export

**Out of scope for now:** card or online payments, multi-branch use, cloud sync, accounting integration, loyalty features.

## Tech Stack

- **Backend:** Python, Flask
- **Database:** SQLite
- **Frontend:** HTML, CSS, JavaScript (browser-based interface, webcam QR scanning)
- **Version control:** Git and GitHub

## Getting Started

> The application code is still under development. These steps will apply once the first version is available.

```bash
# 1. Clone the repository
git clone https://github.com/<owner>/smartpos.git
cd smartpos

# 2. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate          # Windows
# source venv/bin/activate     # Linux / macOS

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the app locally
flask --app app run
```

Then open `http://localhost:5000` in your browser. Webcam scanning works on `localhost` or HTTPS, and the browser will ask for camera permission. Manual search works without a camera.

## Repository Structure

```
smartpos/
├── README.md
├── requirements.txt
├── .gitignore
├── docs/
│   ├── requirements.md
│   └── requirements.pdf
├── app/            # Flask application (routes, models, business logic)
│   ├── templates/
│   └── static/
├── tests/
└── instance/       # local SQLite database (not committed)
```

## Team Workflow

- **Branches:** `feature/<short-name>` and `fix/<short-name>`, merged into `main` through pull requests.
- **Commits:** short, imperative and specific, e.g. `Add product search endpoint`.
- **Versions:** Git tags using `v0.1.0` for the initial development version up to `v1.0.0` for the first complete release. Files are never copied to represent versions.
- **Tasks:** tracked as GitHub Issues / Projects, based on the product backlog in the requirements document.

## Documentation

- [Requirements document (PDF)](docs/requirements.pdf)
- [Requirements document (Markdown)](docs/requirements.md)
