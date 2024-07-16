poetry run uvicorn app.main:app --host localhost --port 8000 --reload

poetry run pytest --dburl=postgresql://postgres:postgres@localhost:5433/postgres

                                                                