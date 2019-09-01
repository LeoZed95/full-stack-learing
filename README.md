# Car dealer website
This project is a simple demonstration of a website that could be used for selling cars or displaying any other data stored in a database. It has been tested on a Raspberry Pi 4.

![](screenshot/screenshot.png)
The website is dynamically generated, with the table size and the number of dropdown buttons and elements depending on the amount of data and columns in the database. Users can filter values for each parameter using dropdown buttons, selecting the desired value. Each filter reduces the amount of data displayed in the table and updates the number of options available in the dropdown lists. Both the table data and dropdown elements are fetched from APIs that query the database after each user selection.

## Database
A simple PostgreSQL database has been created with sample car data, including three parameters: color, number of seats, and class.

To import the database, use the following command in the terminal:
```
psql -U username dbname < dbexport.pgsql
```
Ensure that your PostgreSQL server is using port 5432 (the default). If it is using a different port, update the server connection configuration accordingly. It is also recommended to create a separate database user with only SELECT privileges for enhanced security.

## Server

The project is structured with two subdirectories: server and frontend. This structure is important as the startup script relies on this path.

For the server, Node.js has been used. Configure it as follows (run these commands inside the server directory):

```commandline
npm init -y
```
```
npm install concurrently cors express pg body-parser
```
```
npm install concurrently cors express pg body-parser
```
```
npm install concurrently --save-dev nodemon
```

## Frontend

The frontend was built using React.js. To set it up, run the following command from the project’s root directory:

```
npm init react-app ./frontend
```

## Running both server and client
To run both the server and client, execute the following command from the server directory:

```commandline
npm run both
```
If you encounter any issues, try using the --verbose flag for more detailed output.

This project is not intended for use as a production website but served well for testing purposes. The performance was satisfactory, with website build times around 70-100 ms and API fetch times ranging from 15-40 ms.