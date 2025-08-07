# Better LaTeX Problem Set Template

A specialized LaTeX template designed for mathematical problem sets and homework assignments, featuring enhanced environments optimized for academic mathematical writing, prioritizing readability and structure while maintaining academic formatting standards.

## Key Features

### Enhanced Solution Environments

The template includes two distinct solution environments to accommodate different problem structures:

- **`soln`** - For multi-part problems with line break after "Solution."
  ```latex
  \begin{soln}
  (a) First part of the solution...
  (b) Second part of the solution...
  \end{soln}
  ```

- **`solution`** - For single-part problems with inline formatting
  ```latex
  \begin{solution}
  I claim that the statement holds because...
  \end{solution}
  ```

### Nested Proof Environments

Support for hierarchical proof structures with distinct QED symbols:

- **`subproof`** - Uses ■ (blacksquare) symbol for intermediate proofs
- **`subsubproof`** - Uses ♣ (clubsuit) symbol for deeply nested proofs

These environments are particularly useful for complex proofs requiring lemmas or intermediate results.

### Automatic Problem Numbering

Seamless integration with LaTeX sectioning for problem organization:
- Problems are automatically numbered using `\section{}`
- Full table of contents integration
- Consistent formatting with "Problem #N" headers

### Specialized Mathematical Environments

Additional environments for mathematical exposition:

- **`claim`** - For stating intermediate claims
- **`conclusion`** - For summarizing results
- **`remark`** - Highlighted observations with subtle visual styling
- **`extension`** - Color-coded extensions and generalizations

## Example Output

The template produces clean, professional mathematical documents suitable for academic submission. See the example images for visual reference of the compiled output.
![image](https://github.com/PLASTA0728/Math-Homework-Problem-Set-Template/blob/main/example-page-0001.jpg)
![image](https://github.com/PLASTA0728/Math-Homework-Problem-Set-Template/blob/main/example-page-0002.jpg)
