# Periodic Table Database

This project is a PostgreSQL database implementation of the periodic table, including elements, their properties, and types. It provides a script for querying element information based on atomic number, symbol, or name.

## Features

- Store information about chemical elements, including:
  - Atomic number
  - Name
  - Symbol
  - Atomic mass
  - Melting and boiling points
  - Element type (metal, nonmetal, metalloid)
- A Bash script (`element.sh`) to retrieve element information from the database.
- Capable of handling user input for various queries.

## Database Structure

### Tables

1. **elements**
   - `atomic_number` (INTEGER, PRIMARY KEY)
   - `name` (VARCHAR, NOT NULL, UNIQUE)
   - `symbol` (VARCHAR, NOT NULL, UNIQUE)

2. **properties**
   - `atomic_number` (INTEGER, PRIMARY KEY, FOREIGN KEY REFERENCES elements(atomic_number))
   - `atomic_mass` (DECIMAL, NOT NULL)
   - `melting_point_celsius` (DECIMAL, NOT NULL)
   - `boiling_point_celsius` (DECIMAL, NOT NULL)
   - `type_id` (INTEGER, NOT NULL, FOREIGN KEY REFERENCES types(type_id))

3. **types**
   - `type_id` (INTEGER, PRIMARY KEY)
   - `type` (VARCHAR, NOT NULL)

## Setup

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd periodic_table
##Connect to the PostgreSQL database:

-bash

psql --username=freecodecamp --dbname=periodic_table

###Running the Script
To see all available commands and how to use the script, run:

-bash

./element.sh
