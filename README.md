# DHBW-Docker-Assignment

### 1. Anwendung erstellen:
Erstellen Sie einen neuen Ordner für Ihre Anwendung und legen Sie eine Datei ```DHBW-Docker-Assignment-App.py``` mit folgendem Inhalt an:
```
mkdir DockerTest && cd DockerTest
```
```
nano DHBW-Docker-Assignment-App.py
```
```
print("Hello World!")
```
### 2. Dockerfile erstellen:
Erstellen Sie im selben Ordner eine Datei ```Dockerfile``` mit folgendem Inhalt:

```
nano Dockerfile
```

```
FROM python:3.9

WORKDIR /DockerTest

COPY DHBW-Docker-Assignment-App.py .

CMD ["python", "DHBW-Docker-Assignment-App.py"]
```


### 3. Image erstellen:
Führen Sie den folgenden Befehl im Terminal aus, um das Image zu erstellen:

```
docker build -t DHBW-Docker-Assignment-App
```
### 4. Container ausführen:
Führen Sie den folgenden Befehl aus, um den Container zu starten und die Anwendung auszuführen:
```
docker run -it DHBW-Docker-Assignment-App
```
### 5. Image in den Docker Hub hochladen:
Melden Sie sich an Ihrem Docker Hub-Account an und markieren Sie Ihr Image als ```"public"```.

Führen Sie den folgenden Befehl aus, um das Image in den Docker Hub hochzuladen:
```
docker push DHBW-Docker-Assignment-App
```
### 6. Image auf einem anderen Rechner herunterladen und ausführen:

Auf einem anderen Rechner mit installiertem Docker führen Sie folgende Befehle aus, um das Image herunterzuladen und den Container zu starten:
```
docker pull DHBW-Docker-Assignment-App
```
```
docker run -it DHBW-Docker-Assignment-App
```
### 7. Anwendung verändern und lokal speichern:

Verändern Sie den Inhalt der Datei ```DHBW-Docker-Assignment-App.py``` auf dem ersten Rechner.

Führen Sie den folgenden Befehl aus, um ein neues Image mit den Änderungen zu erstellen:
```
docker build -t DHBW-Docker-Assignment-App
```
Speichern Sie das Image lokal mit dem folgenden Befehl:
```
docker save DHBW-Docker-Assignment-App > DHBW-Docker-Assignment-App.tar
```
### 8. Image auf einem anderen Rechner laden und ausführen:

Kopieren Sie die Datei ```DHBW-Docker-Assignment-App.tar``` auf den anderen Rechner.

Führen Sie den folgenden Befehl aus, um das Image zu laden:
```
docker load < DHBW-Docker-Assignment-App.tar
```
Führen Sie den folgenden Befehl aus, um den Container mit der neuen Version der Anwendung zu starten:
```
docker run -it DHBW-Docker-Assignment-App
```
