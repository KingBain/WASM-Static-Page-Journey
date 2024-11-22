# Static Dashboard with SQLite and WebAssembly

This repository contains a demo application showcasing a lightweight and cost-effective approach to creating and hosting a dashboard that displays and manipulates data. The solution progresses from a traditional cloud-hosted setup with a PostgreSQL database and a Python Dash app to a fully static, client-side implementation using JavaScript, SQLite, and WebAssembly (WASM). 

## Key Features
- **Static Hosting**: The application can be hosted entirely for free on platforms like GitHub Pages or in a cloud storage bucket, as it requires no backend server.
- **SQLite in the Browser**: Uses SQLite backed by WASM to handle database operations directly in the browser session.
- **Dynamic Visualization**: Displays data on an interactive Plotly graph and supports adding, updating, and deleting data.
- **Cost Efficiency**: Eliminates the need for cloud-hosted services like PostgreSQL and app hosting, reducing potential monthly costs from ~$30 to $0.

## Demo
Check out the live demo of the app:  
[**Demo App**](https://rawcdn.githack.com/KingBain/WASM-Static-Page-Journey/refs/heads/main/demo/index.html)

Click the screenshot below to watch the YouTube video explaining this project:

[![Screenshot of Demo](https://github.com/user-attachments/assets/77211f62-e40b-4a6e-99a8-38f2e82d7134)](https://www.youtube.com/watch?v=e0v8wDdxCNs)

## Evolution of the Solution
### Original Setup:
- **Components**:
  - Python Dash app hosted in Azure App Service.
  - PostgreSQL database hosted in Azure.
- **Challenges**:
  - High cost of hosting.
  - Complexity of maintaining a PostgreSQL database for static or infrequently changing data.

### Optimized Setup:
- **Components**:
  - Static HTML and JavaScript files served via GitHub Pages or other free hosting solutions.
  - SQLite database converted to a static `.sqlite` file and managed client-side via WASM.
- **Advantages**:
  - All operations run directly in the client’s browser.
  - No persistent backend or database needed.

## How It Works
1. **Database Initialization**: A PostgreSQL SQL dump was converted into a static SQLite database file.
2. **Client-Side Database**: The SQLite database is loaded into the browser using [sql.js](https://sql.js.org/), a JavaScript library that runs SQLite through WebAssembly.
3. **Dashboard Implementation**: 
   - The application is built with JavaScript and Plotly for interactive data visualization.
   - Users can query, add, and delete data dynamically.
4. **Hosting**: The app consists of two static files:
   - An HTML file for the frontend interface.
   - A pre-generated SQLite database file.

## Running the Demo
To run the demo locally:
1. Clone this repository.
2. Open the `index.html` file in your browser. Ensure the `.sqlite` file is in the same directory.
3. Interact with the app: Query data, add new entries, and visualize changes on the graph.

## Benefits of the Approach
- **Zero Backend Dependencies**: No need for hosted databases or servers.
- **Easy Deployment**: Simply upload the HTML and SQLite files to GitHub Pages or any static hosting service.
- **Lightweight**: Suitable for small datasets and dashboards where persistence is not a concern.

## Example Use Case
The demo application displays planetary data (e.g., radius, mass, distance from the sun) in an interactive dashboard. Users can:
- Query existing planet data.
- Add new celestial objects.
- Delete objects dynamically.

## Technologies Used
- **SQLite**: A lightweight, file-based database.
- **sql.js**: A WebAssembly port of SQLite for client-side database operations.
- **Plotly.js**: A JavaScript library for creating interactive charts and graphs.
- **GitHub Pages**: For hosting the static files.

## Future Improvements
- Add support for persistence using browser storage or serverless options.
- Explore compatibility with larger datasets and offline-first scenarios.

## Acknowledgments
This project was inspired by the potential of using WebAssembly and static file hosting to drastically reduce the cost and complexity of deploying web applications. 

ChatGPT was used in assisting with the Python to JavaScript conversion.

