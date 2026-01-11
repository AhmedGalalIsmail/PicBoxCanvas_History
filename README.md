# PicBoxCanvas_History

check this map

```txt
CoNSoL Suite (Platform)
└── CoNSoL-TakeOff (Standalone App)
    ├── #P1 Inception
    │   ├── #D101 Requirement Analysis
    │   │   ├── #D10101 - Problem Statement
    │   │   ├── #D10102 - Business Goals & KPIs
    │   │   ├── #D10103 - Stakeholder Map & RACI
    │   │   ├── #D10104 - Scope, Constraints, Assumptions
    │   │   ├── #D10105 - Personas & User Journeys
    │   │   ├── #D10106 - Use Cases / User Stories
    │   │   ├── #D10107 - Non-Functional Requirements
    │   │   └── #D10108 - Glossary
    │   └── #D102 Planning
    │       ├── #D10201 - Roadmap & Milestones
    │       ├── #D10202 - Risks & Mitigation
    │       ├── #D10203 - Resource & Budget Plan
    │       ├── #D10204 - Release Strategy
    │       └── #D10205 - Communication Plan
    │
    ├── #P2 Design
    │   ├── #D201 System Architecture
    │   │   ├── #D20101 - Context Diagram
    │   │   ├── #D20102 - Solution Container Diagram
    │   │   ├── #D20103 - Domain Model
    │   │   ├── #D20104 - Sequence & Flow Diagrams
    │   │   ├── #D20105 - Deployment/Execution Topology
    │   │   └── #D20106 - Cross-Cutting Concerns
    │   │
    │   │   ┌── Project Structure Embedded Here 
    │   │   │
    │   │   └── CoNSoL-TakeOff Projects (Architectural View)
    │   │       ├── Layer 1: Desktop (UI)
    │   │       │   ├── Forms/MainForm.vb
    │   │       │   ├── Controls/CanvasControl.vb
    │   │       │   └── CompositionRoot.vb
    │   │       │
    │   │       ├── Layer 2: Application
    │   │       │   ├── TakeOffService.vb
    │   │       │   ├── SnappingService.vb (if exists)
    │   │       │   └── GuideService.vb (if exists)
    │   │       │
    │   │       ├── Layer 3: Domain
    │   │       │   ├── CanvasLayout.vb
    │   │       │   ├── CanvasElement.vb
    │   │       │   ├── Units.vb
    │   │       │   └── DPI.vb
    │   │       │
    │   │       └── Layer 4: Infrastructure
    │   │           ├── Logging/FileLogger.vb
    │   │           ├── Logging/ILogger.vb
    │   │           ├── Crypto/CryptoService.vb
    │   │           ├── Crypto/Hashing.vb
    │   │           ├── IO/TakeOffFileStore.vb
    │   │           └── Config/AppConfig.vb
    │   │
    │   └── #D202 UI & UX Design
    │       ├── #D20201 - Main UI Layout
    │       ├── #D20202 - Canvas Interaction Model
    │       └── #D20203 - Toolbars & Status Bar Behavior
    │
    ├── #P3 Implementation
    │   ├── #D301 Coding Standards & Conventions
    │   ├── #D302 Project-to-Doc Mapping (very important)
    │   │   ├── Desktop Layer
    │   │   │   ├── MainForm.vb → #D40101
    │   │   │   ├── CanvasControl.vb → #D40102
    │   │   │   └── CompositionRoot.vb → #D40103
    │   │   │
    │   │   ├── Application Layer
    │   │   │   └── TakeOffService.vb → #D40201
    │   │   │
    │   │   ├── Domain Layer
    │   │   │   ├── CanvasLayout.vb → #D40301
    │   │   │   └── CanvasElement.vb → #D40302
    │   │   │
    │   │   └── Infrastructure Layer
    │   │       ├── FileLogger.vb → #D40401
    │   │       ├── CryptoService.vb → #D40402
    │   │       ├── Hashing.vb → #D40403
    │   │       └── TakeOffFileStore.vb → #D40404
    │   │
    │   └── #D303 Build & CI/CD Scripts
    │
    ├── #P4 Testing
    │   ├── #D401 Test Plan
    │   ├── #D402 Unit Tests
    │   ├── #D403 Integration Tests
    │   ├── #D404 Performance Tests
    │   └── #D405 Test Reports
    │
    ├── #P5 Deployment
    │   ├── #D501 Deployment Steps
    │   ├── #D502 Packaging
    │   └── #D503 Installer Behavior
    │
    └── #P6 Operations
        ├── #D601 Logging & Monitoring
        ├── #D602 Error Codes & Messages
        ├── #D603 Configuration
        ├── #D604 Support Procedures
        └── #D605 Release Notes

```
