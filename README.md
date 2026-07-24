# asteroid-hazard-classification
Data analysis and ML project on NASA Near-Earth Asteroids – Portfolio project

## Project Overview
Can we accurately predict whether a Near-Earth Asteroid is Potentially Hazardous (PHA) using its orbital and physical characteristics?

A Potentially Hazardous Asteroid is defined as an object that comes within 0.05 AU (approximately 7.5 million km) of Earth’s orbit and has a diameter of 140 meters or larger.

The main goals of this project are to:
- Explore and understand the characteristics of Near_Earth Asteroids
- Identify key patterns related to potentially hazardous asteroids
- Clean and prepare a high-quality dataset ready for machine learning modelling
- Communicate clear findings through visualizations and analysis

## Motivation
I have a strong interest in space and thought this would be a good fit for me. With thousands of Near-Earth Asteroids being tracked, understanding which ones pose a real risk — and how we might prepare — feels like an important and timely problem.

## Data Dictionary
| Column                | Description                                                      | Notes                                             |
|-----------------------|------------------------------------------------------------------|---------------------------------------------------|
| spkid                 | Unique NASA JPL Small-Body ID                                    | Primary identifier                                |
| full_name             | Full name / designation of the asteroid                          | e.g. "433 Eros (A898 PA)"                         |
| pdes                  | Primary designation                                              |                                                   |
| pha                   | Potentially Hazardous Asteroid (True / False)                    | **Target Variable**                               |
| H                     | Absolute magnitude                                               | Smaller H = brighter/larger asteroid              |
| diameter_km           | Estimated diameter in kilometers                                 |                                                   |
| diameter_is_estimated | Whether the diameter is estimated (True) or measured             |                                                   |
| size_category         | Size classification (e.g. Tiny, Small, Local Damage, etc.)       |                                                   |
| class                 | Orbit class (Apollo, Aten, Amor, Atira, etc.)                    |                                                   |
| e                     | Eccentricity                                                     | 0 = circular orbit, closer to 1 = very elongated  |
| a                     | Semi-major axis (AU)                                             | Average distance from the Sun                     |
| i                     | Inclination (degrees)                                            | Tilt of the orbit relative to Earths orbit        |
| q                     | Perihelion distance (AU)                                         | Closest point to the Sun                          |
| ad                    | Aphelion distance (AU)                                           | Farthest point from the Sun                       |
| per_y                 | Orbital period (years)                                           |                                                   |
| moid_au               | Minimum Orbit Intersection Distance (AU)                         | How close the orbits come to each other           |
| n                     | Mean motion (degrees/day)                                        |                                                   |
| condition_code        | Orbit condition code (0 = best known orbit, 9 = most uncertain)  |                                                   |
| first_obs             | Date of first observation                                        |                                                   |
| last_obs              | Date of last observation                                         |                                                   |
| data_arc_years        | Length of observation arc (years)                                |                                                   |

## Data Cleaning Summary
The original dataset contained 41,281 rows and 29 columns. 

**Columns removed**:
These columns were removed due to excessive missing values > 90%.
- 'name'
- 'albedo'
- 'rot_per'

**Rows Removed**:
All the rows that still contained any missing values after the column drop (539 rows).

**Redundant Features Removed**
After exploring the data, the following redundant columns (same measurements in different units) were dropped:
- 'moid_km'
- 'moid_lunar_distances'
- 'per'
- 'data_arc'
- 'diameter_m'

**Additional quality checks performed**:
- No duplicate rows found
- No impossible values detected (e.g. negative numbers, invalid eccentricity, etc.)

**Final clean dataset**:
- 40,742 rows
- 21 columns
- 0 missing values