# Exam Scheduling with Graph Coloring

A single-file web application demonstrating graph coloring for exam scheduling problems. This project showcases graph theory concepts in a practical application for a math class.

## The Mathematics

This application solves the exam scheduling problem using graph coloring:

- **Nodes**: Each course is represented as a node in the graph
- **Edges**: An edge connects two courses if they share at least one student (creating a conflict)
- **Graph Coloring**: Each color represents a time slot. The goal is to assign colors (time slots) to courses such that no two adjacent courses (conflicting courses) share the same color
- **Chromatic Number**: The minimum number of colors needed to properly color the graph
- **Algorithm**: Greedy coloring with nodes ordered by decreasing degree (courses with most conflicts colored first)

## Features

- **Add Courses**: Input course names to create nodes in the graph
- **Add Students**: Assign students to multiple courses to create conflicts
- **Build Graph & Color**: Automatically constructs the conflict graph and applies greedy coloring
- **Visualization**: Interactive graph visualization using vis.js showing colored nodes
- **Schedule Output**: Clean display of time slots with assigned courses
- **Educational Content**: Explanation of the chromatic number and algorithm used
- **Dynamic Updates**: Add/remove students and courses, then re-run to see changes

## How to Use

1. **Open the App**: Open `index.html` directly in any modern web browser
2. **Add Courses**: Enter course names and click "Add Course"
3. **Add Students**: Enter student names and select multiple courses they are enrolled in
4. **Generate Schedule**: Click "Build Graph & Color" to see the conflict graph and computed schedule
5. **Experiment**: Add more students or courses and re-run to observe how the graph and coloring change

## Technical Details

- **Single File**: Everything contained in one `index.html` file
- **No Frameworks**: Pure HTML, CSS, and JavaScript
- **Visualization**: vis.js library loaded from CDN for graph rendering
- **Browser Compatibility**: Works in any modern browser with JavaScript enabled
- **Hosting**: Compatible with GitHub Pages or any static web host

## Graph Coloring Algorithm

The greedy coloring algorithm works as follows:

1. Calculate the degree (number of conflicts) for each course
2. Sort courses by decreasing degree
3. For each course in this order:
   - Find the smallest color not used by any conflicting course
   - Assign that color to the course

This heuristic often finds good approximations of the chromatic number but is not guaranteed to be optimal.

## Example

Suppose we have courses: Math, Physics, Chemistry, Biology

Students:
- Alice: Math, Physics
- Bob: Physics, Chemistry
- Carol: Chemistry, Biology
- Dave: Math, Biology

The conflict graph would have edges between:
- Math ↔ Physics (Alice, Dave)
- Math ↔ Biology (Dave)
- Physics ↔ Chemistry (Bob)
- Chemistry ↔ Biology (Carol)

The greedy coloring might assign:
- Time Slot 1: Physics, Biology
- Time Slot 2: Math, Chemistry

## Learning Outcomes

This project demonstrates:
- Graph representation of real-world problems
- Conflict graph construction
- Greedy algorithms for NP-hard problems
- Approximation algorithms
- Graph visualization techniques
- Web development with vanilla JavaScript

## Requirements

- Modern web browser with JavaScript enabled
- Internet connection for vis.js CDN (works offline once loaded)

## License

This project is for educational purposes.