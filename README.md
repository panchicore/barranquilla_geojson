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









---------------

# Barranquilla ArcGIS Server Layers Summary

This summary organizes the key geographic datasets available on Barranquilla's ArcGIS server into categories.

## Administrative Boundaries

| Layer Name | Description | URL |
|------------|-------------|-----|
| Barrios | Neighborhoods | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Barrios/FeatureServer |
| Barrios_de_Barranquilla | Neighborhoods of Barranquilla | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Barrios_de_Barranquilla/FeatureServer |
| BARRIOS_WFL1 | Alternative neighborhoods layer | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/BARRIOS_WFL1/FeatureServer |
| FICHASBARRIOS_BARRIOS | Documentation on neighborhoods | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/FICHASBARRIOS_BARRIOS/FeatureServer |
| Localidades | Localities/districts | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Localidades/FeatureServer |
| LOCALIDADES_WFL1 | Alternative localities layer | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/LOCALIDADES_WFL1/FeatureServer |
| Limites_Politico_Administrativos | Political-administrative boundaries | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Limites_Politico_Administrativos/FeatureServer |
| FICHASBARRIOS_LIMITE_DISTRITAL | District boundary | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/FICHASBARRIOS_LIMITE_DISTRITAL/FeatureServer |
| FICHASBARRIOS_LIMITE_URBANO | Urban boundary | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/FICHASBARRIOS_LIMITE_URBANO/FeatureServer |
| SecSalud_PuestoSalud_SectoresManzanas | Health Department Sectors and Blocks | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/SecSalud_PuestoSalud_SectoresManzanas/FeatureServer |
| manzanas | City blocks | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/manzanas/FeatureServer |

## Urban Planning and Land Use

| Layer Name | Description | URL |
|------------|-------------|-----|
| CLASIFICACIÓN_DEL_SUELO | Land classification | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/CLASIFICACIÓN_DEL_SUELO/FeatureServer |
| Clasificación_Suelo_POT2014 | Land classification POT 2014 | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Clasificación_Suelo_POT2014/FeatureServer |
| FICHASBARRIOS_TRATAMIENTOS_URBANISTICOS_DENSIDAD | Urban treatments density | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/FICHASBARRIOS_TRATAMIENTOS_URBANISTICOS_DENSIDAD/FeatureServer |
| Tratamientos_URBANISTICOS | Urban treatments | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Tratamientos_URBANISTICOS/FeatureServer |
| TRATAMIENTOS_URBANISTICOS_2024 | Urban treatments 2024 | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/TRATAMIENTOS_URBANISTICOS_2024/FeatureServer |
| Instrumentos_de_Planificación | Planning instruments | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Instrumentos_de_Planificación/FeatureServer |
| ACTIVIDAD_USOS_URBANOS___Actividades | Urban uses activities | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/ACTIVIDAD_USOS_URBANOS___Actividades/FeatureServer |
| ESTRATIFICACION | Socioeconomic stratification | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/ESTRATIFICACION/FeatureServer |
| PEMP_Prado | Special Management and Protection Plan for Prado | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/PEMP_Prado/FeatureServer |

## Transportation and Infrastructure

| Layer Name | Description | URL |
|------------|-------------|-----|
| ESTADO_VIAL | Road conditions | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/ESTADO_VIAL/FeatureServer |
| Vias_corredores | Road corridors | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Vias_corredores/FeatureServer |
| TRAMOS_EN_EJECUCION | Road segments under construction | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/TRAMOS_EN_EJECUCION/FeatureServer |
| Ciclorutas_gdb | Bike routes | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Ciclorutas_gdb/FeatureServer |
| Ciclovias_BAQ | Bike paths | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Ciclovias_BAQ/FeatureServer |
| AMPLIACIÓN_CORREDORES_VIALES_2024 | Road corridor expansion 2024 | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/AMPLIACIÓN_CORREDORES_VIALES_2024/FeatureServer |

## Public Services and Facilities

| Layer Name | Description | URL |
|------------|-------------|-----|
| CAIS_BARRANQUILLA | Police stations | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/CAIS_BARRANQUILLA/FeatureServer |
| PARQUES_WFL1 | Parks | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/PARQUES_WFL1/FeatureServer |
| COLEGIOS_POLIGONOS | Schools (polygons) | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/COLEGIOS_POLIGONOS/FeatureServer |
| FICHASPUNTOS_INSTITUCIONES_EDUCATIVAS | Educational institutions | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/FICHASPUNTOS_INSTITUCIONES_EDUCATIVAS/FeatureServer |
| SecSalud_Red_Urgencias | Emergency health network | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/SecSalud_Red_Urgencias/FeatureServer |
| Espacio_Público | Public space | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Espacio_Público/FeatureServer |
| ZonasWifi | WiFi zones | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/ZonasWifi/FeatureServer |

## Environment and Natural Features

| Layer Name | Description | URL |
|------------|-------------|-----|
| Arroyos | Streams/waterways | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Arroyos/FeatureServer |
| AMENAZA_Inundación | Flood hazard areas | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/AMENAZA_Inundación/FeatureServer |
| Amenaza_Remoción_en_masa | Mass removal hazard areas | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Amenaza_Remoción_en_masa/FeatureServer |
| SUELO_DE_PROTECCIÓN | Protected land | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/SUELO_DE_PROTECCIÓN/FeatureServer |
| Mallorquin_WFL1 | Mallorquin Lagoon | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Mallorquin_WFL1/FeatureServer |

## Safety and Security

| Layer Name | Description | URL |
|------------|-------------|-----|
| puntos_criticos_WFL1 | Critical points | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/puntos_criticos_WFL1/FeatureServer |
| HOMICIDIOS_FOCALIZADOS_2024_WFL1 | Focused homicides 2024 | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/HOMICIDIOS_FOCALIZADOS_2024_WFL1/FeatureServer |
| camaras2025_WFL1 | Security cameras 2025 | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/camaras2025_WFL1/FeatureServer |
| SEGURIDAD_WFL1 | Security | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/SEGURIDAD_WFL1/FeatureServer |

## Health and COVID-19 Data

| Layer Name | Description | URL |
|------------|-------------|-----|
| SecSalud_PosCOVID19 | COVID-19 positive cases | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/SecSalud_PosCOVID19/FeatureServer |
| SecSalud_DatosCOVID | COVID-19 data | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/SecSalud_DatosCOVID/FeatureServer |
| SecSalud_CercosEpidemiologicos | Epidemiological fences | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/SecSalud_CercosEpidemiologicos/FeatureServer |
| CAP_UCI_COVID | COVID ICU capacity | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/CAP_UCI_COVID/FeatureServer |

## Base Maps and General References

| Layer Name | Description | URL |
|------------|-------------|-----|
| Mapa_base_Distrito_de_Barranquilla | Base map of Barranquilla District | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Mapa_base_Distrito_de_Barranquilla/FeatureServer |
| Mapabase_Distrito_de_Barranquilla | Base map of Barranquilla District | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Mapabase_Distrito_de_Barranquilla/FeatureServer |
| Mapa_Base_Panorama_Urbano | Urban panorama base map | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Mapa_Base_Panorama_Urbano/FeatureServer |
| Nomenclatura_Dirección | Address nomenclature | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Nomenclatura_Dirección/FeatureServer |

## Economic and Property Data

| Layer Name | Description | URL |
|------------|-------------|-----|
| Valor_del_Suelo_WFL1 | Land value | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Valor_del_Suelo_WFL1/FeatureServer |
| Catastro_WFL1 | Cadastre | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Catastro_WFL1/FeatureServer |
| Cartografia_Catastral | Cadastral cartography | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Cartografia_Catastral/FeatureServer |
| Economía_Productividad_WFL1 | Economy and productivity | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Economía_Productividad_WFL1/FeatureServer |
| Economica_Naranja_Barranquilla_WFL1 | Orange economy | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Economica_Naranja_Barranquilla_WFL1/FeatureServer |
| Destino_economico | Economic destination | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Destino_economico/FeatureServer |

## Projects and Development

| Layer Name | Description | URL |
|------------|-------------|-----|
| PROYECTOS_STORYMAP | Projects storymap | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/PROYECTOS_STORYMAP/FeatureServer |
| ProyectosEnEjecucion_StoryMap | Projects in execution storymap | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/ProyectosEnEjecucion_StoryMap/FeatureServer |
| Barrios_a_la_obra | Neighborhoods under construction | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/Barrios_a_la_obra/FeatureServer |
| LICENcIAS_URBANISTICAS_WFL1 | Urban licenses | https://services3.arcgis.com/oGYAc07w6wsvgUYr/ArcGIS/rest/services/LICENcIAS_URBANISTICAS_WFL1/FeatureServer |
