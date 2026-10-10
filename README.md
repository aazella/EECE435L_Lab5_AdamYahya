# Lab 5 - Postman and APIs

Flask REST API with a SQLite database for managing users (create, read, update, delete).

## Setup

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

`sqlite3` is built into Python, so the lab's `pip install db-sqlite3` is not needed.

## Run

```bash
python database.py
```

This creates the `users` table (if it does not exist yet) and starts the server.

The API runs at `http://127.0.0.1:5000`.

## Endpoints

| Method | Endpoint |
| --- | --- |
| GET | `/api/users` |
| GET | `/api/users/<user_id>` |
| POST | `/api/users/add` |
| PUT | `/api/users/update` |
| DELETE | `/api/users/delete/<user_id>` |

## Postman

- Collection "Flask user app" (exported): `postman/`
- The base URL is stored in the environment variable `baseURL` (`http://127.0.0.1:5000`).
- Screenshots: `postman_screenshots/`

## Notes

The database and REST code live together in `database.py`. Two fixes were made to the lab code: `conn().rollback()` became `conn.rollback()`, and database connections are now always closed.
