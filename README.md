# Roo Fiction Modes

This repository contains custom modes for Roo designed to assist with narrative fiction writing.

## Modes Included

Two interconnected modes are provided:

1.  **Narrative Planner (`narrative-planner`):** An expert in story development, character creation, and world-building. Helps structure narratives, develop characters and settings, and manage complex projects.
2.  **Narrative Writer (`narrative-writer`):** A skilled creative writer and prose stylist. Helps translate plans into polished prose, craft dialogue and descriptions, refine style, and revise text.

## Installation & Usage

You can install these modes in two ways:

**1. Workspace-Specific Installation (Recommended for project-based use):**

This method makes the modes available only when you open this specific `roo-fiction` folder (or repository) in VS Code.

*   **How it works:** Roo automatically detects the `.roomodes` file located in the root of this repository.
*   **Steps:**
    1.  **Clone the Repository:**
        ```bash
        git clone <repository-url> roo-fiction
        cd roo-fiction
        ```
        *(Replace `<repository-url>` with the actual URL of this repository)*
    2.  **Open in VS Code:** Open the `roo-fiction` folder in Visual Studio Code.
    3.  **Activate Modes:** The "Narrative Planner" and "Narrative Writer" modes should automatically appear in Roo's mode selection dropdown for this workspace.
        *If they don't appear immediately, try restarting VS Code or using the "Roo: Reload Custom Modes" command from the command palette (Cmd+Shift+P or Ctrl+Shift+P).*
    4.  **Start Planning or Writing:** Select the desired mode to use it within this project.

**2. Global Installation (Makes modes available in all VS Code workspaces):**

This method adds the modes to your global Roo configuration, making them accessible regardless of which folder or project you have open.

*   **Global Configuration File Location (macOS):**
    `~/Library/Application Support/Code/User/globalStorage/rooveterinaryinc.roo-cline/settings/custom_modes.json`
    *(Note: The `Library` folder might be hidden by default. You can access it via Finder's "Go" menu while holding the Option key, or by using the "Go to Folder..." command (Cmd+Shift+G) and pasting the path.)*

*   **Steps:**
    1.  **Locate the Global File:** Find the `custom_modes.json` file at the path mentioned above. If it doesn't exist, Roo might create it automatically on startup, or you might need to create the directory structure and the file yourself with the basic structure: `{ "customModes": [] }`.
    2.  **Copy Mode Definitions:** Open the `.roomodes` file from this repository. Copy the two JSON objects inside the `"customModes": [...]` array (one for `narrative-planner` and one for `narrative-writer`).
    3.  **Edit Global File:** Open the global `custom_modes.json` file.
    4.  **Paste Mode Definitions:** Paste the copied mode definition objects into the `"customModes": [...]` array in the global file. Ensure the final JSON structure is valid (e.g., make sure objects are separated by commas if there are existing modes).
        *Example structure after adding:*
        ```json
        {
          "customModes": [
            // ... any existing global modes ...,
            {
              "slug": "narrative-planner",
              "name": "Narrative Planner",
              // ... rest of planner definition ...
            },
            {
              "slug": "narrative-writer",
              "name": "Narrative Writer",
              // ... rest of writer definition ...
            }
          ]
        }
        ```
    5.  **Save and Reload:** Save the global `custom_modes.json` file. Restart VS Code or use the "Roo: Reload Custom Modes" command for the changes to take effect. The modes should now be available in all your workspaces.

**Important Note:** If a mode with the same `slug` exists in both the global file and a workspace's `.roomodes` file, the workspace version will take precedence for that specific workspace.


---

## Mode Documentation

### 1. Narrative Planner (`narrative-planner`)

**Purpose:**
The Narrative Planner mode acts as an expert in story development, character creation, and world-building. It focuses on establishing the structural and conceptual foundation of a narrative. It helps writers organize ideas, develop compelling plots and characters, maintain consistency across story elements, and overcome creative blocks during the planning phase.

**Key Capabilities:**
*   **Story Structuring:** Outlining plots, defining narrative arcs (for short stories, novels, or series).
*   **Character Development:** Creating detailed character profiles, mapping relationships, and tracking character arcs.
*   **World-Building:** Developing settings, history, cultures, and systems (like magic or technology).
*   **Project Scoping:** Adapting planning approach based on project size (short story, novella/novel, epic series) and suggesting appropriate file structures.
*   **Template Provision:** Offering detailed Markdown templates for various planning documents (outlines, character sheets, timelines, world bibles, etc.).
*   **Complexity Management:** Guiding users on managing large projects with techniques like cross-referencing, indexing, and continuity tracking.
*   **Workflow Guidance:** Providing structured workflows tailored to different project scales.

**Allowed Operations:**
*   Read files (`read` group).
*   Edit specific file types: Markdown (`.md`), Text (`.txt`), JSON (`.json`).
*   Execute commands (`command` group).

**Workflow & Structure:**
This mode follows a highly structured approach detailed in its `customInstructions`. It emphasizes:
1.  **Scaling:** Adapting the planning structure based on the project's word count goal.
2.  **Structure:** Recommending specific, detailed folder structures for different project sizes.
3.  **Templates:** Providing ready-to-use Markdown templates for core planning elements.
4.  **Workflow:** Guiding the user through planning stages, starting with foundational elements before adding detail.
5.  **Visualization:** Suggesting external tools for maps, timelines, etc.
6.  **Integration:** Preparing documents and defining transition points for the Narrative Writer mode.

**Integration with Narrative Writer:**
The Planner lays the groundwork. It creates the outlines, character profiles, and world details that the Writer mode will use to craft the actual prose. It includes specific instructions on preparing documents for handover and participating in a feedback loop where insights from the writing process can inform revisions to the plan.

---

### 2. Narrative Writer (`narrative-writer`)

**Purpose:**
The Narrative Writer mode acts as a skilled creative writer and prose stylist. It focuses on transforming the plans and outlines created by the Narrative Planner (or the user) into polished, engaging prose. It helps writers craft compelling descriptions, develop authentic dialogue, create immersive scenes, refine narrative voice, and improve the overall quality of their writing.

**Key Capabilities:**
*   **Prose Crafting:** Drafting scenes, descriptions, and narrative passages.
*   **Dialogue Development:** Creating realistic dialogue with distinct character voices and subtext.
*   **Scene Construction:** Building effective scenes with clear goals, conflict, and pacing.
*   **Perspective Guidance:** Assisting with the execution of different narrative perspectives (1st person, 3rd person limited/omniscient, etc.).
*   **Stylistic Refinement:** Helping to develop prose style, improve word choice, sentence structure, and rhythm.
*   **Pacing Control:** Managing narrative flow at both scene and sentence levels.
*   **Revision Assistance:** Guiding through developmental editing, line editing, and micro-editing.
*   **Genre Adaptation:** Providing genre-specific writing techniques (Fantasy, Sci-Fi, Mystery, Romance, Literary).

**Allowed Operations:**
*   Read files (`read` group).
*   Edit specific file types: Markdown (`.md`), Text (`.txt`), Word documents (`.doc`, `.docx`), Rich Text Format (`.rtf`).
*   Execute commands (`command` group).

**Workflow & Structure:**
This mode focuses on the *craft* of writing, guided by its `customInstructions`:
1.  **Perspective:** Ensuring consistent and effective use of the chosen narrative viewpoint.
2.  **Scene Building:** Focusing on structure, sensory details, and purpose within each scene.
3.  **Description & Dialogue:** Emphasizing vividness, authenticity, and narrative function.
4.  **Style & Voice:** Refining sentence craft, word choice, and overall narrative voice.
5.  **Pacing:** Controlling the flow and rhythm of the story.
6.  **Revision:** Offering strategies for different levels of editing.

**Integration with Narrative Planner:**
The Writer builds upon the foundation laid by the Planner. It uses the planning documents (outlines, character profiles) to ensure consistency in plot, characterization, and world details while drafting prose. It also defines when it's necessary to loop back to the Planner mode if significant inconsistencies, plot holes, or new ideas emerge during the writing process that require adjustments to the core plan.

---

### Overall Workflow Visualization

Here's a simplified view of how these modes might interact in a typical workflow:

```mermaid
graph TD
    A[Start Project] --> B{Narrative Planner};
    B --> C[Define Scope & Structure];
    C --> D[Develop Outline, Characters, World];
    D --> E{Ready to Write?};
    E -- Yes --> F{Narrative Writer};
    F --> G[Draft Prose (Scenes/Chapters)];
    G --> H{Review & Refine};
    H -- Needs Planning Changes --> B;
    H -- Continue Writing --> G;
    H -- Ready for Revision --> I[Revise Prose];
    I --> J[Final Output];
    E -- No --> D;

    style B fill:#f9f,stroke:#333,stroke-width:2px
    style F fill:#ccf,stroke:#333,stroke-width:2px
```

---

## License

*(Refer to the LICENSE file in the repository)*