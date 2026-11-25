# NFA to DFA Simulator – Automata Studio

## 1. Overview: What Does the Simulator Do?

Automata Studio is an interactive web-based application designed to convert a **Non-Deterministic Finite Automaton (NFA) into an equivalent Deterministic Finite Automaton (DFA)**.

The simulator implements the Subset Construction Algorithm to demonstrate how multiple possible NFA states are combined into individual DFA states.

It helps students understand the conversion process through visual representations, transition tables, and step-by-step execution.

The main objective is to simplify the understanding of automata conversion through an interactive learning environment.

## 2. Supported Features: Implemented Operations

The simulator supports the following operations:

- **NFA Input:** Defines the states, input alphabet, initial state, final states, and transitions of an NFA.
- **ε-Closure Calculation:** Finds all states reachable from a particular state using zero or more epsilon transitions.
- **Move Operation:** Determines the set of states reachable from a given state or set of states using a particular input symbol.
- **Subset Construction Algorithm:** Converts an NFA into an equivalent DFA by treating sets of NFA states as individual DFA states.
- **DFA State Generation:** Automatically generates new DFA states whenever new subsets are discovered.
- **Transition Table Generation:** Creates a table representing the transitions between the generated DFA states.
- **Final State Identification:** Identifies DFA accepting states based on whether their corresponding subsets contain at least one accepting NFA state.
- **Dead State Handling:** Handles empty state subsets when required during conversion.
- **Automata Visualization:** Provides a visual representation of the conversion and resulting automata.
- **Step-by-Step Execution:** Helps users understand the intermediate stages of the conversion algorithm.

## 3. Technology Stack and Dependencies

The project uses the following technologies:

- **Frontend:** HTML5, CSS3 and JavaScript.
- **Backend/Server:** Node.js.
- **Core Algorithm:** Subset Construction Algorithm.
- **Automata Concepts:** NFA, DFA, ε-closure, Move Function and Transition Functions.


### Dependencies

Dependencies are managed through npm using `package.json`.

The project includes the following npm scripts:

- `npm start` – Starts the Node.js server using `server.js`.
- `npm test` – Executes the project test file using `test.js`.

Exact package versions can be found in `package.json` and `package-lock.json`.

## 4. Installation

Follow these steps to install and run the project locally.

**Step 1: Clone the repository**

```bash
git clone https://github.com/vidhiujjwal1307/Automata-Studio.git
```

**Step 2: Navigate to the project directory**

```bash
cd Automata-Studio
```

**Step 3: Install dependencies**

```bash
npm install
```

**Step 4: Start the application**

```bash
npm start
```

**Step 5: Open the application**

Open the local URL displayed in the terminal in your web browser.

## 5. How to Run

The deployed simulator can be accessed at:

https://automata-simulator-ashen.vercel.app/subset.html

### Steps to Use the Simulator

1. Open the NFA to DFA simulator.
2. Provide the NFA definition, including states, alphabet, initial state, final states, and transitions.
3. Specify epsilon transitions wherever required.
4. Start the conversion process.
5. Calculate the epsilon closure of the initial state.
6. Apply the Move operation for each input symbol.
7. Calculate epsilon closures of the resulting state sets.
8. Generate new DFA states using the Subset Construction Algorithm.
9. Continue until all reachable subsets have been processed.
10. View the resulting DFA and its transition table.

## 6. Example: Sample Automaton Definition, Input and Output

### Example NFA

Consider an NFA with the following components:

- States: Q = {q0, q1}
- Alphabet: Σ = {a, b}
- Initial State: q0
- Final State: F = {q1}

Transitions:

| Current State | Input | Next State |
|---|---|---|
| q0 | a | q0, q1 |
| q0 | b | q0 |
| q1 | a | ∅ |
| q1 | b | q1 |

### Conversion Process

**Step 1: Initial DFA State**

The initial DFA state is the set containing the initial NFA state.

A = {q0}

**Step 2: Apply Move Operation**

For input symbol `a`:

Move({q0}, a) = {q0, q1}

Therefore, a new DFA state is generated:

B = {q0, q1}

For input symbol `b`:

Move({q0}, b) = {q0}

Therefore, the resulting DFA state is A.

**Step 3: Generate Remaining Transitions**

For state B = {q0, q1}:

- On input `a`, the resulting set is {q0, q1}.
- On input `b`, the resulting set is {q0, q1}.

### Final DFA Transition Table

| DFA State | a | b |
|---|---|---|
| A = {q0} | B | A |
| B = {q0, q1} | B | B |

### Final States

Since B contains the NFA final state q1, B is an accepting DFA state.

The generated DFA is equivalent to the original NFA.

*Note: This is an illustrative example without epsilon transitions. The simulator's ε-closure operation is used when epsilon transitions are present.*

## 7. Project Structure: Modules and Responsibilities

The project is organized into different modules responsible for handling the automata conversion process.

| Module | Responsibility |
|---|---|
| `server.js` | Starts the Node.js server and serves the application. |
| `subset.html` | Provides the NFA-to-DFA simulator interface. |
| NFA Input Module | Handles the NFA states, alphabet and transitions. |
| `move()` Function | Calculates reachable states for a given input symbol. |
| ε-Closure Function | Finds all states reachable through epsilon transitions. |
| Subset Construction Module | Generates DFA states and their transitions. |
| Transition Table Module | Displays the generated DFA transition table. |
| Visualization Module | Displays the automata and conversion results. |
| `test.js` | Runs the project's automated test cases. |

## 8. Testing

Testing is performed to verify the correctness of the NFA-to-DFA conversion process.

The project includes a test script that can be executed using:

```bash
npm test
```

### Important Test Cases

1. **NFA without epsilon transitions:** Verify the conversion of a basic NFA.
2. **NFA with epsilon transitions:** Verify the correct calculation of epsilon closures.
3. **Multiple transitions:** Check whether the Move operation identifies all reachable states.
4. **Multiple final states:** Verify the identification of accepting DFA states.
5. **New subset generation:** Check whether new DFA states are generated correctly.
6. **Repeated subsets:** Ensure previously generated subsets are not duplicated.
7. **Dead state:** Verify the handling of empty subsets.
8. **Transition table:** Ensure that all generated transitions are represented correctly.

### Expected Results

- The generated DFA should recognize the same language as the original NFA.
- Every reachable subset should be processed.
- DFA accepting states should be identified correctly.
- The transition table should represent the generated DFA accurately.

## 9. Known Limitations and Troubleshooting

- The number of DFA states can increase significantly as the number of NFA states increases.
- Incorrect or incomplete NFA input can affect the conversion results.
- Complex automata may require additional processing time.
- The application requires JavaScript-enabled browser support.
- If the server fails to start, verify that Node.js and npm are installed correctly.
- If dependencies are missing, execute `npm install`.
- If `npm run dev` does not work, use `npm start`, as configured in the project's package.json.

## 10. Team Contributions and Acknowledgements

The project was developed collaboratively as part of the Automata Theory coursework.

### Team Contributions

- Designing and developing the NFA-to-DFA simulator.
- Implementing the Move and ε-Closure operations.
- Implementing the Subset Construction Algorithm.
- Generating DFA states and transition tables.
- Developing the visual interface for automata conversion.
- Testing the conversion process with different NFA configurations.
- Preparing project documentation.

### Acknowledgements

We would like to express our gratitude to our faculty members for their guidance and support throughout the development of this project.

This project provided practical experience in implementing automata theory concepts and understanding the mathematical relationship between Non-Deterministic and Deterministic Finite Automata.
