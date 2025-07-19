# Genkit PostgreSQL Plugin

This plugin provides a Genkit flow to interact with a PostgreSQL database.

## Installation

```bash
npm install
```

## API

### `postgresFlow(ai)`

Creates a new flow to execute a query against a PostgreSQL database.

-   `ai`: Your Genkit AI instance.

#### Input

The flow expects an object with the following properties:

-   `user`: Your PostgreSQL username.
-   `host`: The database host.
-   `database`: The name of the database.
-   `password`: The password for the database user.
-   `port`: The port number for the database.
-   `query`: The SQL query to execute.

#### Output

The flow returns the rows from the executed query.

## Example

```typescript
import { configureGenkit } from '@genkit-ai/core';
import { postgresFlow } from 'genkitx-plugin-postgres';

export default configureGenkit({
  plugins: [postgresFlow],
  logLevel: 'debug',
  enableTracingAndMetrics: true,
});

// To run the flow:
// genkit flow:run postgresFlow '{"user": "your_user", "host": "your_host", "database": "your_db", "password": "your_password", "port": 5432, "query": "SELECT * FROM your_table"}'
```
