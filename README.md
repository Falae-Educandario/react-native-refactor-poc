Cross-Platform Refactoring Strategy for Falaê AAC App
📱 Current App Analysis
Falaê is an Augmentative and Alternative Communication (AAC) Android app for people with speech impairments.

Core Features:
User Management: Multi-user profiles with cloud sync
Spreadsheets: Communication boards with visual symbols
Pages & Items: Grid-based navigation with categories
Text-to-Speech: Portuguese Brazilian voice synthesis
Scan Mode: Accessibility feature for motor impairments
Offline Support: Local Room database with image caching
🎯 Cross-Platform Technology Stack Recommendations
Option 1: React Native (RECOMMENDED for Your Use Case)
Why React Native:
✅ Best balance of performance, ecosystem, and code sharing
✅ Excellent TTS support on both platforms
✅ Strong accessibility APIs (crucial for AAC apps)
✅ Large developer community and mature libraries
✅ Can reuse existing backend API (falaeapp.org)
✅ Web version possible via React Native Web

Architecture:
┌─────────────────────────────────────────┐
│         Shared Business Logic (90%)      │
│  ─────────────────────────────────────── │
│  • State Management (Redux/Zustand)      │
│  • API Layer (Axios/Fetch)              │
│  • Data Models & Types                   │
│  • TTS Service Abstraction              │
│  • Navigation Logic                      │
│  • Accessibility Utilities               │
└─────────────────────────────────────────┘
           │              │              │
    ┌──────┴───────┐ ┌───┴───────┐ ┌────┴──────┐
    │   Android    │ │    iOS    │ │    Web    │
    │  (Native)    │ │ (Native)  │ │ (Browser) │
    └──────────────┘ └───────────┘ └───────────┘
