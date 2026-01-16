# DEV HANDOFF - Hyphae Core

## Current Status
The project is in the **Initialization Phase**. The core data structures and a proto-dashboard have been established in `App.tsx` and `types/schema.ts`. Governance files have been initialized.

- **Completed**:
    - Project structure research.
    - AI Codex creation.
    - Initial Task List.
    - POS integration architecture documentation.
- **In Progress**:
    - Finalizing initialization and plan for Phase 1.

## Ecosystem Context
**Hyphae Core** is the strategic control center for the Hyphae Suit ecosystem:
- **POS Integration**: [geckogtmx/hyphae-pos](https://github.com/geckogtmx/hyphae-pos) consumes menu data from Core via `MenuRelease` snapshots.
- **Data Contract**: `types/schema.ts` is the source of truth for shared types (Concept, Category, Product, ModifierGroup, Recipe, etc.).
- **Integration Docs**: See `docs/POS_INTEGRATION.md` for detailed data flows and API contracts.

## Next Instruction
Transition the proto-dashboard into a modular architecture using **Zustand** for state management and **Drizzle** for local persistence.

## Task Backlog (Next 20)
1. [ ] Set up Drizzle ORM and SQLite configuration.
2. [ ] Define Drizzle schema based on `types/schema.ts`.
3. [ ] Create a `world` store using Zustand 5.
4. [ ] Migrate `MOCK_DATA` from `App.tsx` to a seeded SQLite database.
5. [ ] Refactor `DashboardView` into its own component file.
6. [ ] Implement `IntelligenceView` chat history persistence.
7. [ ] Set up a Sync Worker stub for offline-sync logic.
8. [ ] Add Zod validation for all incoming transaction records.
9. [ ] Implement "Heartbeat" logic for `DeviceState` monitoring.
10. [ ] Create a SHASO-compliant "Product Editor" modal.
11. [ ] Add Vitest setup for backend/domain logic testing.
12. [ ] Implement `InventoryService` integration with SQLite.
13. [ ] Add `Recipe` costing calculations in the Finance view.
14. [ ] Create a "Menu Release" export utility (JSON format).
15. [ ] Add Lucide-React icon mapping for all categories.
16. [ ] Implement "Touch Strike Zones" for all navigation elements (SHASO).
17. [ ] Add a `WasteLog` entry form.
18. [ ] Update `GeminiService` to use local environment variables for API keys.
19. [ ] Implement a "System Health" ticker in the Navigation rail.
20. [ ] Document the "Code B-Smash" hierarchy in a Mermaid diagram.

## Known Issues
- `MOCK_DATA` is currently hardcoded in `App.tsx`.
- `GeminiService` uses `MODEL_FAST = 'gemini-2.5-flash'`, ensure API key is configured.
- UI in `App.tsx` is monolithic and needs modularization.
- No menu export utility yet (required for POS integration).
- Schema compatibility testing not implemented (critical for POS data contract).
