# Barranquilla GeoJSON

A collection of GeoJSON files for Barranquilla, Colombia, including neighborhood blocks and administrative boundaries.

## Contents

This repository contains GeoJSON data for Barranquilla, specifically:

- **BAQ_Neighborhood_Blocks**: GeoJSON file containing neighborhood blocks/sectors data originally sourced from Barranquilla's Health Department (Secretaría de Salud). This data represents the administrative divisions and city blocks within Barranquilla.

## Data Source

The data was originally extracted from Barranquilla's ArcGIS portal:
- Original source: Barranquilla's Municipal ArcGIS portal
- Original dataset: "SecSalud_SectoresManzanas" (Health Department Sectors and Blocks)
- Data URL: https://barranquilla.maps.arcgis.com/apps/mapviewer/index.html?layers=b800c0ae221b42b08f27b969e3fe45c6

## Data Processing

The original data was converted from ArcGIS Feature Service to GeoJSON format using the ArcGIS REST API. The conversion preserved the original attributes while transforming the geometry into standard GeoJSON format.

## Usage

These GeoJSON files can be used for:

- Urban planning and analysis
- Health sector studies and planning
- Demographic analysis
- Visualization in mapping tools (Leaflet, Mapbox, QGIS, etc.)
- Integration with other geospatial applications

### Example usage with Leaflet:

```javascript
// Load the neighborhood blocks GeoJSON file
fetch('BAQ_Neighborhood_Blocks.geojson')
  .then(response => response.json())
  .then(data => {
    L.geoJSON(data, {
      style: function(feature) {
        return {
          color: "#ff7800",
          weight: 1,
          opacity: 0.65
        };
      },
      onEachFeature: function(feature, layer) {
        layer.bindPopup("Barrio: " + feature.properties.BARRIO);
      }
    }).addTo(map);
  });
```

## Structure

The GeoJSON files include the following attributes:

- **ID**: Unique identifier for each feature
- **BARRIO**: Neighborhood name
- **LOCALIDAD**: Locality/district name
- Additional attributes specific to each dataset

## Updates

This repository will be updated with additional GeoJSON files for Barranquilla as they become available.

## Contributing

Contributions are welcome! If you have additional GeoJSON data for Barranquilla or improvements to the existing files, please feel free to submit a pull request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements

- Barranquilla Municipal Government
- Secretaría de Salud de Barranquilla (Barranquilla Health Department)
