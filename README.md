# ε-NFA to DFA Simulator – Automata Studio

## 1. Overview: What does the simulator do?

Automata Studio is a web-based simulator that converts an **ε-NFA (Epsilon Non-Deterministic Finite Automaton) into an equivalent DFA (Deterministic Finite Automaton)** using the Subset Construction Algorithm.

The simulator visually demonstrates each stage of the conversion process, helping users understand how finite automata work.

It performs the following steps:
- Calculates the ε-closure of each state.
- Converts the ε-NFA into an equivalent ε-free NFA.
- Applies the Subset Construction Algorithm to generate a DFA.
- Displays the resulting automata and transition table.
- Provides step-by-step animation to understand the conversion process.

## 2. Supported Features: Implemented Operations

The simulator provides the following features:

- **ε-Closure Calculation:** Finds all states reachable from a given state using zero or more ε-transitions.
- **Move Operation:** Determines the set of states reachable from a given state or state set using a particular input symbol.
- **ε-NFA to ε-Free NFA Conversion:** Removes epsilon transitions using epsilon closures.
- **Subset Construction:** Converts the resulting NFA into an equivalent DFA.
- **Transition Table:** Displays DFA states and their corresponding transitions.
- **Automata Visualization:** Displays the NFA and DFA diagrams side by side.
- **Step-by-Step Execution:** Animates the conversion process and highlights the currently processed state and transition.
- **State Naming Options:** Allows different naming conventions for DFA states.
- **Dead State Handling:** Represents the empty subset (∅) as a dead state when required.
- **Keyboard Controls:** Supports Space for play/pause, Left and Right arrows for stepping, and Home and End for navigation.
- **Copy Options:** Allows users to copy a shareable link and the resulting DFA as text.

## 3. Technology Stack and Dependencies

The project is implemented as a web-based application.

Technology stack:
- **Frontend:** HTML, CSS and JavaScript (confirm against the source files).
- **Automata Theory:** Finite Automata and Subset Construction Algorithm.
- **Visualization:** Interactive automata diagrams and animated transitions.
- **Deployment:** Vercel.

Dependencies and versions:
- JavaScript: Version to be confirmed.
- HTML5 and CSS3: Browser-supported standards.
- External libraries: To be confirmed from the project source files.

## 4. Installation

Follow these steps to run the project locally:

1. Clone the project repository:

   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory:

   ```bash
   cd <project-folder>
   ```

3. Install dependencies if a package.json file is present:

   ```bash
   npm install
   ```

4. Start the development server using the project's configured command:

   ```bash
   npm run dev
   ```

5. Open the local URL displayed in the terminal.

**Note:** If the project is implemented as a static HTML/CSS/JavaScript application without a build system, open its HTML entry file directly in a browser instead. The exact setup depends on the repository structure.

## 5. How to Run

The deployed application can be accessed here:

https://automata-simulator-ashen.vercel.app/subset.html

Steps to use the simulator:

1. Open the application in a web browser.
2. Enter or configure the ε-NFA.
3. Select the required visualization mode: NFA and DFA, NFA only, or DFA only.
4. Choose the desired DFA state-naming convention.
5. Click the Convert button to begin the conversion.
6. Observe the ε-closure calculations and the equivalent ε-free NFA.
7. Follow the subset construction process as DFA states are discovered.
8. View the final DFA diagram and transition table.
9. Use the playback controls to move through individual conversion steps.

## 6. Example: Sample Automaton Definition, Input and Output

**Input:**

An example ε-NFA consists of:
- A finite set of states (Q).
- An input alphabet (Σ).
- A transition function (δ).
- An initial state (q0).
- A set of final states (F).
- Optional ε-transitions.

The user enters or configures the automaton in the simulator.

**Processing:**

The simulator:
1. Calculates the ε-closure of the initial state.
2. Applies the move operation for each input symbol.
3. Calculates the ε-closure of the resulting states.
4. Creates new DFA states from the discovered subsets.
5. Repeats the process until no new subsets are generated.

**Output:**

- Equivalent ε-free NFA.
- DFA state transition table.
- Final DFA diagram.
- Accepting states and dead state, if applicable.

The resulting DFA recognizes the same language as the original ε-NFA.

## 7. Project Structure: Modules and Responsibilities

The project is organized around the following functional responsibilities. Exact filenames should be updated according to the source repository.

| Module | Responsibility |
|---|---|
| Input Module | Accepts and manages the automaton definition. |
| ε-Closure Module | Calculates states reachable through epsilon transitions. |
| Move Function | Finds reachable states for a given input symbol. |
| NFA Conversion Module | Generates the equivalent epsilon-free NFA. |
| Subset Construction Module | Generates DFA states and transitions. |
| Transition Table Module | Displays the generated DFA transition table. |
| Visualization Module | Draws the NFA and DFA diagrams. |
| Animation Module | Demonstrates the conversion step by step. |
| Result Module | Displays the final DFA and provides copy functionality. |

## 8. Testing

The simulator can be tested using different automata configurations.

**Test cases:**

1. **NFA without epsilon transitions:** Verify that the simulator handles a normal NFA correctly.
2. **ε-NFA with multiple epsilon transitions:** Verify correct ε-closure calculation.
3. **Multiple reachable states:** Check whether the move operation returns all reachable states.
4. **Multiple accepting states:** Verify that DFA subsets containing at least one accepting NFA state are marked accepting.
5. **Dead state:** Verify correct handling of the empty subset (∅).
6. **Subset generation:** Ensure that new DFA states are generated until all reachable subsets have been processed.
7. **Transition table:** Verify that the displayed transitions match the generated DFA.
8. **Animation controls:** Check play, pause, next-step, previous-step, Home and End controls.

**Expected Behavior:**

The generated DFA should be equivalent to the original ε-NFA in terms of accepted language. Every reachable DFA subset should have the correct transitions, and accepting states should be identified correctly.

## 9. Known Limitations and Troubleshooting

- Incorrect automaton input may result in unexpected conversion output.
- Large automata can generate many DFA states because subset construction may produce up to 2ⁿ subsets for n NFA states.
- Complex automata may require additional time for visualization and animation.
- The simulator requires a modern web browser with JavaScript enabled.
- If the conversion does not start, check the automaton input and ensure that the Convert action is triggered.
- If the visualization is not displayed correctly, refresh the page or try another supported browser.

## 10. Team Contributions and Acknowledgements

The project was developed collaboratively as part of the Automata Theory coursework.

**Team Contributions:**
- Implementation of automata conversion operations.
- Development of ε-closure and move functionality.
- Implementation of the Subset Construction Algorithm.
- Development of interactive visualizations and transition tables.
- Testing and verification of the generated DFA.
- Documentation and project integration.

**Acknowledgements:**

We would like to thank our faculty and mentors for their guidance and support throughout the development of this project.

The project helped us understand the practical implementation of finite automata, epsilon transitions, and the conversion of nondeterministic finite automata into deterministic finite automata.