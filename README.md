TraceKit
A structured workflow record and traceability platform
A browser-based tool for designing multi-step process workflows, tracking parameters at each stage, generating traceability matrices, and managing equipment or resource state transitions — all exportable as structured JSON.

Overview
TraceKit was built to demonstrate applied computing skills in workflow design, structured data management, process documentation, and AI-assisted parameter generation. It provides a visual interface for building step-by-step process records with configurable parameters, automated cross-referencing, and state machine visualisation.

Features
Workflow Builder

Visual process palette with 12 configurable operation types
Step-specific parameter fields tailored to each operation
Reorderable steps with free-text notes and remarks
Process flow visualisation with step connectors

Traceability Matrix

Auto-generated matrix mapping workflow steps to source document references
Status tracking per step — verified, pending, requires review
Exportable as structured JSON

Resource State Diagrams

Auto-generated state transition diagrams based on active workflow steps
Models valid state flows per resource type (e.g. Idle → Setup → Running → Complete → Clean)
Reflects real-world state machine design patterns

AI Parameter Assistant

Powered by Claude (Anthropic API)
Describe a process step in plain language → receive structured parameter suggestions
Parsed output populates a new step card automatically

JSON Export

Full workflow record exported as structured JSON
Includes step metadata, parameter values, status flags, and verification requirements
Compatible with downstream processing pipelines


Tech Stack
LayerTechnologyFrontendVanilla HTML, CSS, JavaScriptAI IntegrationAnthropic Claude APIStylingCSS custom properties, dark mode supportDeploymentSingle .html file — runs in any modern browser

Getting Started
Run locally
No installation required. Open tracekit.html in any modern browser:
bash# Option 1: double-click the file in your file explorer

# Option 2: serve locally
npx serve .
# open http://localhost:3000/tracekit.html
Deploy to GitHub Pages
bashgit init
git add tracekit.html README.md
git commit -m "Initial release: TraceKit v1.0"
git remote add origin https://github.com/yourusername/tracekit.git
git push -u origin main
Enable GitHub Pages in Settings → Pages → Deploy from branch → main.
Live at:
https://yourusername.github.io/tracekit/

Project Structure
tracekit/
├── tracekit.html      # Complete single-file application
└── README.md          # This file

Core Concepts Demonstrated
ConceptImplementationWorkflow designStep-based process builder with typed operationsTraceabilityAuto-generated matrix with source document mappingState machinesResource state transition diagramsAI integrationNatural language → structured parameter generationData exportStructured JSON with metadata and validation flagsDocumentationDouble-check flags, verification requirements, audit fields

Sample JSON Output
json{
  "document_type": "Workflow Record",
  "title": "Process Batch 2024-001",
  "version": "1.0",
  "status": "draft",
  "steps": [
{
      "step_number": 1,
      "step_id": "STEP-001",
      "operation_type": "Dispense",
      "description": "Initial material intake",
      "parameters": {
        "quantity": "55.0 kg",
        "tolerance": "± 2.0%",
        "equipment": "Station A"
      },
      "critical_step": true,
      "requires_double_check": true
    }
  ]
}
