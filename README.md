# OpenLayers React Mapping Application

## Overview

This is a complete React application built with OpenLayers that provides interactive mapping capabilities including feature visualization, editing tools, and dynamic layer management. The application demonstrates modern web mapping techniques with a clean, modular architecture.

## Features Implemented

### TASK 1 - Basic Map & Popup
- **Full-page OpenLayers Map**: The application displays a complete viewport map using OpenLayers with OpenStreetMap tiles as the base layer
- **GeoJSON Vector Layer**: Loads sample data from `src/assets/data.geojson` containing NYC landmarks (Central Park, Statue of Liberty, Brooklyn Bridge, etc.)
- **Interactive Popups**: Clicking on any feature displays a styled popup showing the feature's properties using OpenLayers Overlay system

### TASK 2 - Zoom & Editing Tools
- **Zoom to Feature**: When clicking a feature, the map automatically zooms to fit the feature's extent with smooth animation
- **Drawing Tools**: Complete set of drawing tools for creating new features:
  - **Point Drawing**: Create point features by clicking on the map
  - **Line Drawing**: Create line features by clicking multiple points
  - **Polygon Drawing**: Create polygon features by clicking to define vertices
- **Modify Tool**: Edit existing features by dragging vertices and edges
- **Delete Tool**: Remove selected features from the vector source
- **Real-time Updates**: All editing operations directly update the vector source in real-time

### TASK 3 - Reusable Map Utilities
- **MapUtils.js**: Comprehensive utility module with the following functions:
  - `addALayer(map, name, layer)`: Add a named layer to the map for easy reference
  - `removeLayer(map, name)`: Remove a layer by its name identifier
  - `getLayerByName(map, name)`: Retrieve a specific layer by name
  - `listLayerNames(map)`: Get all layer names currently on the map
  - `createStyledVectorLayer(source, options)`: Create pre-styled vector layers

## How Each Feature Works

### Map Initialization
The map is created using OpenLayers with OpenStreetMap as the base layer. The view is centered on New York City with an appropriate zoom level to show all sample features.

### Feature Loading
GeoJSON data is loaded using OpenLayers' GeoJSON format reader and added as a vector layer. Features are automatically projected from WGS84 (longitude/latitude) to Web Mercator projection for display.

### Click Interaction
A Select interaction handles map clicks to identify features. When a feature is selected:
1. The popup component receives the feature data
2. The map zooms to the feature's extent using `view.fit()`
3. An overlay positions the popup at the feature's centroid

### Drawing Tools
Each drawing tool creates a new OpenLayers Draw interaction:
- Users can switch between Point, LineString, and Polygon drawing modes
- New features automatically receive properties including name, type, and creation timestamp
- The drawing tools directly modify the vector source

### Modify and Delete
- The Modify interaction allows users to edit feature geometries by dragging vertices
- Selected features can be deleted using the delete button, which removes them from the vector source

### Responsive Design
The map automatically resizes when the browser window changes size using OpenLayers' `updateSize()` method.

## AI Assistance Used

### Code Structure and Architecture
AI assistance was used to design the overall application architecture, ensuring proper separation of concerns between the map logic, UI components, and utility functions.

### OpenLayers Integration
AI helped with the correct import patterns for OpenLayers modules using ES6 syntax, and provided guidance on proper OpenLayers API usage for:
- Map initialization and configuration
- Vector layer creation and styling
- Interaction setup (Select, Draw, Modify)
- Overlay positioning and management

### React Best Practices
AI assistance was used to implement:
- Proper useEffect hooks for map lifecycle management
- State management for UI interactions
- Event handling patterns
- Component composition and prop passing

### Styling and UI/UX
AI helped create the Tailwind CSS styling for:
- Popup component layout and responsive design
- Tool panel design with proper hover states and active indicators
- Status indicators and user feedback elements
- Overall visual hierarchy and accessibility considerations

### Error Handling and Edge Cases
AI assistance was used to implement proper error handling for:
- Map resize events
- Feature selection edge cases
- Tool state management
- Memory cleanup on component unmount

The AI assistance ensured the code follows modern React and OpenLayers best practices while maintaining clean, readable, and maintainable code structure.

## Project Structure

```
src/
├── components/
│   ├── MapComponent.jsx     # Main map component with all interactions
│   └── Popup.jsx           # Popup UI component for feature display
├── utils/
│   └── MapUtils.js         # Reusable layer management functions
├── assets/
│   └── data.geojson        # Sample GeoJSON data
├── App.jsx                 # Main application component
├── main.jsx               # Application entry point
└── index.css              # Global styles with Tailwind
```

## Running the Application

```bash
npm install
npm run dev
```

The application will start on `http://localhost:5173` and is ready to use immediately with all features functional.# icourt-maps-app
