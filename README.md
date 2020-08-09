🅿🅾🆂🆃🅶🆁🅴🆂🆀🅻

# PostgreSQL-tutorial-documentation
A complete walk through guide to master on PostgreSQL

[Follow me on LinkedIn](https://www.linkedin.com/in/cinmoys-here/)

This Documentation includes:
- [Introduction](#introduction)
- [Installation](#installation)
- [Getting Started](#your-first-step)
 - [Creating Database](#creating-database)
 - [Connect database](#connecting-to-database)
 - [Creating Table](#creating-table)
 - [Insert into](#insert-into)

> I used Windows 10 (64-bit) operating system to run all the codes and procedures.

# 🚧 Installation

Make sure your hard disk have enough space for installation.Then Download the installer file from the link.Download the latest version of your computer architecture.
> [Download from here(For windows users)](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)

Other operating system users can download from this [link](https://www.postgresql.org/download/)

Run the installer file.Installation process is like any other software but make sure you mark the following items correctly.
- PostgreSQL Server
- pgAdmin
- Stack Builder
- Command Line Tools

![alt text](images/insatallation.png)

After you finish you can run either `SQL Shell (psql)` for command line client or `pgAdmin 4` for GUI client.You are now ready to go.


# Your first step
As our pc serves as a server(database server) we need a client with which we can connect,view the contents and modify them. In Three ways we can do it.

- GUI client (`pgAdmin 4`)
- Terminal/cmd (`SQL Shell`)
- Application

I will use mostly terminal/cmd for my future works as it is a good habit and helps a lot during real projects.


Run the SQL Shell (psql).As you are running it for the first time your default server[localhost], Database [postgres], port [5432], Username [postgres].So you need to press just `enter`.Password is the superuser password that you set during installation.
<p align="center">
	<img src="https://i.ibb.co/L5KPXvs/getting-started.png" alt="getting-started" border="0">
</p>

For windows you can operate from `command prompt` also.You have to add the `PostgreSQL` bin directory in the system path (add in path under environment variables).
Open command prompt.Run-

`psql -U postgres`

provide your superuser password.You are done.😁 

## Creating database
Before starting things be familiar with the terminal environment and basic navigation commands.
Remember psql or SQL commands are not case sensetive.But you are advised to use the **UPPERCASE** letter in the commands. 

Run - 

`CREATE DATABASE test;`

## Connecting to database

You can connect a database in a various way.
- **Case 1**
 - You can simply use this command to connect a database `cinmoy` if user remains same : `\c cinmoy`
- **Case 2**
 - If credentials are different then: `\c DBNAME USER HOST PORT`
- ** Case 3**
 - Or you can just connect from windows cmd : `psql DBNAME USER`

## Creating Table


## Insert Into

