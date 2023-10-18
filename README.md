# Hoppscotch lokal einrichten

## Browser-Exension installieren
[Chrome](https://chrome.google.com/webstore/detail/hoppscotch-browser-extens/amknoiejhlmhancpahfcfcfhllgkpbld)

## Docker Setup

### Vorbereitung
Die Datei `.env.example` zu `.env` umbenennen.
Eine [neue Applikation](https://github.com/settings/applications/new) in GitHub erstellen, damit man sich einloggen kann.
Anschießend ID und Secret in die `.env`-Datei unter GitHub eintragen.

### Container Starten
```bash
docker compose up -d
```

### Migrations ausführen
Eine Konsle für den Docker-Container der App öffnen

```sh
docker exec -it hoppscotch sh
```

Anhscließend die Migartion ausführen
```sh
pnpx prisma migrate deploy
```

## Chrome Extension einrichten
Um CORS-Probelem zu vermeiden muss die aktuelle Hoppscotch-URL entsprechend hinterlegt werden.
Default sollte der Origin `http://localhost:3000` mit der Extension hinzgefügt werden.

## Hoppscotch nutzen
Im Browser die URL `http://localhost:3000` öffnen und sich mit GitHub anmelden.
Den Admin-Status kann man sich nachher auch mit der Datenbank freigeben.

Nun sollte Hoppscotch nutzbar sein und auch lokale Testumgebungen aufrufen können.