# Constraint Satisfaction Puzzle Solver

**Description:**  
This project involves solving a constraint satisfaction problem (CSP) in which a grid of black and white circles is completed according to specific constraints. The objective is to fill the grid while ensuring each row and column satisfies the given restrictions on the number and positioning of circles.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Project Structure](#project-structure)
- [Algorithms and Techniques](#algorithms-and-techniques)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview
The main task in this project is to solve a CSP puzzle. The grid (puzzle) should satisfy the following constraints:

1. **Row and Column Count**: Each row and column must contain an equal number of black and white circles.
2. **Adjacency Constraint**: No more than two consecutive circles of the same color can be adjacent in a row or column.
3. **Unique Rows and Columns**: No two rows or columns can be identical.

The program will read the grid dimensions and initial layout from an input file and will apply a CSP-solving algorithm to achieve a valid solution.

---

## Installation
To set up the project locally, follow these steps:

```bash
# Clone the repository
git clone https://github.com/gnozadi/constraint-satisfaction-solver.git

# Navigate to the project directory
cd constraint-satisfaction-solver

# Compile the code
make
```

## Usage
After compiling, you can use the solver with an input file specifying the grid layout.

```bash
# Run the CSP solver
./csp_solver input.txt
```

*Example input file format (`input.txt`):*
- The first line specifies `n` (grid size) and `m` (number of predefined circles).
- The following `m` lines specify the row, column, and color (0 for black, 1 for white) of each predefined circle.

```
8 4
0 1 0
2 3 1
4 5 0
6 7 1
```

## Features
- **CSP Modeling**: Models the grid as a CSP problem with variables, domains, and constraints.
- **Backtracking with Forward Checking**: Uses a backtracking algorithm with forward checking to reduce possible values and improve efficiency.
- **Heuristic Search**: Implements MRV (Minimum Remaining Values) and LCV (Least Constraining Value) heuristics for optimized solving.
- **AC-3 Algorithm**: Uses the AC-3 algorithm for arc consistency to further prune the search space.

## Project Structure
- **csp_solver.c**: Contains the main logic for CSP-solving and constraint enforcement.
- **input_parser.c**: Parses input files and initializes the puzzle grid.
- **Makefile**: Builds the project.

## Algorithms and Techniques
This project uses the following algorithms and heuristics for solving CSPs:

- **Backtracking with Forward Checking**: Reduces potential values based on constraints to avoid invalid assignments early.
- **MRV and LCV Heuristics**: MRV selects variables with the fewest legal values, while LCV selects values that least restrict other variables.
- **AC-3 for Arc Consistency**: Ensures arc consistency by iteratively checking and reducing domains of variable pairs.

## Contributing
Contributions are welcome! To contribute:

1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Make your changes
4. Push to the branch (`git push origin feature-branch`)
5. Open a Pull Request

## License
This project is licensed under the MIT License.
