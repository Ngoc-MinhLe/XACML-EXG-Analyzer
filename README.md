XACML EXG Analyzer - v6.5 Final Stability

A Graph-Based Framework for Explainable Decision Analysis in XACML Access Control Policies

This tool is a graph-based access policy analyzer designed to address the transparency challenge in Attribute-Based Access Control (ABAC) systems utilizing the XACML 3.0 standard. The project is built upon the theoretical framework of the research paper regarding Evaluation Explanation Graphs (EXG).

🚀 Core Features

Policy Parsing & Hierarchy Visualization: Automatically reads and analyzes complex XACML policy structures including PolicySet, Policy, and Rule. Displays the structure as an intuitive logic tree.

EXG Construction (Algorithm 1): Recursively builds the Evaluation Explanation Graph (EXG), accurately reflecting policy dependencies and decision propagation mechanisms.

Backward Traversal Explanation (Algorithm 2): Traverses the graph backward from the final result to determine the causal path (Explanation Path), identifying the Dominant Rule responsible for the decision.

High-Definition Visualizer:

Zoom & Pan: Flexible drag-and-drop and zoom-in/out capabilities.

Precision Scaling: Node frames automatically fit the text content, ensuring high aesthetic quality for research reports.

Integrated Status Tags: Displays Permit, Deny, and NotApplicable results directly on the graph with high contrast.

Experimental Data Export: Saves analysis results as .json files, including execution time (latency), node count, and decision outcomes for experimental statistics.

🔬 Theoretical Background

The tool implements two primary algorithms from the research:

Algorithm 1 (EXG Construction): Recursively traverses policy elements, establishing edges based on containment relationships and combining algorithms.

Algorithm 2 (Explanation Extraction): After obtaining the result from the PDP (Policy Decision Point), the engine performs a backward traversal from the root node to filter out "active" branches contributing to the final decision.

🛠️ How to Use

Launch: Open the analyzer.html file in any modern web browser (Chrome, Edge, Firefox).

Step 1 - Import XACML: Click the "1. Import" button to upload your XACML policy file (.xml). The structure will appear in the Structure column on the left.

Step 2 - Configure Request: Enter the query attributes (Subject, Resource, Action, etc.) into the Context Request panel.

Step 3 - Analyze: Click the "2. Analyze" button. The EXG graph will be automatically rendered in the center column.

Step 4 - Export Data: Click "3. Export Data" to save the experimental results to your computer.

Fullscreen Mode: Click the "Fullscreen" button to expand the graph to full screen, and use the "Auto-Fit" button to align the diagram perfectly within the viewport.

📁 JSON Data Structure (Export)

The exported data is designed to align with experimental statistics tables (e.g., Table 2 in the paper):

{
  "dataset": "Name of the policy set",
  "outcome": "Permit / Deny / NotApplicable",
  "latency": "Processing time (ms)",
  "nodes": "Total nodes in the EXG",
  "dominant_rule": "ID of the rule causing the decision",
  "timestamp": "Execution time"
}


💻 Tech Stack

Tailwind CSS: Modern UI, responsive across various screen sizes.

Mermaid.js (v11.12.2): Powerful graph rendering library supporting complex flowcharts.

Native DOM Parser: Analyzes XML directly in the browser without requiring server-side processing.

JavaScript (ES6+): Handles graph traversal algorithms and decision propagation logic.

📌 Notes for Researchers

To capture the clearest diagrams for your paper, use Fullscreen mode and zoom into the Decision Path branches (marked with thick borders).

The Reset function in the attributes panel helps quickly clear old values to start a new query scenario.

The provided sample datasets (FMS, HACS, SIS) are optimized to showcase the depth and complexity of the EXG graph.