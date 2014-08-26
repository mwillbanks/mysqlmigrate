# mysqlmigrate

A MySQL database migration tool in bash.

## Foundations

* We only migrate up, not down.
* Hook into existing mysql command line tools
* Use natural sorting order for execution
* No fansy pansy shit
* Just works

## General Usage

```
Usage: ./mysqlmigrate [options]

MySQL Migrations

OPTIONS:
   -h      Show this message
   -c      Configuration file (Defaults to ./my.cnf)
   -m      Migrations directory (Defaults to ./migrations)
   -o      Output file
```

## Getting Started

1. Create a my.cnf file containing your information

           [client]
           host=localhost
           username=migrations
           password=m1gr4710ns
           database=application

2. Create a migrations folder, add .sql files into it

3. Execute the program and you're done

## Other Notes

* This script will not escape file names, so don't be an idiot and use crappy
  files names with null bytes, single quotes, etc.
* Each changeset is wrapped into a transaction
* This script literally attempts to do the least amount possible
* Once a SQL script is run, it will not be run again.
