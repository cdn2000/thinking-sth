# postgresql 经验
### show all
    \list or \l   --show databases
    \dt           --show tables
    \du           --show users
### psql -h localhost mydb -W ----error
change /var/lib/pgsql/data/pg_hba.conf  
__From__:

    host    all             all             127.0.0.1/32            ident 
__To__:

    host    all             all             127.0.0.1/32            md5
### change user's passwd.
    \password

