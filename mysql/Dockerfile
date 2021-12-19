FROM mysql:8.0.0

#mysql

COPY basket.sql ./home
COPY script.sh ./home
# CMD  mysql sh -c 'exec mysql -uroot -psecret' < /home/basket.sql
# CMD mysql -u root  --password=secret -h 127.0.0.1 -P 3306 --protocol=tcp  < /home/basket.sql 
# CMD mysql -uroot -p"secret" < /home/basket.sql