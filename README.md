# Wumpus World Logic Agent - Propositional Resolution Engine

This project is a web-based implementation of an intelligent agent for the **Wumpus World** environment. It utilizes **Propositional Logic** and a **Resolution-based Inference Engine** to determine safe moves within a 4x4 grid.

## 🚀 Live Demo
The application is deployed and can be accessed here:(https://dynamic-wumpus-logic-agent-pi.vercel.app/)

## 🧠 Project Overview
The core objective of this project is to demonstrate how a Knowledge-Based Agent (KBA) reasons using logic. When the agent perceives information (e.g., "No Breeze at [1,1]"), the Inference Engine processes this against a set of predefined environment rules to deduce hidden facts, such as identifying safe cells or locating pits.

### Key Features
- **Logic Parser & CNF Converter:** Converts complex propositional sentences into Conjunctive Normal Form (CNF) for resolution.
- **Resolution Refutation Engine:** Implements the Resolution algorithm to prove the safety of adjacent cells by looking for contradictions (empty clauses).
- **Interactive Grid Visualization:** A dynamic 4x4 grid that updates in real-time.
    - 🟩 **Green:** Safe Cells
    - 🟥 **Red:** Confirmed Pits/Wumpus
    - ⬜ **Gray:** Unknown/Unvisited
- **Real-Time Metrics:** Displays the total number of inference steps taken for each logical deduction.

## 🛠️ Technical Stack
- **Backend:** Python (Flask)
- **Frontend:** HTML5, CSS3, JavaScript (ES6)
- **Logic:** Propositional Resolution Algorithm

## 📖 Logic Implementation
The agent follows these steps to make a decision:
1. **Knowledge Representation:** The environment rules (e.g., $B_{1,1} \Leftrightarrow P_{1,2} \vee P_{2,1}$) are stored in the Knowledge Base (KB).
2. **CNF Conversion:** All rules are converted to CNF (e.g., $(\neg B_{1,1} \vee P_{1,2} \vee P_{2,1}) \wedge (\neg P_{1,2} \vee B_{1,1}) \dots$).
3. **Negation of Query:** To prove square $X$ is safe ($\neg P_x$), the engine assumes the opposite ($P_x$).
4. **Resolution Loop:** The engine resolves existing clauses to find an **Empty Clause ($\square$)**. If found, the original query is proven true.

## ⚙️ Installation & Setup
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/wumpus-world-logic.git](https://github.com/RijaFatima92/wumpus-world-logic.git)
Install dependencies:

Bash
pip install flask
Run the application:

Bash
python app.py
Open http://127.0.0.1:5000 in your browser.
