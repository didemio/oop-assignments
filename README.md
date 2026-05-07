# OOP Assignments – C++

A series of 7 progressive C++ assignments completed as part of the **Object-Oriented Programming** course at Riga Technical University. Each assignment builds on the previous one, introducing new OOP concepts step by step.

---

## Assignment 1 – Task Manager

A command-line task management app using `Task` and `TaskList` classes.

**Key concepts:** Encapsulation, class design, lambdas, `std::chrono`

**Features:**
- Create tasks with name, priority (`NORMAL` / `HIGH`), and due date
- Filter tasks using lambda predicates (e.g. show only due tasks)
- Mark tasks as complete and remove done tasks

**Files:** `Task.hpp/cpp`, `TaskList.hpp/cpp`, `Main.cpp`

---

## Assignment 2 – Boat Selection & Search

A boat inventory system with query-object-based search.

**Key concepts:** Encapsulation, query object pattern, sentinel/default return values

**Features:**
- Store boats with type, length, capacity, and manufacture year
- Search by any field (type, length, or year)
- Returns a default "Unknown" boat on no match

**Files:** `Boat.hpp/cpp`, `Selection.hpp/cpp`, `main.cpp`

---

## Assignment 3 – Enum Types & Analytics

Extends the boat system with enum-based types and analytical utility functions.

**Key concepts:** `enum class`, const correctness, reference semantics

**Features:**
- `BoatType` enum for structured type representation
- `max_length()` – finds the longest boat (returns `const Boat&`)
- `avg_length()` – computes average length across the selection

**Files:** `Boat.hpp`, `Selection.hpp/cpp`, `main.cpp`

---

## Assignment 4 – Abstraction Layer & Multi-criteria Search

Introduces a base `Abstraction` class and richer search overloads.

**Key concepts:** Inheritance, composition, function overloading, `std::chrono::year_month_day`

**Features:**
- Generic `Abstraction` base with id, spec, purchase date, sold status
- `Boat` inherits from `Abstraction`
- Search by full object or by individual fields (model, year, price)

**Files:** `Abstraction.hpp/cpp`, `AbstractionSpec.hpp`, `Boat.hpp/cpp`, `Selection.hpp/cpp`, `main.cpp`

---

## Assignment 5 – Smart Pointers & Shared Specs

Refactors ownership model using `std::shared_ptr` and separates specs from items.

**Key concepts:** `std::shared_ptr`, shared ownership, `BoatSpec` as a separate entity

**Features:**
- `BoatSpec` holds model, year, price — shared across multiple boats
- `Boat` stores a `shared_ptr<BoatSpec>`
- Selection searches by matching spec objects

**Files:** `Abstraction.hpp/cpp`, `Boat.hpp/cpp`, `BoatSpec.hpp/cpp`, `Selection.hpp/cpp`, `main.cpp`

---

## Assignment 6 – Virtual Dispatch, Operator Overloading & File I/O

Evolves `Abstraction` into a polymorphic interface and adds CSV persistence.

**Key concepts:** Pure virtual functions, `operator<<` / `operator>>`, file I/O, exception handling

**Features:**
- `Abstraction` becomes a pure virtual interface (`send_to`, `recv_from`, `matches`)
- `operator<<` for clean printing of any `Abstraction`-derived object
- `sel.save("boats.csv")` and constructor loading from CSV
- `operator[]` with `std::out_of_range` exception

**Files:** `Abstraction.hpp/cpp`, `AbstractionSpec.hpp/cpp`, `Boat.hpp/cpp`, `BoatSpec.hpp/cpp`, `Selection.hpp/cpp`, `utilities.hpp/cpp`, `main.cpp`

---

## Assignment 7 – Templates & Mixed-Type Collections

Extends the system to support multiple item types (boats and bikes) in one generic collection.

**Key concepts:** Templates, polymorphism, `std::vector<shared_ptr<Abstraction>>`, multi-type collections

**Features:**
- `Bike` and `BikeSpec` added alongside `Boat`/`BoatSpec`
- `Selection` holds any `Abstraction`-derived object
- Template `show()` function works for any printable type
- CSV save/load for mixed collections

**Files:** `Abstraction.hpp/cpp`, `AbstractionSpec.hpp/cpp`, `Boat.hpp/cpp`, `BoatSpec.hpp/cpp`, `Bike.hpp/cpp`, `BikeSpec.hpp/cpp`, `Item.hpp/cpp`, `Selection.hpp/cpp`, `utilities.hpp/cpp`, `main.cpp`

---

## How to Build (any assignment)

```bash
g++ -std=c++20 *.cpp -o program
./program
```

---

## Tech Stack

- **Language:** C++20
- **Concepts covered:** Encapsulation, Inheritance, Polymorphism, Abstraction, Smart Pointers, Templates, File I/O, Exception Handling
