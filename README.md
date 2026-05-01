# Exam Scheduling with Graph Coloring

A single-file web application demonstrating how graph coloring solves exam scheduling problems. Built with vanilla HTML/CSS/JavaScript and [vis.js](https://visjs.org/) for graph visualization.

## Live Demo

**[https://graphtheory433-finale.vercel.app](https://graphtheory433-finale.vercel.app)**

No installation needed — just open the link in any modern browser.

## Running Locally

If you want to run it from source, download or clone this repository and open `index.html` in any modern web browser:

- **Mac**: double-click `index.html` in Finder, or run `open index.html` in Terminal
- **Windows**: double-click `index.html` in File Explorer
- **Linux**: run `xdg-open index.html` in a terminal

> If the graph area appears blank, your browser may be blocking CDN requests over `file://`. Fix it by serving locally:
> ```bash
> python3 -m http.server 8080
> ```
> Then visit `http://localhost:8080`.

## How to Use

1. **Add Courses** — type a course name and click "Add Course" to create nodes in the graph
2. **Add Students** — type a student name, check the courses they are enrolled in, and click "Add Student"
3. **Build Graph & Color** — click the button to construct the conflict graph and compute a schedule
4. **Read the output** — the colored graph shows which courses conflict, and the schedule below lists time slots with no conflicts

You can add or remove courses and students at any time, then click "Build Graph & Color" again to update the result.

## The Mathematics

The app models the exam scheduling problem as a graph coloring problem:

- **Nodes** represent courses
- **Edges** connect two courses if they share at least one student (a conflict)
- **Colors** represent time slots — the goal is to assign time slots so no two conflicting courses share one
- **Chromatic number** — the minimum number of colors (time slots) needed

The algorithm used is greedy coloring ordered by decreasing degree: courses with the most conflicts are scheduled first. This is a well-known heuristic that often finds good solutions but does not guarantee the optimal (minimum) number of time slots.

## Example

Courses: Math, Physics, Chemistry, Biology

| Student | Courses |
|---------|---------|
| Alice   | Math, Physics |
| Bob     | Physics, Chemistry |
| Carol   | Chemistry, Biology |
| Dave    | Math, Biology |

Conflict edges: Math–Physics, Math–Biology, Physics–Chemistry, Chemistry–Biology

Greedy coloring result:
- **Time Slot 1**: Physics, Biology
- **Time Slot 2**: Math, Chemistry

## Requirements

- Any modern browser (Chrome, Firefox, Safari, Edge)
- Internet connection on first load (for vis.js CDN)
