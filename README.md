# Pgbouncer Stack

## Parameters

### userlist.txt

Content of userlist.txt. When using `md5` in `pg_hba.conf`, generate the md5 password with:

```shell
$ echo -n "md5"; echo -n "<password><user>" | md5sum | awk '{print $1}'
```

Then fill in `userlist.txt` with one line per allowed user:

```
"<user>" "<md5_password>"
```

### pg_hba.conf

This is a standard `pg_hba.conf` file, e.g.:

```
host       <database> <user>  <from_network>  md5
```


### Target host

Select the service that should be targetted by the bouncer.


### Listen port

The port used to publish the Pgbouncer service.
