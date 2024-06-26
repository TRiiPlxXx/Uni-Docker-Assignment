# DHBW-Docker-Assignment

### 1. Anwendung erstellen:
Erstellen Sie einen neuen Ordner für Ihre Anwendung und legen Sie eine Datei ```dhbw-docker-assignment-app.py``` mit folgendem Inhalt an:
```
mkdir DockerTest && cd DockerTest
```
```
nano dhbw-docker-assignment-app.py
```
```
while True:
  print("Hello World!")
```
### 2. Dockerfile erstellen:
Erstellen Sie im selben Ordner eine Datei ```dockerfile``` mit folgendem Inhalt:

```
nano dockerfile
```

```
FROM python:3.9

WORKDIR /DockerTest

COPY dhbw-docker-assignment-app.py .

CMD ["python", "dhbw-docker-assignment-app.py"]
```


### 3. Image erstellen:
Führen Sie den folgenden Befehl im Terminal aus, um das Image zu erstellen:

```
docker build -t dhbw-docker-assignment-app .
```
### 4. Container ausführen:
Führen Sie den folgenden Befehl aus, um den Container zu starten und die Anwendung im Hintergrund auszuführen:
```
docker run -d dhbw-docker-assignment-app
```
Zum veranschaulichen, dass der Container im Hintergrund läuft:
```
docker logs [CONTAINER]
```

### 5. Image in den Docker Hub hochladen:
Melden Sie sich an Ihrem Docker Hub-Account an und markieren Sie Ihr Image als ```"public"```.

Führen Sie den folgenden Befehl aus, um das Image in den Docker Hub hochzuladen:
```
docker login
```
```
docker build -t jsnwolfer/dhbw-docker-assignment-app:latest .
```
```
docker push jsnwolfer/dhbw-docker-assignment-app:latest
```
### 6. Image auf einem anderen Rechner herunterladen und ausführen:

Auf einem anderen Rechner mit installiertem Docker führen Sie folgende Befehle aus, um das Image herunterzuladen und den Container zu starten:
```
docker pull jsnwolfer/dhbw-docker-assignment-app
```
```
docker run -d jsnwolfer/dhbw-docker-assignment-app
```
Zum veranschaulichen, dass der Container im Hintergrund läuft:
```
docker logs [CONTAINER]
```
