---
title: MariaDB Settings
date: 2024-08-25 22:58:00
categories: [database]
tags: [database, mariadb, mysql, configuration]
---

# MariaDB Configuration

This is a pain in the ass that took me the entire weekend to figure out what is wrong. In the end, I give up and reinstall mariadb entirely.

But here are some resources that helps a lot when it comes to the understanding what is MariaDB:

- [Migrate from MySQL to MariaDB](https://codewithsusan.com/notes/migrate-mysql-to-mariadb)
- Getting Started with MariaDB by Daniel Bartholow

## Encryption on MariaDB

There are two places you can do encryption in MariaDB:

- **At-Transit**: the communication channel between client and server will be encrypted, usually via TLS or SSL
- **At-Rest**: the actual database on the hard disk is encrypted using AES, such that if the disk is lost, they won't be able to fetch the content within

### Encryption at Rest

TODO
