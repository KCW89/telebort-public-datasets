# M1 - Mobile Foundations: Teaching Diagrams

Comprehensive visual reference guides for M1 (Mobile Foundations) projects.

## Available Diagrams

### Project 03: Explore & Share
**File**: `project-03-explore-share.excalidraw`

**What it covers** (7 sections):
1. **FILE MAP** - Component tree structure (App.js → AuthContext → Screens → API)
2. **DATA FLOW** - How Context, useContext, and API integration work together
3. **PLATFORM CONTEXT** - Expo Go vs EAS Build (when to use each)
4. **LIFECYCLE TIMELINE** - useEffect timing and API call sequencing
5. **COMMON ERRORS** - React Native gotchas (Text wrapping, hooks rules, FlatList data)
6. **DEBUG CHECKLIST** - Metro bundler, console logs, cache clearing
7. **HOUSE ANALOGY** - Mental model for understanding navigation and context

**Key concepts visualized**:
- React Navigation (Tab Navigator)
- Context API for global state (AuthContext)
- API service layer pattern (CommunityAPI)
- useEffect lifecycle hooks
- AsyncStorage data persistence
- FlatList rendering with loading/error states
- SectionList categorization

**Technologies**:
- React Native
- Expo (~54.0.0)
- @react-navigation/native
- @react-navigation/bottom-tabs
- AsyncStorage
- Axios for API calls

## How to Use These Diagrams

### For Instructors
1. Open `.excalidraw` files at https://excalidraw.com
2. Use during lectures to explain architecture
3. Walk students through data flow section by section
4. Reference specific sections when debugging student code

### For Students
1. Open in Excalidraw (free, no login)
2. Use as reference while coding
3. Consult "Common Errors" section when stuck
4. Follow "Debug Checklist" for troubleshooting

### Opening Diagrams
**Option 1: Excalidraw.com (Recommended)**
1. Go to https://excalidraw.com
2. Click "Open" → Select `.excalidraw` file
3. All formatting preserved, dark theme included

**Option 2: VS Code Extension**
- Install "Excalidraw" extension
- Open `.excalidraw` files directly in editor

## Diagram Design Standards

All M1 diagrams follow these conventions:
- **Dark theme** (#121212 background)
- **Color coding**:
  - Orange (#f08c00): File structure, API layer
  - Blue (#1971c2): Data flow, state management
  - Green (#2f9e44): UI components, success states
  - Purple (#9c36b5): Context, hooks
  - Red (#c92a2a): Errors, warnings, pitfalls
- **7-section structure**: File Map → Data Flow → Platform → Lifecycle → Errors → Debug → Analogy
- **Code examples**: Real snippets from template solutions
- **Mental models**: Analogies for complex concepts

## Project Architecture Summary

### M1 Project 03: Explore & Share
**Type**: Community events app with tab navigation
**Complexity**: Intermediate (65-70% pre-built)
**Focus**: API integration + Context + Navigation

**Student TODOs**:
- Complete `CommunityAPI.fetchEvents()`
- Complete `CommunityAPI.searchContent()`
- Complete `AuthContext.signIn()`
- Integrate API calls in screens
- Handle loading/error states

**Pre-built components**:
- Tab navigation setup
- AuthProvider wrapper
- Screen layouts (Feed, Search, Share, Profile)
- EventCard reusable component
- AsyncStorage persistence

## Version History

- **v1.0** (Dec 2024): Initial release for Project 03
  - 7-section comprehensive guide
  - React Native focus (adapted from W3 SvelteKit pattern)
  - Mobile-specific debugging (Metro bundler, Expo Go)

## Contributing

When creating new M1 diagrams:
1. Follow the 7-section template
2. Use standardized color palette
3. Include code snippets from actual template solutions
4. Add platform-specific notes (Expo vs Native)
5. Test in both Excalidraw.com and VS Code extension

## Related Documentation

- **Course**: `/Paid Courses/M1-Mobile Foundations/`
- **Templates**: `/Paid Courses/M1-Mobile Foundations/Template Solution/`
- **Activities**: Concepts 07-09 (API, SectionList, Context)

---

**Last Updated**: December 2024
**Maintainer**: Content Development Team
