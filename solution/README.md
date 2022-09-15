docker run -d infracloudio/csvserver:latest
docker ps -a
docker logs b6271bdc7aeb
docker cp inputFile  jolly_nash:/csvserver/ 
docker exec -it jolly_nash sh
sh-4.4# netstat -nltp
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp6       0      0 :::9300                 :::*                    LISTEN      1/csvserver

docker run -d -t -i -p 9393:9300 -e CSVSERVER_BORDER=Orange infracloudio/csvserver:latest
