# Flight Search App

## Overview

The **Flight Search App** allows users to search for flights from a specified airport, view available destinations, and save their favorite routes. The app interacts with a relational database using **Room** for persistent data storage and **Preferences DataStore** to store simple data, such as the user's recent search queries.

This project is designed to practice SQL, Room, and DataStore integration in an Android app.

## Prerequisites

Before running the app, make sure you have:

- **Android Studio** installed on your computer
- Basic knowledge of SQL for reading and manipulating a relational database
- Experience with using Room in an Android app to interact with a database
- Knowledge of using DataStore to persist simple data
- Ability to build moderately complex user interfaces with XML Views

## Features

- **Search Airport**: Allows the user to enter an airport name or IATA code, and provides autocomplete suggestions from a pre-populated database.
- **View Flights**: Displays available flights from the selected airport to all other airports.
- **Save Favorites**: Users can save their favorite routes (departure and destination airports).
- **Persist Search**: The search text is saved using Preferences DataStore, so the search field is pre-populated when the app is reopened.

## Database

The app uses a **SQLite database** with the following two tables:

### Airport Table
| Column       | Data type | Description                              |
|--------------|-----------|------------------------------------------|
| `id`         | INTEGER   | Unique identifier (primary key)          |
| `iata_code`  | VARCHAR   | 3 letter IATA code                       |
| `name`       | VARCHAR   | Full airport name                        |
| `passengers` | INTEGER   | Number of passengers per year            |

### Favorite Table
| Column           | Data type | Description                              |
|------------------|-----------|------------------------------------------|
| `id`             | INTEGER   | Unique identifier (primary key)          |
| `departure_code` | VARCHAR   | IATA code for departure                  |
| `destination_code`| VARCHAR  | IATA code for destination                |

### Database Queries
- Autocomplete airport search using `LIKE` for airport names and IATA codes.
- Display airports sorted by the number of passengers in descending order.
- List flights (departure and destination) when an airport is selected.
- Show saved favorite routes when no search query is entered.

## UI Design

### Main Screen
- Text field to enter airport names or IATA codes.
- Autocomplete suggestions as the user types.
- When a suggestion is selected, a list of flights from the selected airport is displayed.
- If no search query is entered, display a list of saved favorite routes.

## How to Use

1. Open the app on your Android device.
2. Enter an airport name or IATA code in the text field to get autocomplete suggestions.
3. Select a suggestion to view available flights.
4. Save your favorite routes by clicking the "Save" button next to each flight.
5. When reopening the app, the text field will be pre-populated with the last search query. If the text field is empty, the app will display your saved favorite routes.

## Technologies Used

- **Room**: To integrate and manage the SQLite database in the app.
- **Preferences DataStore**: To store user preferences like the search query.
- **SQL**: To perform queries on the database, including text searches and sorting.
- **Kotlin**: Programming language for developing the app.
- **Android XML Views**: For building the user interface.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/deonrtan2/cc17-3k-tandeonr-act9.git
