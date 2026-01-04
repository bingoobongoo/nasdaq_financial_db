# Nasdaq financial database

UPDATE: Since yfinance updated their API, downloading OLHC data and calculating indicator data no longer works. Only the financial data (quarterly statements and ratios) can be saved to the database.

**Platform:** WSL Ubuntu

## Installation

Here are all the steps to run the project on your computer.

Install `postgresql`:

```text
sudo apt update
sudo apt install postgresql postgresql-contrib
```

Confirm the installation:

```text
psql --version
```

Give `postgres` user a password:

```text
sudo passwd postgres
```

Close and reopen terminal, then type:

```text
sudo service postgresql start
```

Now, when postgreSQL is installed, clone this repository:

```text
git clone https://github.com/bingoobongoo/nasdaq_financial_db.git
cd ./nasdaq_financial_db
```

Install all required packages:

```text
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## Creating database

Make sure you have stable network connection and run:

```text
python3 main.py postgres <password> <databaseName>
```

Additionally, you can also specify **port** on which postgreSQL is running (default is 5432):

```text
python3 main.py postgres <password> <databaseName> <port>
```

After this you can minimize the terminal window and wait until database is created.
> The whole process can take approximately 20 minutes.

## Database

Database schema is saved as a ***nasdaq_companies_backup.tar*** file. For more details about database (i.e entities, attributes and relationships) check the [***DATABASE.md***](DATABASE.md) file.

> Note that the ***nasdaq_companies_backup.tar*** file is just a schema for database. The actual data is downloaded using ***main.py*** script.