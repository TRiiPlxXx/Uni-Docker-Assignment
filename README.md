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
### 5. Image in den Docker Hub hochladen:
Melden Sie sich an Ihrem Docker Hub-Account an und markieren Sie Ihr Image als ```"public"```.

Führen Sie den folgenden Befehl aus, um das Image in den Docker Hub hochzuladen:
```
docker build -t jsnwolfer/dhbw-docker-assignment-app:latest .
```
```
docker push jsnwolfer/dhbw-docker-assignment-app:latest
```
### 6. Image auf einem anderen Rechner herunterladen und ausführen:

Auf einem anderen Rechner mit installiertem Docker führen Sie folgende Befehle aus, um das Image herunterzuladen und den Container zu starten:
```
docker pull dhbw-docker-assignment-app
```
```
docker run -it dhbw-docker-assignment-app
```
### 7. Anwendung verändern und lokal speichern:

Verändern Sie den Inhalt der Datei ```dhbw-docker-assignment-app.py``` auf dem ersten Rechner.

Führen Sie den folgenden Befehl aus, um ein neues Image mit den Änderungen zu erstellen:
```
docker build -t dhbw-docker-assignment-app
```
Speichern Sie das Image lokal mit dem folgenden Befehl:
```
docker save dhbw-docker-assignment-app > dhbw-docker-assignment-app.tar
```
### 8. Image auf einem anderen Rechner laden und ausführen:

Kopieren Sie die Datei ```dhbw-docker-assignment-app.tar``` auf den anderen Rechner.

Führen Sie den folgenden Befehl aus, um das Image zu laden:
```
docker load < dhbw-docker-assignment-app.tar
```
Führen Sie den folgenden Befehl aus, um den Container mit der neuen Version der Anwendung zu starten:
```
docker run -it dhbw-docker-assignment-app
```
