# PLAN: Notion Portfolio Memo Engine & UI Cleanup

## 🎯 Goal
- Create a robust "Memo Engine" using Iframes for isolated HTML/CSS rendering.
- Simplify the home page to include only the greeting and project list.
- Ensure "Global Persistence" by relying on AI-driven code commits to the repository.
- Fix broken page creation/deletion logic.

## 🏗️ Architecture
- **Sandboxed Rendering**: Use `<iframe>` with `srcdoc` to render custom HTML/CSS without affecting the parent portfolio layout.
- **Persistence Workflow**: 
  1. User designs in the browser. 
  2. UI generates a "Persistence Request" (JSON). 
  3. User sends request to AI. 
  4. AI modifies `index.html` and pushes to Git.
- **Routing**: Fix the SPA routing to dynamically recognize newly added sidebar links and sections.

## 📝 Task Breakdown

### Phase 1: Planning (Done)
- [x] Analyze requirements
- [x] Design persistence & isolation model

### Phase 2: Implementation (Current)
- **Task 1: Home Page Cleanup** (`frontend-specialist`)
  - Remove "최근 기록" (Recent Records) and fluff from `page-home`.
  - Ensure greeting and project list are the main focus.
- **Task 2: Isolated Memo Engine** (`frontend-specialist`)
  - Update `page-newsletter-strategy` and other content sections to use `<iframe>`.
  - Create a CSS-reset within the iframe to guarantee "exact" mirroring of user code.
- **Task 3: Robust Routing & Management** (`debugger`)
  - Fix `navigateTo` and sidebar element selection to use event delegation or dynamic re-querying.
  - Implement a stable `deletePage` logic that correctly identifies static vs dynamic content.
- **Task 4: Verification & Deployment** (`test-engineer`)
  - Verify Iframe responsiveness.
  - Test dark mode compatibility for the sandbox (optional or scoped).

## 🧪 Verification Criteria
- [ ] HTML/CSS in a memo does not leak styles to the sidebar or other pages.
- [ ] Deleting a page removes it from the sidebar and content area immediately.
- [ ] Only the greeting and project list appear on the Home page.
- [ ] Repository is updated with the new structure.
