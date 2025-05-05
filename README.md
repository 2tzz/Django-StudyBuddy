
---

# Django StudyBuddy

**StudyBuddy** is a full-stack web application that helps students connect, create study rooms, and engage in topic-based discussions.

Built using **Django** for the backend and extended with **Django REST Framework (DRF)** to expose a flexible, scalable **REST API**, this app supports both traditional web views and RESTful access for frontend or mobile clients.

---

## Features

- ✅ User Authentication (Login/Register)
- ✅ Create and join study rooms
- ✅ Topic-based filtering and search
- ✅ User profile management
- ✅ Full RESTful API (built with DRF)

---

## Technologies Used

- **Backend**: Django, Django REST Framework (DRF)
- **Frontend**: HTML, CSS, JavaScript (templating)
- **Database**: SQLite (default)
- **API**: JSON-based REST API
- **Auth**: Django's built-in authentication system

---

## 🔍 What is Django REST Framework?

[Django REST Framework (DRF)](https://www.django-rest-framework.org/) is a powerful toolkit for building **Web APIs** with Django.  
It lets you expose your data as **JSON endpoints**, making it easy to:

- Connect a frontend like React or Vue
- Power mobile apps
- Reuse logic between the web and API
- Support CRUD operations programmatically

### Example DRF View:
```python
from rest_framework.views import APIView
from rest_framework.response import Response
from .models import Room
from .serializers import RoomSerializer

class RoomListView(APIView):
    def get(self, request):
        rooms = Room.objects.all()
        serializer = RoomSerializer(rooms, many=True)
        return Response(serializer.data)
```

---

## Installation

```bash
git clone https://github.com/2tzz/Django-StudyBuddy.git
cd Django-StudyBuddy
python -m venv env
source env/bin/activate  # Windows: env\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Visit: [http://localhost:8000](http://localhost:8000)

---

## API Endpoints (via DRF)

| Method | Endpoint         | Description         |
|--------|------------------|---------------------|
| GET    | `/api/rooms/`    | List all rooms      |
| POST   | `/api/rooms/`    | Create a new room   |
| GET    | `/api/rooms/<id>`| Retrieve a room     |
| PUT    | `/api/rooms/<id>`| Update a room       |
| DELETE | `/api/rooms/<id>`| Delete a room       |

---

## Folder Structure

```
studybuddy/
├── core/            # Django app with views, models
├── api/             # Django REST Framework API views
├── templates/       # HTML templates
├── static/          # Static assets
├── db.sqlite3
└── manage.py
```

---

## Contributing

Pull requests and suggestions are welcome.  
Please fork the repo and open a PR.

---

## License

MIT License

---
