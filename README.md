# Car Dealership Capstone
Django starter application for dealer listings, state filtering, reviews, car makes, registration, login/logout, and required static pages.

## Run locally
```bash
python -m venv .venv
# Windows: .\.venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py seed_demo
python manage.py createsuperuser
python manage.py runserver
```
Open http://127.0.0.1:8000/ and http://127.0.0.1:8000/admin/.

## API
- GET `/api/dealers`
- GET `/api/dealers/<id>`
- GET `/api/dealers/state/Kansas`
- GET `/api/dealers/<id>/reviews`
- POST `/api/reviews` JSON `{"dealer_id":1,"name":"Alex","review":"Fantastic services"}`
- POST `/api/analyze-review` JSON `{"review":"Fantastic services"}`
- GET `/api/car-makes`
- POST `/api/auth/register` JSON `username`, `first_name`, `last_name`, `email`, `password`
- POST `/api/auth/login` JSON `username`, `password`
- POST `/api/auth/logout`

## cURL examples
```bash
curl http://127.0.0.1:8000/api/dealers
curl http://127.0.0.1:8000/api/dealers/state/Kansas
curl http://127.0.0.1:8000/api/dealers/1
curl http://127.0.0.1:8000/api/dealers/1/reviews
curl http://127.0.0.1:8000/api/car-makes
curl -X POST http://127.0.0.1:8000/api/analyze-review -H "Content-Type: application/json" -d '{"review":"Fantastic services"}'
```
Save genuine command outputs and browser screenshots under the exact filenames in your course rubric. This scaffold does not itself prove tasks were run or deployed.
