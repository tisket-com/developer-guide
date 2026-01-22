# developer-guide
Technical documentation for developers

## MCP API Test

This line was added via the Tisket MCP `context` tool - testing the new unified API!

## New Event — January 17, 2026

This event was added to verify MCP visibility and confirm that document edits correctly trigger Recent Activity updates in Tisket.

## Test Event — January 17, 2026

This is a test event added to confirm that README updates can be created programmatically via the MCP API and are reflected correctly in the Tisket UI.

## Standalone MCP Server Test — January 18, 2026

This section was added to verify the standalone MCP server running on port 4000 is fully functional with all tool implementations wired up correctly.

## Author Fix Test — January 21, 2026

Testing that commit author info now uses the user's real name and email from the database.

## Timeline & File Versions Update — January 21, 2026

Added several UI improvements to the timeline and document viewer:

- **Repository Timeline**: When viewing a file within a repo, the sidebar now shows the full repository timeline (not just the current file's history)
- **File Versions Panel**: Right sidenav now displays a "Versions" section at the top showing the file's commit history with timestamps and author names
- **Color-coded Timeline Dots**: Timeline entries that affect the current file show a colored dot (green for file creation, blue for modifications)
- **Diff Header**: Improved diff header with 5xl max-width, centered layout, and proper padding
- **Overflow Handling**: Timeline comments now properly truncate with ellipsis when the sidebar is resized

## Context & State Management Refactor — January 22, 2026

Major improvements to context management and UI state handling:

- **PageContext**: New context for managing page-level UI state including headings, aside layout visibility, and diff header information. Separates concerns from BrowserGitContext for cleaner architecture.
- **Version Subscription System**: BrowserGitContext now uses ref objects and a subscription mechanism for version tracking, allowing components to subscribe to version changes without triggering unnecessary re-renders.
- **useVersion Hook**: New hook for improved version tracking across components, providing a cleaner API for accessing file version state.
- **Deleted File Viewer**: New component for viewing files that have been deleted, with proper diff visualization.

## UI/UX Enhancements — January 22, 2026

Several usability improvements across the workspace:

- **Smooth Scrolling to Diffs**: InlineDiffRenderer now automatically scrolls to the first diff line when viewing changes, making it easier to spot modifications.
- **Component Memoization**: Workspace layout and sidebar components optimized with React.memo and useMemo for better performance during navigation.
- **Project/Team Creation**: CreateProjectSheet and CreateTeamSheet now accept an `initialName` prop for pre-filling input fields, with useEffect to update state when the sheet opens.
- **Workspace Switcher**: New WorkspaceSheet component for quickly switching between workspaces or creating new ones.
- **Enhanced Search**: WorkspaceOverview now includes improved search functionality with keyboard navigation (arrow keys + enter) for selecting projects, teams, and documents.