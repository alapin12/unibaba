# Unibaba

**A peer-to-peer marketplace for UNSW students.** Students can buy and sell textbooks, gear and other items on campus, message each other about listings, and rate sellers.

Built in one weekend at **UNIHACK 2025** by a team of five UNSW students.

▶️ **[Watch the demo video](https://www.youtube.com/watch?v=Y9ku9ZArkKs)**

---

## Features

- **UNSW-only accounts:** signup is limited to `@ad.unsw.edu.au` email addresses, so everyone on the marketplace is a verified student
- **Listings:** create, edit, delete and mark items as sold, with image uploads and categories
- **Search and filters:** search by keyword across names and descriptions, and filter by category
- **Buyer–seller messaging:** each listing has its own conversation thread, collected in a personal inbox
- **Seller ratings:** a 0–5 star rating system (updated over AJAX), with an average score on each seller's dashboard
- **Seller dashboard:** manage your listings and see recent reviews in one place
- **Campus meet-up map:** item pages include an interactive Leaflet map centred on UNSW

## Tech stack

| Layer     | Tools |
|-----------|-------|
| Backend   | Python, Django 5.1 (built-in auth, ORM, class-based login views) |
| Database  | SQLite |
| Frontend  | Django templates, Tailwind CSS, Bootstrap, vanilla JS / jQuery |
| Other     | Pillow (image uploads), Leaflet.js (maps) |

## Project structure

```
market/         Project settings and root URL config
base/           Landing page, signup, login and logout
item/           Item and Category models, plus listing CRUD, search and filters
conversation/   Buyer–seller message threads and inbox
rating/         Seller rating model and the AJAX rating endpoint
dashboard/      Seller dashboard
static/         Shared CSS and JS
```

## Running locally

```bash
git clone https://github.com/alapin12/unibaba.git
cd unibaba
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser   # optional: lets you add categories in /admin
python manage.py runserver
```

Then open http://127.0.0.1:8000.

> **Note:** add at least one category through the Django admin (`/admin`) before creating a listing.

### Configuration

The defaults work for local development. For any deployment, set these environment variables:

| Variable               | Default                   |
|------------------------|---------------------------|
| `DJANGO_SECRET_KEY`    | an insecure dev-only key  |
| `DJANGO_DEBUG`         | `True`                    |
| `DJANGO_ALLOWED_HOSTS` | `localhost,127.0.0.1`     |

## Team

Built at UNIHACK 2025 by five UNSW students.
