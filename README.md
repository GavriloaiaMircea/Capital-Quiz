# WorldCapitalQuiz

WorldCapitalQuiz is a web application that allows users to test their knowledge of world capitals. Users are presented with a random country, and they need to type in the correct capital.

## Features

- **Quiz Game:** Users guess the capital city for a given country.
- **Score Tracking:** The application keeps track of the user's score.
- **Random Question Selection:** Each question is randomly selected from a database of countries and capitals.

## Technologies Used

- **Node.js:** Runtime environment for executing JavaScript code on the server.
- **Express.js:** Web framework for Node.js to manage routing and requests.
- **PostgreSQL:** Database for storing countries and capitals.
- **EJS (Embedded JavaScript):** Templating engine for rendering HTML views dynamically.
- **pg (node-postgres):** PostgreSQL client for Node.js.
- **CSS:** For styling the user interface.

## How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/GavriloaiaMircea/Capital-Quiz.git
cd Capital-Quiz
```

### 2. Set Up the PostgreSQL Database

1. Open pgAdmin or use a PostgreSQL command-line client.

2. Create a new database named `World` (or another name if you prefer, but remember to update the connection details in the code).

3. Create a table called `capitals` with the following structure:

    ```sql
    CREATE TABLE capitals (
      id SERIAL PRIMARY KEY,
      country VARCHAR(255),
      capital VARCHAR(255)
    );
    ```

4. Import the data from `capitals.csv` into the `capitals` table. In pgAdmin, this can be done by right-clicking on the table, selecting Import/Export, and choosing the CSV file from the repository.

### 3. Update the Database Connection

In the `index.js` file, update the connection details for your PostgreSQL database. The details should match your PostgreSQL setup:
```javascript

    const db = new pg.Client({
      user: "your_postgres_user",
      host: "localhost",
      database: "World", // or your custom database name
      password: "your_password",
      port: 5432,
    });
```

### 4. Install Dependencies

Run the following command to install all necessary dependencies:
```bash
    npm install
```

### 5. Start the Application

Once everything is set up, start the application:

```bash
    node index.js
```

Open your browser and navigate to [http://localhost:3000](http://localhost:3000) to start playing the quiz.

## How It Works

The application connects to a PostgreSQL database containing a list of countries and their capitals.
A random country is selected from the database and displayed to the user.
The user inputs their guess for the capital, and the application checks if the answer is correct.
The score is updated, and the next country is presented.
