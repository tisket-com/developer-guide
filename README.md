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