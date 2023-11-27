# REST-Schnittstelle


Basis URI: `https://server_{number}/api/v1`

## Als Nutzender möchte ich wissen wer diese Webseite betreibt (Impressum), um den Inhaber erreichen zu können

*1. Impressum-Ressource:*
   - *URI:* `/impressum`
   - *Beschreibung:* Diese Ressource stellt alle relevanten Informationen für das Impressum bereit.

*2. Methode*
    - GET

*3. Beispielanfrage:*
http
GET /impressum

*4. Beispielantwort:*
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

*5. Fehlerbehandlung:*
- *200 - OK* + impressum.json
- *404 - Not found :* Falls die Ressource nicht gefunden wird
- *503- Service unavailable:* Server überlastet oder down 

## Als Nutzer möchte ich mich mit Email und Passwort registrieren können, um einen gesicherten Zugang zu meinem Account zu haben und konfigurieren zu können




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

POST - Beiträge posten /{userId}/posts
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
POST - Beiträge posten /{userId}/posts
```json
"payload": {
    "picture": blob/WebP???,
}
```

## Als Nutzer möchte ich Beiträge kategorisiert filtern können, um nach bestimmten Beiträgen zu suchen

haben wir schon

## Als Nutzer möchte ich Posts löschen können, um meine Veröffentlichungen rückgängig zu machen.

DELETE - Beiträge delete /{userId}/posts/{postId}


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

GET - /posts/user/{myUserID}/myfeed

## Als Nutzer möchte ich die Option haben, Nutzerprofile einzusehen und grundlegende Informationen über sie zu erhalten.

GET /user/{userId}
