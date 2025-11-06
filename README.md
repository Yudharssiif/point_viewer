# Control Point Viewer

A web-based GIS application for viewing and managing control points with coordinate system transformations and measurement tools.

## Features

### 1. Coordinate Systems Support

- ARC 1960 (Zones 35, 36, 37)
- WGS84 UTM (Zones 35, 36, 37)
- Automatic coordinate system transformations using proj4js

### 2. Control Points

- Display control points on an interactive map
- View detailed information for each control point:
  - Name
  - Zone
  - Easting and Northing (ARC 1960)
  - Elevation
  - WGS84 coordinates
- Table view of all control points with sorting and filtering

### 3. Search Functionality

- Search by control point name
- Search by coordinates (ARC 1960 or WGS84 UTM)
- Location search with OpenStreetMap integration
- Interactive search results with map centering

### 4. Measurement Tools

- Distance measurement
- Area measurement
- Real-time measurement display
- Clear measurement functionality

### 5. Map Features

- Toggle between street and satellite view
- User location tracking
- Zoom controls
- Responsive design for all screen sizes
- Collapsible sidebar for better map viewing

## Setup

1. Clone the repository:

```bash
git clone [repository-url]
cd [repository-name]
```

2. Start a local server (one of the following methods):

```bash
# Using Python 3
python -m http.server 8000

# Using Python 2
python -m SimpleHTTPServer 8000

# Using Node.js
npx http-server
```

3. Open the application in your browser:

```
http://localhost:8000
```

## File Structure

- `index.html` - Main application file
- `points.geojson` - Control points data in GeoJSON format
- `README.md` - Project documentation

## Dependencies

- [Leaflet.js](https://leafletjs.com/) - Interactive maps
- [Proj4js](http://proj4js.org/) - Coordinate transformations
- [Tailwind CSS](https://tailwindcss.com/) - Styling
- [Font Awesome](https://fontawesome.com/) - Icons

## GeoJSON Data Format

The control points should be stored in `points.geojson` with the following structure:

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "name": "CP-001",
        "zone": "36",
        "easting": 123456.789,
        "northing": 9876543.21,
        "elevation": 45.67
      },
      "geometry": {
        "type": "Point",
        "coordinates": [longitude, latitude]
      }
    }
  ]
}
```

## Usage

1. **View Control Points**

   - Control points are automatically loaded and displayed on the map
   - Click on any point to view detailed information

2. **Search**

   - Use the search bar at the top to find control points or locations
   - Enter coordinates in the format "Northing, Easting"
   - Search by control point name or location name

3. **Coordinate Entry**

   - Switch between ARC 1960 and WGS84 UTM using the tabs
   - Enter coordinates and click "Search" to locate positions

4. **Measurements**

   - Click "Measure Distance" to measure distances between points
   - Click "Measure Area" to measure enclosed areas
   - Double-click to finish measurements
   - Use "Clear Measurements" to reset

5. **Map Controls**
   - Use the buttons in the bottom right to:
     - Toggle between street and satellite view
     - Get current location
     - Zoom in/out

## Browser Compatibility

Tested and working on:

- Google Chrome (latest)
- Mozilla Firefox (latest)
- Microsoft Edge (latest)
- Safari (latest)

## Notes

- Geolocation requires HTTPS or localhost for security reasons
- Some browsers may require permission for location access
- Coordinate transformations are approximations and should be verified for high-precision work

## License

MIT License

Copyright (c) 2025 Street Mappers

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
