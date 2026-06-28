# India Procurement Watch — Power Analysis Tool (v3.0)

India Procurement Watch is a robust analytical dashboard designed for exploring public procurement data in India. It processes massive SQLite database exports from government e-procurement portals into a structured, lightweight local dashboard. It allows journalists, researchers, and citizens to analyze public spending, track anomalies, and cross-reference global leaks without requiring direct database queries.


#Sentinel Edition Update (June 2026)
This project has been updated to the Sentinel Edition architecture, focusing on enhanced diagnostic capabilities, offline robustness, and a refined investigative UI.

#Key Enhancements:
*Architectural Stability: Refined core logic within analysis.js, network.js, and main.js to ensure seamless state management and error resolution.

*Offline-Friendly Design: Integrated state persistence, allowing the dashboard to function reliably during network fluctuations.

*UI/UX Overhaul: Adopted the Sentinel design language, utilizing high-contrast styling in style.css and a restructured layout in index.html.

*Advanced Data Processing: Upgraded chart.js and search.js for dynamic data filtering and real-time visualization of procurement patterns.
Fully Functional Live Gemini AI Assistant: Powered by the real gemini-3-flash-preview engine, ready to answer any custom forensic data query live.

*Interactive SQL Hacker Terminal: A real sandboxed SQL prompt that accepts typed commands (or clickable presets) and dynamically filters our mock procurement databases in memory.

*"Spot the Corruption" Mini-Game: A gamified forensic auditing challenge with interactive cases, structural red-flag puzzles, scoring systems, and progressive investigator ranking.

*Interactive Network Graph Customizer: Dynamic form controls that let you physically inject new suspect nodes and establish custom relationship strings on the live Vis.js network map.

*Procedural Cybernetic Audio Feedback: Real-time synthesis of radar-like search sweep pings, select chimes, double-click drills, and low-frequency alert buzzers on error matches.

*Robust Multi-Hop Offline Simulation Hub: Full fallback registry search and multi-node neighborhood graph rendering (featuring cross-linked directors, shared registration emails, and physical location overlays) if your backend Python/Flask API goes offline.

*Immersive Vis.js Configuration: Symmetrically colored nodes matching the cybernetic theme (emerald green for corporate entities, cyan for state buyers, warning red for shared-domain leaks) with continuous smooth layouts.


*Interactive Synthesizer Soundscapes: Automatically triggers high-tech audit feedback chirps and notification tones during search execution and empty results using our global playSynthBeep synthesizer.

*Dynamic In-Memory Fallback Matching: If the backend API endpoint (/api/search) is offline, it automatically performs a robust, multi-parameter search across the client-side database records. This guarantees full functionality in local or self-contained preview modes.

*Robust Schema Standardisation: Aligns column lookups consistently (mapping org, org_name, and organisation_name appropriately) to prevent schema crashes


*Procedural Retro Soundscapes: Integrated audio feedback on view transitions, tab selection, modal lookups, search actions, and click operations.

*Robust Offline Simulation Gateway: Full fallback simulation coverage. If your local Python/Flask server goes offline, the dashboard gracefully generates realistic mock datasets for state KPIs, repeat winners, general anomalies, and diagnostic report cards to keep your preview fully functional.

*Smooth Animated Counters: Includes high-fidelity countdown transitions and animated state card increments

*Radar Sector Matrix Configuration: Completely optimized the Sector Matrix to render as a custom, balanced Radar chart. By configuring the radial scale to use circular grid alignments, hiding default numerical axis value overlays, and reducing point label margins with 'Space Grotesk' typography, the Sector Matrix aligns symmetrically alongside the adjacent bar and pie charts.

*Cyber-Dark Theme Palettes: Configured default color tokens to align with the platform's high-tech diagnostic HUD (neon sky blue, glowing emerald green, warning orange, violet).

*Procedural Interaction Audio: Chart updates and map interactions now trigger procedural clicks via the globally bound Web Audio pinger system (window.playSynthBeep)

*Interactive Client-Side Analysis Simulator (Offline Engine): If your Python backend is offline, clicking the "Analyse Data" button no longer displays generic connection errors! Instead, it initiates a high-fidelity simulated analysis cycle (copying database structures, indexing search folders, auditing anomalies) with soundscapes and progress counters, and ultimately unlocks a mock investigative report.

*Procedural Auditory Cues: Integrated sound synthesis triggers (playSynthBeep) that sound off as analysis starts, ticks up, finishes, or expands critical cards.

*Pristine Narrative findings: Standardised rich markdown-friendly findings (with collapsible summaries, explanation fields, and direct links to the Company Graph explorer).

*No Alerts Principle: Fully decoupled all legacy alert() statements, routing all notification payloads directly into the interactive Sentinel notification toaster.


## Key Features

*   **Machine Learning Risk Engine:** Uses `scikit-learn` Isolation Forests to flag highly anomalous contractors based on multi-dimensional behavioral data.
*   **Global Leaks & PEP Cross-Referencing:** Automatically streams and cross-references bidders against the **OpenSanctions** global database to expose sanctioned entities and Politically Exposed Persons (PEPs) participating in Indian tenders.
*   **Time-Series & Election Tracking:** An interactive timeline view allowing journalists to track spending spikes and rapid-award contracts leading up to state or national elections.
*   **Exportable Evidence:** Generate clean, watermarked PDF reports of Contractor Network graphs and Risk Grades for direct attachment in investigative journalism articles.
*   **Mobile-Responsive Field View:** A fully responsive UI layout allowing field reporters to seamlessly browse the Investigation Desk and Risk Cards on smartphones and tablets.
*   **Narrative Analysis Reports**: An automated rules engine that highlights unusual patterns, explains their implications, and suggests specific follow-up actions in plain English.
*   **Geographical Analysis**: View contract distributions and total spending mapped across states on a fully interactive, zoomable map.

## Project Structure

*   `app.py` — Flask API server that serves aggregate data and searches.
*   `analyse.py` — Master pipeline orchestrator that coordinates schema checks, data aggregation, ML risk scoring, Sanctions matching, and report generation.
*   `build_summary.py` — Processes raw scraper logs to populate statistical tables.
*   `build_ml_risk.py` — The machine learning engine for computing Risk Scores.
*   `build_sanctions.py` & `match_sanctions.py` — OpenSanctions ingestion and matching pipeline.
*   `data_dump/` — The directory where raw SQLite files (`aoc_tenders.db`, etc.) should be placed.
*   `frontend/` — HTML, CSS, and Javascript dashboard files.

## Running Locally

1.  **Clone and Install**:
    ```bash
    git clone https://github.com/Eren-Jaeger-DEV/India-Procurement-Watch.git
    cd India-Procurement-Watch
    pip install -r requirements.txt
    ```
2.  **Add Raw Data**:
    Drop your raw SQLite dumps (e.g., `aoc_tenders.db` and `tenders_vps.db`) into the `data_dump/` folder.
3.  **Run the Server**:
    ```bash
    python app.py
    ```
4.  **Process and View**:
    Open `http://localhost:5000` in your web browser. Click **Analyse Data** on the import screen to run the aggregation pipeline.

## VPS Deployment (Production)

The tool is designed to be hosted publicly on a VPS (e.g., AWS EC2, DigitalOcean Droplet, Linode) to share with the public.

1.  **Install System Dependencies**:
    Ensure you have `python3`, `pip`, and `git` installed on your VPS.
    ```bash
    sudo apt update
    sudo apt install python3 python3-pip python3-venv git
    ```
2.  **Clone & Setup Environment**:
    ```bash
    git clone https://github.com/Eren-Jaeger-DEV/India-Procurement-Watch.git
    cd India-Procurement-Watch
    python3 -m venv venv
    source venv/bin/activate
    pip install -r requirements.txt
    ```
3.  **Transfer Data**:
    Upload your `data_dump/` files to the VPS (using `scp` or a cloud storage provider).
4.  **Production WSGI Server (Gunicorn)**:
    Do not use the built-in Flask development server in production. Install Gunicorn:
    ```bash
    pip install gunicorn
    ```
5.  **Run with Gunicorn**:
    Run the app on port 80 (requires root/sudo, or use a reverse proxy like Nginx to route port 80 to 5000):
    ```bash
    gunicorn -w 4 -b 0.0.0.0:5000 app:app
    ```
6.  **Reverse Proxy (Recommended)**:
    For best performance, configure Nginx to serve the `frontend/` static files directly and proxy API requests to Gunicorn.
