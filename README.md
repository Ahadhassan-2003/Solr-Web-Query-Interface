# Solr Search Interface

A web application for searching and filtering book information stored in Apache Solr.

## Overview

This application provides a user-friendly web interface to search a Solr database containing book information. Users can search by keywords, get autocomplete suggestions, and filter results by category, author, and publication status.

## Features

- Real-time search with immediate results
- Autocomplete suggestions as you type
- Dynamic filtering by category, author, and publication status
- Responsive design for all screen sizes
- Clean separation of frontend and backend components

## Architecture

The application consists of two main components:

1. **Backend API** (FastAPI)
2. **Frontend UI** (HTML, CSS, JavaScript)

## Setup Instructions

### Prerequisites

- Python 3.7+
- Apache Solr running with indexed data
- pip (Python package manager)

### Backend Setup

1. Install the required dependencies:
   ```
   pip install fastapi uvicorn requests
   ```

2. Update the `SOLR_URL` variable in `app.py` to point to your Solr collection:
   ```python
   SOLR_URL = "http://localhost:8983/solr/jcgArticles"  # Change if needed
   ```

3. Start the FastAPI server:
   ```
   uvicorn app:app --reload
   ```
   The API will be available at http://localhost:8000

### Frontend Setup

1. Place all three files in a directory:
   - `index.html`
   - `styles.css`
   - `search.js`

2. Update the `API_URL` in `search.js` if your backend is not running on port 8000:
   ```javascript
   const API_URL = 'http://localhost:8000';  // Change if needed
   ```

3. Serve the frontend files using any web server, or simply open the HTML file in a browser.
   For development, you can use Python's built-in server:
   ```
   python -m http.server 8080
   ```
   Then access the application at http://localhost:8080

## API Endpoints

- **GET /search/**: Search the Solr database with optional filters
- **GET /suggest/**: Get autocomplete suggestions based on partial input
- **GET /filters/**: Retrieve available filter options for categories and authors

## File Structure

```
solr-search-app/
├── backend/
│   └── app.py              # FastAPI backend application
├── frontend/
│   ├── index.html          # HTML structure
│   ├── styles.css          # CSS styling
│   └── search.js           # JavaScript functionality
└── README.md               # This file
```

## Future Enhancements

- Pagination for large result sets
- More advanced filtering options
- Sort functionality
- User authentication for saved searches
