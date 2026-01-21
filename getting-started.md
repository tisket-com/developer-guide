# Getting Started

Welcome to the Developer Guide!

## Quick Start

1. Clone the repository
2. Install dependencies
3. Run the development server

## Next Steps

Check out the following guides:
- [Features](./features.md)
- [API Reference](./api/overview.md)
- [Architecture](./architecture.md)

## What's Next

Once you've completed the Quick Start, you can dive deeper into the platform:

- Explore **Features** to understand what's available and how different components fit together.
- Review the **API Reference** for detailed information on endpoints, authentication, and request/response formats.
- Read through the **Architecture** guide to learn how the system is structured and how data flows through it.

From here, you should be ready to start building, extending, or integrating with the platform.

## Testing Updates

This section exists to verify that documentation changes are correctly written, committed, and reflected in Tisket. If you can see this section, the update pipeline is working as expected.

## Timeline Feature Demo

This section was added to demonstrate the new Timeline feature in the sidebar. When you view a file's history, you can:

- See all commits that modified this file
- Click on a commit to view the inline diff
- Compare changes between versions

The Timeline replaces the old History button and provides a VS Code-like experience for viewing file changes.

## Local Branch Sync Test — January 21, 2026

Testing the new local branch architecture for SSE commits. This commit should:

- Appear immediately in the timeline (no API delay)
- Be stored on a `local` branch in the browser git repo
- Support immediate diff viewing without GitHub API calls
- Be cleaned up on next sync/refresh from GitHub