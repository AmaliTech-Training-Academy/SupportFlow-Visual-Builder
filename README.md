# SupportFlow-Visual-Builder
This challenge is designed to test your ability to bridge Computer Science fundamentals with Modern Frontend Engineering.

## 1. Business Scenario & Context
**Client:** SupportFlow AI  
**Industry:** Customer Support Automation (Chatbots)  

**The Problem:** SupportFlow helps companies build automated "Help Bots" (e.g., "Press 1 for Billing, 2 for Tech Support"). Currently, their configuration is done via a messy Excel spreadsheet. It is error-prone, hard to visualize, and frustrating for non-technical managers.

**Your Role:** You are the new Frontend Engineer. The Product Manager wants a **Visual Decision Tree Editor** where users can see their conversation flow as a flowchart, edit the questions in real-time, and "test drive" the bot instantly.

---

## 2. The Assignment Stages
This is a **hybrid design/engineering challenge**. You are expected to demonstrate competence in both visual design logic and complex DOM manipulation.

### Phase 1: The Design System (Figma/Penpot)
**Before writing code, you must design the visual language of the tool.**

* **Deliverable:** A link to your design file (Figma, Penpot, or Sketch) or a PDF export of your design frames.
* **Requirement:** Your design file must include a dedicated **"Design System" page** that defines:
    * **Canvas:** How does the background look? (e.g., Dot grid, infinite canvas feel).
    * **Node Cards:** Design the "Question Card." It needs a distinct Header (ID), Body (The Question), and Ports/Buttons (The Answers).
    * **Connectors:** How do you visually represent the link between Question A and Question B? (e.g., Curved Bezier lines, straight arrows, or elbow connectors).
    * **Color Semantics:** distinct visual styles for "Start Node," "Standard Node," and "End/Leaf Node."

### Phase 2: The Implementation (Code)
**Build the "Flow Builder" using your design system.**

* **Constraint 1 (Critical):** You **cannot** use Flowchart/Graph libraries like `react-flow`, `jsPlumb`, or `mermaid.js`. You must build the node rendering and line connection logic yourself to prove you understand DOM coordinates and SVG/Canvas drawing.
* **Constraint 2:** Do not use component libraries like Material UI or Bootstrap. (Tailwind is allowed only if you use it to build custom components).

---

## 3. User Stories & Acceptance Criteria

### Core Features (Required)

#### Story 1: The Visual Graph (The "CS" Challenge)
> "As a user, I want to see my conversation logic as a connected flowchart, not a list."

* **AC 1:** The app renders "Nodes" (questions) based on the provided JSON data.
* **AC 2:** The Nodes are positioned absolutely on the canvas (using the x/y coordinates provided in the JSON).
* **AC 3:** Visual lines (SVG or HTML Canvas) connect a Parent Node to its Child Nodes based on the flow logic.

#### Story 2: The Editor
> "As a user, I need to update the text when our support policies change."

* **AC 1:** Clicking a Node opens an "Edit Panel" or turns the card into an editable form.
* **AC 2:** Users can edit the "Question Text" and the changes reflect immediately on the canvas.
* **AC 3:** (Constraint) You do not need to save changes to a permanent database. Managing local state (in-memory) is sufficient.

#### Story 3: The "Preview" Mode (The Runner)
> "As a manager, I want to test the bot experience as if I were a real customer."

* **AC 1:** A "Play" button toggles the UI from "Editor View" (Flowchart) to "Preview Mode" (Chat Interface).
* **AC 2:** In Preview Mode, the app displays the Start Node's question.
* **AC 3:** When the user selects an answer, the app traverses the graph to show the next node.
* **AC 4:** Show a "Restart" button when a leaf node (end of conversation) is reached.

### The "Wildcard" Feature (Required)

#### Story 4: The Innovation Clause
> "As a developer, I want to add one feature that makes this tool indispensable."

* **Task:** Identify a missing feature that improves the *Editor* experience.
* **Examples:**
    * **Drag & Drop:** Allow users to drag nodes to new positions (updates x/y coords).
    * **Validation:** Highlight "Orphan Nodes" (nodes that have no parent) in red.
    * **Zoom/Pan:** Ability to zoom in on the canvas.
* **AC 1:** Implement **one** additional feature of your choice.
* **AC 2:** Document your choice in the README.

---

## 4. Technical Requirements
* **Data:** Use the `flow_data.json` file provided in this repo.
* **Tech Stack:** React, Vue, Svelte, or Vanilla JS.
* **Key Challenge:** Drawing the connecting lines is the hardest part. You will likely need to calculate the center points of the HTML elements to draw SVG lines between them.

---

## 5. Submission Instructions
1.  **Fork** this repository.
2.  Complete the code in your fork.
3.  Update this `README.md` with:
    * Setup instructions.
    * Link to your Design File.
    * Explanation of how you calculated the connection lines (The Math/Logic).
    * Explanation of your **Wildcard Feature**.
4.  Submit your repo link via the online form.
