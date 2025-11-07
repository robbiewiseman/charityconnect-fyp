# VERSION 1
============================================================
CharityConnect – Final Year Project (BIS, University College Cork)
Student: Robert Wiseman (122436052)
============================================================

PROJECT OVERVIEW
------------------------------------------------------------
CharityConnect is a Flask-based fundraising platform that enables event organisers
to create and manage charity events, issue digital tickets, and generate verified
receipts with QR codes for attendees. The system is designed to demonstrate a
Proof-of-Value artefact by improving transparency, usability, and affordability in
charitable event management.

The system has three primary user roles:
 - Donor/User: Can browse and purchase tickets for charity events.
 - Organiser: Can create and manage charity events and beneficiaries.
 - Administrator: Can verify organiser accounts and audit event activity.

------------------------------------------------------------
ENVIRONMENT AND SETUP
------------------------------------------------------------
Developed using:
 - Python 3.14
 - Flask 3.0
 - SQLAlchemy ORM
 - Flask-WTF (CSRF protection and form validation)
 - PostgreSQL (via Neon cloud instance)
 - ReportLab (for PDF generation)
 - qrcode (for QR code creation)

Local environment managed using:
 - `python-dotenv` for .env configuration
 - `virtualenv` for package isolation
 - `pip install -r requirements.txt` for dependency setup

------------------------------------------------------------
DATABASE CONNECTION
------------------------------------------------------------
The system connects to a Neon PostgreSQL database hosted at:
  postgresql://neondb_owner@ep-orange-wildflower-abcvb0ut-pooler.eu-west-2.aws.neon.tech/neondb?sslmode=require

A local SQLite fallback (`local.db`) is used if no Neon connection is available.

Environment variables are stored in `.env` and loaded at runtime.

------------------------------------------------------------
INSTALLATION AND EXECUTION
------------------------------------------------------------
1. Open the project in VS Code or a terminal.
2. Create and activate a virtual environment:
       python -m venv .venv
       .\.venv\Scripts\activate
3. Install dependencies:
       pip install -r requirements.txt
4. Verify your .env file contains:
       FLASK_ENV=development
       DATABASE_URL=postgresql://<neon_url>
       SECRET_KEY=dev-secret
5. Run the application:
       flask run
6. Access locally:
       http://127.0.0.1:5000

------------------------------------------------------------
DATABASE INITIALISATION (SEED DATA)
------------------------------------------------------------
To create tables and load demo data:

       python seed.py

This seeds:
 - Admin: admin@example.com / admin123
 - Organiser: organiser@example.com / organiser123
 - User: user@example.com / user123
 - Example events: “Christmas Charity Gala”, “Community 5K Fun Run”

------------------------------------------------------------
VERSION CONTROL
------------------------------------------------------------
All code files contain version comments (e.g. Version 1.0).
Future iterations will increment these to 2.0, 3.0, etc.
Version control is maintained locally through manual version tagging
as per UCC FYP audit requirements.
============================================================
# VERSION 1