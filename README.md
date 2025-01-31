# Bustling-Spatial-Analysis


## **Project Description**
This project is part of a university group project focused on **spatial data analysis and visualisation** using **PostgreSQL with PostGIS**. It integrates geospatial datasets to analyse urban metrics, infrastructure distribution, and economic activity.

The project primarily examines **the bustling metric of Greater Sydney**, assessing economic activity and urban vibrancy across **Statistical Area Level 2 (SA2) regions**. The analysis incorporates multiple datasets, including:
- **Business activity data** (`Business.csv`) to evaluate local economic density.
- **Population and income statistics** (`Population.csv`, `Income.csv`) to analyse socio-economic factors.
- **Public transport data** (`Stops.txt`) to assess accessibility.
- **Polling stations and schools data** (`PollingPlaces2019.csv`, `catchments_primary.shp`, etc.) for infrastructure analysis.

This project also explores **integrating non-relational data** into Jupyter Notebooks, using **Python libraries such as SQLAlchemy, psycopg2, and Pandas** to write SQL queries, process spatial data, and compute urban analysis metrics.

A key aspect of the analysis is computing the **bustling score**—a composite indicator that evaluates:
- **Business density**
- **Public transport accessibility**
- **Civic infrastructure (polling stations, schools, healthcare facilities)**
- **Additional datasets for urban vitality**

The results include **statistical evaluations, spatial joins, and visualisations** using geospatial tools, with outputs presented as **interactive maps, histograms, and scatter plots**.

For more details on methodology and dataset integration, refer to the **project report**.

---

## **Requirements**
Before running this project, ensure that:
- **PostgreSQL** is installed and running (version 17 or later recommended).
- **PostGIS extension** is enabled in the database.
- **pgAdmin** is installed for database management.
- **Python environment** is set up with necessary libraries:
  - `sqlalchemy`
  - `psycopg2`
  - `pandas`
  - `geopandas`

---

## **Setup Instructions**
1. Clone or download this repository.
2. Ensure the `credential.json` file contains the correct PostgreSQL configuration.
3. Install required Python packages using:
   ```sh
   pip install -r requirements.txt
Run the database schema setup script:
sh
Copy
Edit
python setup_database.py
Verify PostGIS installation in PostgreSQL:
sql
Copy
Edit
SELECT postgis_version();
If PostGIS is not installed, enable it:
sql
Copy
Edit
CREATE EXTENSION postgis;
Configuration
credential.json
Ensure the credential.json file is correctly configured with your own local PostgreSQL credentials.

json
Copy
Edit
{
    "host": "localhost",
    "port": 5432,
    "database": "your_database",
    "user": "postgres",
    "password": "<your_pgadmin_password>"
}
Note: The password should be the same as the one you registered in pgAdmin on your local system. If you are unsure, you can reset it using:

sql
Copy
Edit
ALTER USER postgres WITH PASSWORD 'your_new_password';
Notifications
Any system errors or failures will be logged in the logs/ directory. If the database connection fails, check:

PostgreSQL is running
sh
Copy
Edit
Get-Service postgresql*
Password authentication is correct
sh
Copy
Edit
psql -U postgres -h localhost -p 5432
The database exists
sql
Copy
Edit
\l
Additional Notes
This project processes geospatial datasets, including:
Schools
Transport stops
Polling stations
The final analysis includes:
Statistical evaluation of urban activity
Geospatial visualisations of processed data
Interactive maps for visualisation and analysis.
