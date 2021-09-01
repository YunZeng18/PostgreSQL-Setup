# How to Install and Set Up PostgreSQL Database on Ubuntu 20.04 locally

https://linuxhint.com/install_postgresql_-ubuntu/

1. $ sudo apt update
2. $ sudo apt upgrade
3. $ sudo apt install postgresql
4. optional: check default port 5432 $ ss -nlt
5. optional: startup settings of the PostgreSQL Server after system boot-up $ sudo systemctl disable postgresql
6. $ sudo gedit /etc/postgresql/12/main/postgresql.conf  
   change listen_addresses = ‘localhost’ to listen_addresses = ‘\*’
7. $ sudo systemctl restart postgresql
8. $ sudo gedit /etc/postgresql/12/main/pg_hba.conf  
   add this line to the end to allow an incoming client to connect your databases and users  
   host all all 0.0.0.0/0 md5
9. $ sudo ufw allow from any to any port 5432 proto tcp  
   make sure that the firewall does not stop incoming connections through the PostgreSQL port 5432
10. $ sudo -i -u postgres
11. $ psql
    you are now in postgreSQL!
