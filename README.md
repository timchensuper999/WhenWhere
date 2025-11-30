# WhenWhere

DST‑safe, timezone‑aware meeting planner for cross‑continent coordination.

## Features
- One‑to‑many time conversion across all supported cities  
- Point or range conversion between two cities  
- Multi‑city overlapping “same local window” computation  
- Full DST correctness via IANA timezones

## Run Locally

### Backend (FastAPI)
```bash
python -m venv .venv
source .venv/bin/activate  # windows: .venv\Scripts\activate
pip install fastapi uvicorn pydantic pytz
uvicorn backend.app:app --reload
```

### Frontend
Open `index.html` in a browser.  
Frontend expects API at `http://127.0.0.1:8000`.

---

## API

### GET /cities
Returns a list of supported city names.

### POST /compute
Body fields determine which computation mode is used:
- 1 city, no end → ALL_AT_POINT  
- 2 cities, no end → PAIR_AT_POINT  
- 2 cities + end → PAIR_RANGE  
- ≥2 cities + end → N_SAME_LOCAL  

---

## Roadmap
- Better overlapping‑window visualization  
- City fuzzy search  
- Shareable URL presets  
- Docker support

## License
TBD.
