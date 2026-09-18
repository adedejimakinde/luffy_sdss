# Luffy SDSS (Spatial Decision Support System)

A Spatial Decision Support System (SDSS) built to model geographical hazard zones, map student locations, and optimize transportation routes. Originally conceptualized within the Classnode (formerly Luffy) ecosystem, this service leverages spatial databases and machine learning to aid in geographical planning and safety assessments.

## 🌟 Key Features

* **Geospatial Modeling:** Utilizes PostGIS geometry fields to accurately map and store student coordinates, school boundaries, and bus routes.

* **Hazard Zone Detection:** Defines and visualizes geographical hazard zones to ensure student safety during transit and planning.

* **Route Optimization:** Analyzes spatial data to calculate efficient transportation routes.

* **Predictive Analytics:** Integrates `scikit-learn` to process historical data and model spatial decision outcomes.

## 🛠 Tech Stack

* **Backend:** Python, Django

* **Database:** PostgreSQL with PostGIS extension

* **Machine Learning:** Scikit-learn

* **Infrastructure:** Docker, Docker Compose

## 🚀 Quick Start (Docker)

The recommended way to run this project locally is via Docker, which automatically provisions the PostGIS-enabled database container.

### 1. Clone the repository

`bash git clone https://github.com/adedejimakinde/luffy_sdss.git cd luffy_sdss `

### 2. Configure Environment Variables

Create a `.env` file in the project root:
`env DEBUG=True SECRET_KEY=your-secret-key DATABASE_URL=postgis://user:password@db:5432/luffy_sdss `

### 3. Build and Run the Containers

`bash docker compose up --build -d `

### 4. Run Migrations and Create Superuser

`bash docker compose exec web python manage.py migrate docker compose exec web python manage.py createsuperuser `

The application will be available at `http://localhost:8000`.

## 🗺️ Spatial Database Notes

Ensure that your PostgreSQL instance has the PostGIS extension installed before running migrations. If running without Docker, you can enable it manually in your database via `psql`:

`sql CREATE EXTENSION postgis; `

## 🤝 Contributing

Contributions, issues, and feature requests are welcome. Feel free to check the [issues page](https://github.com/adedejimakinde/luffy_sdss/issues?utm_source=gemini) if you want to contribute.

## 📝 License

This project is licensed under the MIT License.