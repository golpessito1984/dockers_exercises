
1º Run a nginx, a mysql, and a httpd (apache) server

2º Run all ot them --detach ( -d ), name them with --name

3º nginx should listen on 80:80, httpd on 8080:80, mysql on 3306:3306

4º When running mysql, user the --env option ( or -e ) to pass in 
   MYSQL_RANDOM_ROOT_PASSWORD=yes

5º Use docker container logs on mysql to find the random password it created on startup

6º Clean it all with docker container stop and docker container rm 

7º User docker container ls to ensure everthing is correct before and after cleanup
