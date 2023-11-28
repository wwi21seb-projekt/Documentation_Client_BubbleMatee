# REST-Schnittstelle

Basis URI: `https://server_{number}/api/v1`

## Als Nutzender möchte ich wissen wer diese Webseite betreibt (Impressum), um den Inhaber erreichen zu können

_1. Impressum-Ressource:_

- _URI:_ `/impressum`
- _Beschreibung:_ Diese Ressource stellt alle relevanten Informationen für das Impressum bereit.

_2. Methode_ - GET

_3. Beispielanfrage:_
http
GET /impressum

_4. Beispielantwort:_

```json
{
    "name": "Ihr Unternehmen",
    "adresse": "Straße, PLZ Ort",
    "kontakt": {
    "email": "info@ihrunternehmen.com",
    "telefon": "+49 123 456789"
    },
    "verantwortlich": "Max Mustermann",
    "rechtsform": "GmbH",
    "weitereAttribute:": [
        {
            "bezeichner": "Mobiltelefon-Kevin",
            "wert": "+49123456789"
        },
        {...}
    ]
}
```

_5. Fehlerbehandlung:_

- _200 - OK_ + impressum.json
- _404 - Not found :_ Falls die Ressource nicht gefunden wird
- _503- Service unavailable:_ Server überlastet oder down

## Als Nutzer möchte ich mich mit Email und Passwort registrieren können, um einen gesicherten Zugang zu meinem Account zu haben und konfigurieren zu können

## Änderungen Jonas + Paul

## Als Nutzender möchte ich mich mit Email und Passwort registrieren können, um einen gesicherten Zugang zu meinem Account zu haben und konfigurieren zu können

_1. Registrierung-Ressource:_

- _URI:_ `/user`
- _Beschreibung:_ Diese Ressource ermöglicht es neuen Benutzern, sich zu registrieren.

_2. Methode_ - POST

_3. Beispielanfrage:_

```json
"payload": {
    "userName": "TestUser",
    "password": "qwerty",
    "preName": "Max",
    "surName": "Mustermann",
    "birthDate": "1999-11-01",
    "mailAddress": "max.mustermaaaan@gmail.com"
}
```

_4. Beispielantwort:_
201 - Created:

```json
{
  "id": "UUID",
  "userName": "TestUser",
  "mailAddress": "max.mustermaaaan@gmail.com"
}
```

_5. Fehlerbehandlung:_

- _201 - Created:_ Benutzer erfolgreich erstellt.
- _400 - Bad Request:_ Fehlende oder ungültige Daten.
- _409 - Conflict:_ Benutzername bereits vorhanden.
- _503- Service unavailable:_ Server überlastet oder down

---

_1. Kontoaktivierung-Ressource:_

- _URI:_ `/user/{id}/activate`
- _Beschreibung:_ Aktiviert das Konto des Benutzers nach der Registrierung.

_2. Methode_ - POST

_3. Beispielanfrage:_

```json
    "payload": {
        "id": "UUID",
        "userName": "TestUser",
        "mailAddress": "max.mustermaaaan@gmail.com",
        "code": "1234"
    }
```

_4. Beispielantwort:_

- _200 - OK:_ Konto erfolgreich aktiviert.

_5. Fehlerbehandlung:_

- _400 - Bad Request:_ Code ungültig
- _404 - Not Found:_ Benutzer-ID nicht gefunden.
- _410 - Gone:_ Code abgelaufen
- _503- Service unavailable:_ Server überlastet oder down

---

_1. Login-Ressource:_

- _URI:_ `/login`
- _Beschreibung:_ Ermöglicht es dem Benutzer, sich mit E-Mail und Passwort anzumelden.

_2. Methode_ - POST

_3. Beispielanfrage:_

```json
    "payload": {
        "userName": "TestUser",
        "password": "qwerty"
    }
```

_4. Beispielantwort:_

- _200 - OK:_ Erfolgreiche Anmeldung.

_5. Fehlerbehandlung:_

- _401 - Unauthorized:_ Ungültige Anmeldeinformationen.
- _403 - Forbidden:_ Account gesperrt
- _404 - Not Found:_ Benutzer nicht gefunden.
- _503- Service unavailable:_ Server überlastet oder down

---

_1. Konto aktualisieren-Ressource:_

- _URI:_ `/user/{id}/update`
- _Beschreibung:_ Ermöglicht dem Benutzer, seine Kontoinformationen zu aktualisieren.

_2. Methode_ - PUT

_3. Beispielanfrage:_

```json
    "payload": {
        "userName": "NewUserName",
        "mailAddress": "new.email@gmail.com"
    }
```

_4. Beispielantwort:_

- _200 - OK:_ Konto erfolgreich aktualisiert.

_5. Fehlerbehandlung:_

- _400 - Bad Request:_ Ungültige Daten.
- _403 - Forbidden:_ Account gesperrt
- _404 - Not Found:_ Benutzer-ID nicht gefunden.
- _503- Service unavailable:_ Server überlastet oder down

POST - Registrierung /user

```json
"payload": {
    "userName": "TestUser",
    "password": "qwerty",
    "preName": "Max",
    "surName": "Mustermann",
    "birthDate": "1999-11-01",
    "mailAddress": "max.mustermaaaan@gmail.com"
}
```

201 - Created:

```json
"body": {
    "id": "UUID",
    "userName": "TestUser",
    "mailAddress": "max.mustermaaaan@gmail.com"
}
```

PUT - Activate Account /user/{id}/activate
POST - Login /login
PUT - Update Account /user/{id}

## Als Nutzer möchte ich Texte posten können, um meine Gedanken zu teilen

POST - Beiträge posten /posts/{userId}

```json
"payload": {
    "hashtags": ["trending", "foryoupage"],
}
```

## Als Nutzer möchte ich die Möglichkeit haben, Hashtags zu verwenden, um meine Beiträge zu kategorisieren und leichter auffindbar zu machen.

GET - Posts erhalten /posts

Query: start, end, sort, filter, hashtag, userid

Beispiel für Hashtags:

GET - Hashtags suchen /posts?hashtag={hashtag}&userId={userId}

## Als Nutzer möchte ich Fotos hochladen können, um ...

POST - Beiträge posten /posts

```json
"payload": {
    "userId" "asdsad"
    "picture": blob/WebP???,
}
```

## Als Nutzer möchte ich Beiträge kategorisiert filtern können, um nach bestimmten Beiträgen zu suchen

haben wir schon

## Als Nutzer möchte ich Posts löschen können, um meine Veröffentlichungen rückgängig zu machen.

DELETE - Beiträge delete /posts/{postId}

## Als Nutzer möchte ich die Möglichkeit haben, andere Nutzer zu suchen und ihre persönlichen Nachrichten-Feeds anzeigen zu können und zu abonnieren

GET - User suchen /user/search/{userName} -> zurück liste an usern
POST - User abonnieren /user/{myUserId}/subscribe
DELETE - User abonnieren /user/{myUserId}/subscribe

```json
"payload": {
    "userid": "otherUser",
}
```

## Als Nutzer möchte ich einen Feed haben, um neue Beiträge meiner Freunde sehen zu können.

GET - /posts/myfeed/{userId}

## Als Nutzer möchte ich die Option haben, Nutzerprofile einzusehen und grundlegende Informationen über sie zu erhalten.

GET /user/{userId}
