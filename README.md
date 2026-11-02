# 📐 Linear Programming & Optimisation Solver

A **C# console application** developed as a **Belgium Campus LPR381 group project**. The application reads optimisation models from text files, provides a choice of solving methods, displays calculation steps and exports results to a text report.

---

## 🎯 Project Overview

The project explores linear, integer and single-variable non-linear optimisation through a menu-driven application.

It focuses on:
- Loading and validating mathematical models from text files.
- Solving linear and integer programming problems.
- Displaying canonical forms and solver iterations.
- Exploring sensitivity analysis and duality.
- Exporting calculation steps and results.

---

## 🛠 Tools & Technologies

- **C#** and **.NET 10**
- Console-based user interface
- **xUnit** test project
- Microsoft.NET.Test.Sdk and Coverlet collector
- Text-file model input and report output

---

## ✨ Key Features

| Method / Feature | Purpose |
| --- | --- |
| Primal Simplex | Solve linear programming models using tableau operations |
| Dual Simplex | Restore feasibility where the solver's applicable conditions are met |
| Revised Primal Simplex | Solve using basis-matrix calculations |
| Branch & Bound Simplex | Explore bounds for integer programming models |
| Cutting Plane | Add Gomory cuts for integer programming |
| Branch & Bound Knapsack | Solve suitable binary knapsack models |
| Golden Section Search | Search an interval for an optimum of a suitable single-variable function |
| Sensitivity analysis | Explore coefficient, RHS, variable and structural changes |
| Duality | Construct and solve a dual model and inspect the duality gap |
| Report export | Save working and results to a text file |

Golden Section Search is intended for a unimodal function on the chosen interval. The included example models cover maxima, minima and trigonometric objectives.

---

## 📁 Repository Contents

| File / Folder | Description |
| --- | --- |
| `LPR381/LPR381.slnx` | Solution containing the console app, core library and tests |
| `LPR381/LPR381/` | Console entry point, menus and sample models |
| `LPR381/LPR381.Core/Algorithms/` | Solver implementations and algorithm registry |
| `LPR381/LPR381.Core/Simplex/` | Canonical form, tableaux, pivot rules and matrix operations |
| `LPR381/LPR381.Core/Sensitivity/` | Sensitivity and duality operations |
| `LPR381/LPR381.Core/Models/` | Model, constraint and variable classes |
| `LPR381/LPR381.Core/IO/` | Model parsing, formatting and report writing |
| `LPR381/LPR381.Core/NonLinear/` | Non-linear model and expression support |
| `LPR381/LPR381.Tests/` | Existing automated tests |
| `LPR381/LPR381/samples/` | Valid examples, edge cases and deliberately invalid inputs |
| `docs/Input_Format.md` | Detailed model input syntax |
| `run.bat` | Original Windows build-and-run launcher |
| `README.md` | Project overview and setup instructions |

---

## 🚀 Getting Started

### Requirements

Install the **.NET 10 SDK**, matching the `net10.0` target declared in all three project files. If using Visual Studio, use an installation that supports both .NET 10 and the `.slnx` solution format.

### Build and run

Download and extract the folder, then open a terminal in the repository root:

```bash
dotnet build LPR381/LPR381.slnx
dotnet run --project LPR381/LPR381/LPR381.csproj
```

On Windows, you can also launch `run.bat` after installing the SDK.

### Open in Visual Studio

1. Open **`LPR381/LPR381.slnx`** through **Open → Project/Solution**.
2. Set **LPR381** as the startup project.
3. Start the application and load a model using the menu.
4. Select an applicable solver, inspect its working and export a report as needed.

`LPR381.Core` is a library and `LPR381.Tests` is a test project; start the console application rather than either of these projects.

### Run the existing tests

```bash
dotnet test LPR381/LPR381.slnx
```

The suite covers model parsing, canonical form construction, simplex calculations, solver algorithms, Golden Section Search and sensitivity operations. Package restore requires access to the declared NuGet dependencies.

---

## 📝 Example Model

```text
max +3 +2
+2 +1 <=100
+1 +1 <=80
+1 +0 <=40
+ +
```

This describes maximising `3x₁ + 2x₂` subject to three constraints, with both variables non-negative. It is included as `santa.txt`.

The final line specifies variable restrictions such as `+`, `-`, `urs`, `int` and `bin`. See [the input guide](docs/Input_Format.md) for the complete format and non-linear examples.

---

## 💡 Sample Problems

- **Linear models:** `santa.txt`, `equality.txt`, `minimisation.txt`.
- **Integer and binary models:** `integer.txt`, `knapsack.txt`.
- **Special cases:** `infeasible.txt`, `unbounded.txt`.
- **Parser validation:** `broken_*.txt` files are deliberately invalid.
- **Non-linear examples:** `golden.txt`, `golden_quadratic.txt`, `golden_minimum.txt`.

---

## 🧠 Skills Demonstrated

- Mathematical modelling and optimisation algorithms.
- Object-oriented programming and modular application design.
- Matrix and tableau operations.
- Input parsing, validation and error handling.
- Sensitivity analysis and duality.
- Report generation and automated testing.

---

## 📚 Project Background

Developed as a **group project for Linear Programming 381 (LPR381)** at **Belgium Campus**. The repository includes the shared application, core algorithms, sample models and test suite.

### Verification

This upload package preserves the original source, project files, tests, samples and launcher. File integrity and local project references were checked during packaging. The .NET SDK is unavailable in the packaging environment, so no build, test-pass count or solver-result verification is claimed for this version.

---

## 🌷 Portfolio Owner

**Elaine Potgieter**  
Bachelor of Computing Student | Data Science Specialisation  
SQL • Power BI • Python • Business Analysis
