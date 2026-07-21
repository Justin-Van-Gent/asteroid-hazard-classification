# asteroid-hazard-classification
Data analysis and ML project on NASA Near-Earth Asteroids – Portfolio project

## Project Overview
Can we accurately predict whether a Near-Earth Asteroid is Potentially Hazardous (PHA) using its orbital and physical characteristics?

A Potentially Hazardous Asteroid is defined as an object that comes within 0.05 AU (approximately 7.5 million km) of Earth’s orbit and has a diameter of 140 meters or larger.

By building a classification model and exploring key features (especially MOID, size, absolute magnitude, and orbit class), this project aims to:

Better understand what makes an asteroid dangerous
Provide insights relevant to planetary defense
Demonstrate a full data science workflow from data cleaning to modeling

## Data Dictionary
| Column                | Description                                                      |
|-----------------------|------------------------------------------------------------------|
| spkid                 | Unique NASA JPL Small-Body ID                                    |
| full_name             | Full name / designation of the asteroid                          |
| pdes                  | Primary designation                                              |
| pha                   | Potentially Hazardous Asteroid (True / False)                    |
| H                     | Absolute magnitude                                               |
| diameter_km           | Estimated diameter in kilometers                                 |
| diameter_m            | Estimated diameter in meters                                     |
| diameter_is_estimated | Whether the diameter is estimated (True) or measured             |
| size_category         | Size classification (e.g. Tiny, Small, Local Damage, etc.)       |
| class                 | Orbit class (Apollo, Aten, Amor, Atira, etc.)                    |
| e                     | Eccentricity                                                     |
| a                     | Semi-major axis (AU)                                             |
| i                     | Inclination (degrees)                                            |
| q                     | Perihelion distance (AU)                                         |
| ad                    | Aphelion distance (AU)                                           |
| per                   | Orbital period (days)                                            |
| per_y                 | Orbital period (years)                                           |
| moid_au               | Minimum Orbit Intersection Distance (AU)                         |
| moid_km               | Minimum Orbit Intersection Distance (km)                         |
| moid_lunar_distances  | Minimum Orbit Intersection Distance in Lunar Distances           |
| n                     | Mean motion (degrees/day)                                        |
| condition_code        | Orbit condition code (0 = best known orbit, 9 = most uncertain)  |
| first_obs             | Date of first observation                                        |
| last_obs              | Date of last observation                                         |
| data_arc              | Length of observation arc (days)                                 |
| data_arc_years        | Length of observation arc (years)                                |
|                       |                                                                  |

## Data Cleaning Summary
The original dataset contained 41,281 rows and 29 columns. 

**Columns removed**:
These columns were removed due to exessive missing values > 90%.
- 'name'
- 'albedo'
- 'rot_per'

**Rows Removed**:
All the rows that still contained any mssing values after the column drop (539 rows).
Affected columns with remaining missing values included:
- 'data_arc'
- 'data_arc_years'
- 'moid_au'
- 'moid_km'
- 'moid_lunar_distances'
- 'H'
- 'condition_code'
- 'first_orbs'

**Additional quality checks performed**:
- No duplicate rows found
- No impossible values detected (e.g. negative numbers, invalid eccentricity, etc.)

**Final clean dataset**:
- 

## Motivation
I have a strong interest in space and planetary defense. With thousands of Near-Earth Asteroids being tracked, understanding which ones pose a real risk — and how we might prepare — feels like an important and timely problem.
