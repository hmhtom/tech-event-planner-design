# Tech Event Planner View Rendering API

- [Homepage](#homepage)
  - [Variables](#variables)
- [Login Page](#login-page)
- [Dashboard Page](#dashboard-page)
  - [Variables](#variables-1)
- [Create Event Page](#create-event-page)
  - [Variables](#variables-2)
- [Update Event Page](#update-event-page)
  - [Variables](#variables-3)
- [Event Page](#event-page)
  - [Variables](#variables-4)

## Homepage

- Route: `/`
- Method: `GET`
- View Rendering: `homepage`
- Query
  - category_id(optional)
  - page(optional)
- Need Authentication: No

### Variables

- `events`

```JSON
[
    {
        "id"
        "title"
        "description"
        "date"
        "location"
        "user_id"
        "category_id"
        "createdAt"
        "updatedAt"
        "creator": {
            "id"
            "username"
        }
    },
    ......
]
```

- `categories`

```JSON
[
    {
        "id"
        "name"
    },
    ......
]
```

- `current_user_id`
- `current_username`
- `logged_in`

## Login Page

- Route: `/login`
- Method: `GET`
- View Rendering: `login`
- Need Authentication: No

## Dashboard Page

- Route: `/dashboard`
- Method: `GET`
- View Rendering: `dashboard`
- Need Authentication: Yes

### Variables

- `user`

```JSON
{
    "id"
    "username"
    "email"
    "created": [
        {
            "id"
            "title"
            "description"
            "date"
            "location"
            "user_id"
            "category_id"
            "createdAt"
            "updatedAt"
        },
        ......
    ],
    "attend": [
        {
            "id"
            "title"
            "description"
            "date"
            "location"
            "user_id"
            "category_id"
            "createdAt"
            "updatedAt"
            "participant": {
                "id"
                "user_id"
                "event_id"
            },
            "creator": {
                "id"
                "username"
                "email"
            }
        },
        ......
    ]
}
```

- `current_user_id`
- `current_username`

## Create Event Page

- Route: `/dashboard/new-event`
- Method: `GET`
- View Rendering: `new-event`
- Need Authentication: Yes

### Variables

- `current_user_id`

## Update Event Page

- Route: `/dashboard/update-event/:id`
- Method: `GET`
- View Rendering: `new-event`
- Need Authentication: Yes

### Variables

- `current_user_id`

## Event Page

- Route: `/event/:id`
- Method: `GET`
- View Rendering: `event`
- Need Authentication: No

### Variables

- `event`

```JSON
{
    "id"
    "title"
    "description"
    "date"
    "location"
    "user_id"
    "category_id"
    "createdAt"
    "updatedAt"
    "creator": {
        "id"
        "username"
        "email"
    },
    "attendee": [
        {
            "id"
            "username"
            "email"
        }
    ]
}
```

- `current_user_id`
- `current_username`
- `logged_in`
