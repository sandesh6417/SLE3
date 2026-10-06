# 8-Puzzle Solver using BFS and DFS

**Course:** 02AML204 - Introduction to Artificial Intelligence\
**SLE:** SLE-3 - Architectural Design (Full C4 Model)\
**Name:** Sandesh Patil\
**PRN:** 25UAM044\
**Division:** A

## 1. Project Overview

The 8-Puzzle Solver is a search-based Artificial Intelligence system
that finds a path from an initial 8-puzzle state to a target goal state.

The system supports:

-   Breadth-First Search (BFS)
-   Depth-First Search (DFS)

The user provides the initial puzzle state, goal state, and search
method. The Search Engine explores puzzle states using visited-state
tracking and returns the solution path and search result.

This project continues the **8-Puzzle BFS vs DFS** work from SLE-2 and
represents its architecture using the **Full C4 Model**.

## 2. Objectives

-   Represent the 8-puzzle as searchable states.
-   Find a path from the initial state to the goal state.
-   Implement BFS and DFS search strategies.
-   Avoid unnecessary repeated exploration using visited-state tracking.
-   Understand the difference between BFS and DFS.
-   Design the system using all four C4 levels.

## 3. System Architecture

### Level 1 - Context Diagram

The user provides the initial 8-puzzle state and selects BFS or DFS. The
solver processes the request and returns the solution path and search
result.

![C4 Context Diagram](sle3_context.png)

### Level 2 - Container Diagram

Main containers:

1.  Input Module
2.  Puzzle Representation
3.  Search Engine
4.  BFS Module
5.  DFS Module
6.  Visited / Memory Module
7.  Output Module

![C4 Container Diagram](sle3_container.png)

### Level 3 - Component Diagram

The main container selected for component-level design is the Search
Engine.

Its components are:

-   Algorithm Controller
-   Frontier / Recursion Control
-   Visited Set Manager
-   Goal Test
-   Path Reconstructor

![C4 Component Diagram](sle3_component.png)

### Level 4 - Code Level

  -----------------------------------------------------------------------
  Function / Data                     Responsibility
  ----------------------------------- -----------------------------------
  `PuzzleState`                       Stores the 8-puzzle board state and
                                      parent information.

  `bfs_search(start, goal)`           Performs Breadth-First Search using
                                      a queue and visited set.

  `dfs_search(start, goal)`           Performs Depth-First Search using
                                      recursion/stack and visited states.

  `get_neighbors(state)`              Generates valid next puzzle states.

  `is_goal(state, goal)`              Checks whether the current state
                                      matches the goal state.

  `reconstruct_path(state)`           Builds the final solution path.
  -----------------------------------------------------------------------

## 4. Search Algorithms

**BFS:** Explores states level by level using a queue.

**DFS:** Explores one branch deeply before moving to another branch,
using recursion or a stack.

## 5. Project Flow

``` text
User
  ↓
Input Module
  ↓
Puzzle Representation
  ↓
Search Engine
  ↓
BFS / DFS
  ↓
Visited / Memory
  ↓
Goal Test
  ↓
Path Reconstruction
  ↓
Output / Solution Path
```

## 6. Design Decisions

-   BFS and DFS are grouped under one Search Engine because both solve
    the same 8-puzzle search problem using different traversal
    strategies.
-   Input, processing, memory, and output are separated to keep the
    design clear.
-   Visited-state tracking is used to reduce repeated exploration.
-   The component-level design focuses only on the Search Engine.

## 7. SLE-2 to SLE-3 Connection

**SLE-2:** BFS vs DFS search/performance work on the 8-Puzzle problem.

**SLE-3:** Full C4 architectural design of the same 8-Puzzle Solver.

The project therefore continues from search/performance analysis to
software architecture.

## 8. AI Contribution

**AI Tool Used:** ChatGPT

AI was used to help organize the C4 architecture, prepare concise
explanations, structure the documentation, and improve the descriptions
of the diagrams.

The student selected and reviewed the 8-Puzzle BFS vs DFS system,
checked the algorithm and component responsibilities, and understood the
final architecture for evaluation.

## 9. Project Files

``` text
8-Puzzle-Solver/
├── README.md
├── CONTRIBUTION_LOG.md
├── sle3_context.png
├── sle3_container.png
├── sle3_component.png
└── project source code files
```

## 10. Conclusion

The Full C4 Model represents the 8-Puzzle Solver from user interaction
down to its main functions. The architecture separates input, search
processing, puzzle/visited memory, and output while showing the roles of
BFS and DFS.

This project connects the work completed in SLE-2 with the architectural
design required for SLE-3.
