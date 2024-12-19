# Algorithm Visualizer

Algorithm Visualizer is an interactive web-based application for visualizing sorting and pathfinding algorithms. It helps users understand how different algorithms work by providing animations and step-by-step insights into their processes. 

This project is built with **Spring Boot**, **Thymeleaf**, **JavaScript**, and **CSS**, leveraging **HTMX** for dynamic content swapping and smooth interactivity.

---

## Table of Contents

- [Features](#features)
- [Demo](#demo)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Sorting Algorithms Supported](#sorting-algorithms-supported)
- [Pathfinding Algorithms Supported](#pathfinding-algorithms-supported)
- [Folder Structure](#folder-structure)
- [Code Structure](#code-structure)
- [HTMX Integration](#htmx-integration)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- Interactive visualization of sorting and pathfinding algorithms.
- Dynamic swapping of algorithms using **HTMX**.
- Clean and responsive user interface with animated transitions.
- Real-time updates for each algorithm step.
- Toggle between different algorithms directly from the navbar.
- Color-coded visualization for better understanding.
- Fully modular code structure for easy extensibility.

---

## Demo

Here’s how the application looks when running:

1. **Sorting Algorithms Visualization**  
   Displays sorting progress step-by-step. Each bar represents an element in the array, and their heights are proportional to their values.

2. **Pathfinding Algorithms Visualization**  
   Demonstrates the grid traversal process, highlighting visited nodes and the shortest path.

You can see a live demo [here](#). (Link will be updated later)

---

## Technologies Used

### Backend
- **Spring Boot**: Backend framework for handling requests and responses.
- **Java**: Primary language used for the backend logic.
- **Thymeleaf**: Server-side rendering engine for dynamic HTML content.

### Frontend
- **HTMX**: For seamless AJAX requests and DOM updates.
- **JavaScript**: For client-side interactivity and animation.
- **Bootstrap**: For responsive and modern UI components.
- **CSS**: For custom styling.

---

## Installation

### Prerequisites
1. **Java** (JDK 11 or later)
2. **Maven** or **Gradle**
3. **IDE**: IntelliJ IDEA, Eclipse, or VS Code.

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/algorithm-visualizer.git
   cd algorithm-visualizer
   ```
2. Build the project:
   ```bash
   mvn clean install
   ```
3. Run the Spring Boot application:
   ```bash
   mvn spring-boot:run
   ```
4. Open your browser and go to:
   ```
   http://localhost:8080
   ```

---

## Usage

### Navbar Options
- **Sorting Algorithms**: Select one of the supported algorithms (Bubble, Insertion, Merge, etc.) via clicking sorting algorithm in the navbar. The visualization updates dynamically without refreshing the page.
- **Pathfinding Algorithms**: Switch between Dijkstra, A*, BFS, and DFS using radio buttons in the navbar.

### Visualizing Sorting
1. Click on a sorting algorithm in the navbar.
2. Watch the sorting animation in the container below.
3. Refresh the page to reload.

### Visualizing Pathfinding
1. Select a pathfinding algorithm (e.g., BFS or Dijkstra) from the navbar.
2. Click "Start" to begin the animation.
3. Observe the grid traversal and shortest path.

---

## Sorting Algorithms Supported

- **Bubble Sort**: Compare adjacent elements and swap them.
- **Insertion Sort**: Build the sorted portion one element at a time.
- **Merge Sort**: Divide-and-conquer strategy for sorting.

---

## Pathfinding Algorithms Supported

- **Dijkstra's Algorithm**: Finds the shortest path between nodes in a weighted graph.
- **A***: Heuristic-based shortest path algorithm.
- **Breadth-First Search (BFS)**: Explores the graph level by level.
- **Depth-First Search (DFS)**: Explores as deep as possible before backtracking.

---

## Folder Structure

```
/algorithm-visualizer
│
├── /src
│   ├── /main
│   │   ├── /java
│   │   │   ├── /com
│   │   │   │   ├── /example
│   │   │   │   │   ├── /algorithmvisualizer
│   │   │   │   │   │   ├── /algorithms
│   │   │   │   │   │   │   ├── /implementation        # Algorithm implementations
│   │   │   │   │   │   │   │   ├── AStar.java          # A* pathfinding algorithm
│   │   │   │   │   │   │   │   ├── Bfs.java            # BFS pathfinding algorithm
│   │   │   │   │   │   │   │   ├── Dfs.java            # DFS pathfinding algorithm
│   │   │   │   │   │   │   │   ├── Dijkstra.java       # Dijkstra's shortest path algorithm
│   │   │   │   │   │   │   ├── PathFind.java           # Interface for pathfinding algorithms
│   │   │   │   │   │   │   ├── AStarCell.java         # Helper class for A* algorithm
│   │   │   │   │   │   │
│   │   │   │   │   │   ├── /model                     # Model classes for algorithms
│   │   │   │   │   │   │   ├── Cell.java              # Represents a cell for pathfinding (BFS, DFS, Dijkstra)
│   │   │   │   │   │   │   ├── Point.java             # Represents a point for DFS
│   │   │   │   │   │   │   ├── PathFindResult.java    # Represents pathfinding result (grid, path, moves)
│   │   │   │   │   │   │
│   │   │   │   │   │   ├── /controller                # Web controllers
│   │   │   │   │   │   │   ├── PathFindController.java # Handles pathfinding algorithm requests
│   │   │   │   │   │   │   ├── SortingController.java # Handles sorting algorithm requests
│   │   │   │   │   │   │
│   │   │   │   │   │   ├── /service                   # Service classes for business logic
│   │   │   │   │   │   │   ├── PathFindService.java    # Logic for pathfinding algorithms
│   │   │   │   │   │   │   ├── SortingService.java    # Logic for sorting algorithms
│   │   │   │   │   │   │
│   │   │   │   │   │   ├── /AlgorithmVisualizerApplication.java # Main Spring Boot application class
│   │   │   │   │   │
│   │   │   ├── /resources
│   │   │   │   ├── /templates
│   │   │   │   │   ├── index.html                     # Main homepage for visualizations
│   │   │   │   │   ├── sorting.html                   # Sorting algorithm visualization
│   │   │   │   │   ├── path-find.html                 # Pathfinding algorithm visualization
│   │   │   │   ├── /static
│   │   │   │   │   ├── path-find.js                   # JavaScript for pathfinding visualization
│   │   │   │   │   ├── sortingScript.js               # JavaScript for sorting visualization
│   │   │   │   │   ├── style.css                      # CSS for general styling
│
└── pom.xml                                            # Maven configuration file

```

## Code Structure

### Key Files and Folders
- **Backend:**
  - **`AlgorithmVisualizerApplication.java`**: Main Spring Boot application class.
  - **Controller:**
    - **`PathFindController.java`**: Handles requests related to pathfinding algorithms and serves pathfinding visualization pages.
    - **`SortingController.java`**: Handles sorting algorithms requests and serves sorting visualization pages.
  - **Service:**
    - **`PathFindService.java`**: Contains the business logic for the pathfinding algorithms.
    - **`SortingService.java`**: Contains the business logic for sorting algorithms.
  - **Model:**
    - **`PathFindResult.java`**: Represents the result of a pathfinding operation (e.g., grid, path, explored cells).
    - **`Cell.java`**: Represents a cell in the grid for pathfinding algorithms, containing its row, column, distance, and reference to the previous cell.
    - **`Point.java`**: Represents a point used in DFS (Depth-First Search) with a row, column, and reference to the previous point.

- **Algorithm Implementation:**
  - **Pathfinding Algorithms (PathFind.java interface and implementations):**
    - **`PathFind.java`**: Interface that defines the common method (`find()`) for all pathfinding algorithms.
    - **`AStar.java`**: A* pathfinding algorithm implementation.
    - **`Bfs.java`**: BFS (Breadth-First Search) pathfinding algorithm implementation.
    - **`Dfs.java`**: DFS (Depth-First Search) pathfinding algorithm implementation.
    - **`Dijkstra.java`**: Dijkstra's shortest path algorithm implementation.
  - **Supporting Classes:**
    - **`AStarCell.java`**: Helper class used by A* to represent grid cells with additional data (heuristic, cost).
    - **`Cell.java`**: Represents a cell used in BFS, DFS, and Dijkstra algorithms, including its position and reference to the previous cell (model).
    - **`Point.java`**: Represents a point used in DFS, storing its position and reference to the previous point (model).

- **Frontend:**
  - **HTML Files:** Located in the `src/main/resources/templates` directory.
    - **`index.html`**: Home page that includes links to pathfinding and sorting algorithm visualizations.
    - **`sorting.html`**: Page to visualize sorting algorithms.
    - **`path-find.html`**: Page to visualize pathfinding algorithms on a grid.
  - **JavaScript Files:** Located in the `src/main/resources/static` directory.
    - **`path-find.js`**: Handles the grid rendering and animation for pathfinding algorithms.
    - **`sortingScript.js`**: Handles the sorting visualization, animating the sorting steps.
  - **CSS File:**
    - **`style.css`**: General styling for the visualization grid, sorting bars, and UI elements.

---

## HTMX Integration

HTMX is used extensively in this project to enable dynamic and seamless updates:
- **Dynamic Content Loading**: The navbar buttons (`<label>`) use `hx-get` to fetch corresponding HTML snippets.
- **Real-time Swapping**: `hx-swap="outerHTML"` allows swapping only the necessary parts of the DOM.
- **Interactive Controls**: Grid generation and sorting animations are triggered without page reloads.

---

## Contributing

Contributions are welcome! Here’s how you can help:
1. Fork the repository.
2. Create a new feature branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes and push the branch:
   ```bash
   git commit -m "Add feature-name"
   git push origin feature-name
   ```

---
