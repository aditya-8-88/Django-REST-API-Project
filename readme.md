# DjangoRESTful

This project is a simple Django REST API for managing a collection of drinks. Users can retrieve, create, update, and delete drink records using RESTful endpoints.

---

## Prerequisites

1. **Python** (3.8 or later)
2. **Django** 
3. **Django REST Framework**
4. **MySQL** running on the default port (3306)
5. **Postman** (or any API testing tool): To test the REST endpoints.

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone git@github.com:aditya-8-88/Django-REST-API-Project.git
cd Django-REST-API-Project
```

### 2. Install Dependencies  

Create a virtual environment and install the required Python packages:

```bash
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
pip install -r requirements.txt
```
### 3. Configure MySQL Database

Update the settings.py file with your MySQL database credentials:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': '<database_name>',
        'USER': '<username>',
        'PASSWORD': '<password>',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 4. Apply Migrations

Run the following commands to apply migrations:

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Start the Development Server

```bash
python manage.py runserver
```





## API Endpoints

### Base URL:
```http://127.0.0.1:8000```

### Endpoints:

#### 1. Get All Drinks  
- URL: ```http://127.0.0.1:8000/getDrinks/```  
- Method: **GET**  
- Response: 
```json
   {
     "drinks": [
         {
            "id": 1,
            "name": "Coke",
            "description": "Carbonated soft drink"
         },
         {
            "id": 2,
            "name": "Pepsi",
            "description": "Another carbonated soft drink"
         }
     ]
   }

```
#### 2. Create a New Drink  
- URL: ```http://127.0.0.1:8000/getDrinks/```
- Method: **POST**
- Request Body (Example):
``` json
   {
      "name": "Sprite",
      "description": "Lemon-lime soda"
   }
```
- Response:
```json
   {
      "id": <Some ID>,
      "name": "Sprite",
      "description": "Lemon-lime soda"
   }

```

#### 3. Get a Single Drink
- URL: ```http://127.0.0.1:8000//getDrink/1/```
- Method: **GET**
- Response (Example):

```json
   {
      "id": 1,
      "name": "Coke",
      "description": "Carbonated soft drink"
   }

```

#### 4. Update a Drink
- URL: ```http://127.0.0.1:8000/getDrink/<DrinkID>/```
- Method: **PUT**
- Request Body (Example):
```json
 {
    "name": "Coke Zero",
    "description": "Zero sugar carbonated soft drink"
 }
```
- Response:
```json
   {
      "id": 1,
      "name": "Coke Zero",
      "description": "Zero sugar carbonated soft drink"
   }

```

#### 5. Delete a Drink
- URL: ```http://127.0.0.1:8000/getDrink/<int:id>/```
- Method: **DELETE**
- Response:
```json
   {
      "detail": "No content"
   }

```
### Notes
1. Ensure your MySQL server is running before starting the project.
   - To start the MySQL service:  

        ```bash
          sudo systemctl start mysql
        ```
   - Use a tool like Postman or ```curl``` to test the API endpoints.

### Additional Features
- Admin Panel: Visit /admin/ to manage data manually.
- Extendable Models: Modify the Drink model in models.py to add more fields.
- Serialization: Modify the DrinkSerializer in serializers.py as needed.

### Contribution
Feel free to fork this repository and submit pull requests to enhance the API.

### License
This project is open-source and available under the MIT License.
