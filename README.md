# Flask API for Employee and Vehicle Assignment

## Requirements

- Python 3.x
- Flask
- Flask-CORS

## Installation

First, install the required packages:

```bash
pip install Flask Flask-CORS
```

## Running the API

Run the Flask API using the following command:

```bash
python flask_app_with_calculate.py
```

The API will be accessible at `http://localhost:5000/calculate` or `http://127.0.0.1:5000/calculate`.

## Testing with Postman

- Set the request type to "POST".
- Use the URL `http://localhost:5000/calculate` or `http://127.0.0.1:5000/calculate`
- Set "Content-Type" to "application/json" under Headers.
- Add the sample payload to the request body.

### Sample Payload

```json
{
  "vehicles": {
    "vehicle 1": {
      "capacity": 5
    },
    "vehicle 2": {
      "capacity": 5
    },
    "vehicle 3": {
      "capacity": 5
    }
  },
  "employees": {
    "udoy": {
      "zone": "north",
      "time": "10 AM"
    },
    "sajid": {
      "zone": "north",
      "time": "10 AM"
    },
    "fayez": {
      "zone": "north",
      "time": "10 AM"
    },
    "ayon": {
      "zone": "north",
      "time": "10 AM"
    },
    "yahan": {
      "zone": "north",
      "time": "10 AM"
    },
    "rakib": {
      "zone": "north",
      "time": "10 AM"
    },
    "arnab": {
      "zone": "north",
      "time": "10 AM"
    },
    "shaibal": {
      "zone": "south",
      "time": "10 AM"
    },
    "alamin": {
      "zone": "south",
      "time": "10 AM"
    },
    "nuru": {
      "zone": "west",
      "time": "10 AM"
    }
  }
}
```

### Sample Response

```json
{
  "result": [
    {
      "10 AM": {
        "alamin": "vehicle 3",
        "arnab": "vehicle 2",
        "ayon": "vehicle 1",
        "fayez": "vehicle 1",
        "nuru": "vehicle 2",
        "rakib": "vehicle 2",
        "sajid": "vehicle 1",
        "shaibal": "vehicle 3",
        "udoy": "vehicle 1",
        "yahan": "vehicle 1"
      }
    },
    {
      "10 AM": {
        "vehicle 1": {
          "assigned_employee": ["udoy", "sajid", "fayez", "ayon", "yahan"],
          "capacity": 0,
          "zone": ["north"]
        },
        "vehicle 2": {
          "assigned_employee": ["rakib", "arnab", "nuru"],
          "capacity": 2,
          "zone": ["north", "west"]
        },
        "vehicle 3": {
          "assigned_employee": ["shaibal", "alamin"],
          "capacity": 3,
          "zone": ["south"]
        }
      }
    }
  ]
}
```
