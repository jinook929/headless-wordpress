# Based on the Current `docker-compose.yml` file (2022.10.06)

0. have **Docker Desktop** on your machine

1. execute `docker compose up` in terminal (root folder)

2. go to `localhost:8181` (credentials: *mysql:3306*, *madwell*, *madwell*),
   then import db sql file (e.g. madwell.sql) file from team/dev/prod

3. go to `localhost:8888/wp-admin` (credentials: *madwell*, *madwell*)

4. check/choose **Twenty Twenty-One** theme for multiple menus
5. check/set **Menus** > **Locations**: *Primary* -> *Header*, *Secondary* -> *Footer*

6. save **Permalinks** setting in Settings, preferably **Post name**

7. install plugins (listed in `/wordpress/composer.json` file)
   use `composer update` or, in case it doesn't work, install them manually

- how to update upload_max_filesize (when uploading zip file is too big)
  - via editing `.htaccess` file: add lines below to the top or bottom: 
  `php_value upload_max_filesize 256M`
  - via terminal (find docker container id by `docker ps`, then below...): 
  `docker container exec -it [CONTAINER ID] bash -c "echo 'php_value upload_max_filesize 256M' > '/var/www/html/.htaccess'"`

8. copy & paste `/wp-content/uploads` folder from team/dev/prod

9. click **Update** button on **GraphQL Gutenberg** admin