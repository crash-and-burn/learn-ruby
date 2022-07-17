# Programmieren wir einen Blog!

Fange ein neues Rails Projekt an. Wie wäre es mit einem Blog?

```
rails new blog
```

Du siehst, Rails kopiert alle nötigen Dateien in das neue Projektverzeichnis.
Gehe mal dort hinein mit

```
cd blog
```

Und starte mal den Rails Server, um zu testen, ob Dein neues Programm schon was anzeigt.

```
bin/rails server
```

Start einen Browser (Chrome?) und öffne folgenden Link:

```
http://localhost:3000
```

Was siehst Du?

### Model, View, Controller (MVC)

Öffne doch mal Deinen neuen Ordner in VSCode. Dann können wir ein wenig programmieren.

Rails basiert auf dem MVC Pattern, d.h.

- es besteht aus Modellen, die Deine Daten & Objekte repräsentieren.
- es besteht aus Views (engl.: Ansichten, Darstellungen) die etwas darstellen können und
- es besteht aus Controllern, d.h. Programmteilen die kontrollieren, was gemacht werden soll (z.B. eine Benutzereingabe wegspeichern).

Starten wir mal mit einem Controller.

Ändere erst mal die Datei `config/routes.rb`, die gibt an, was ausgeführt wird, wenn der Browser bestimmt Routen (d.h. Adressen) aufruft.

Kopiere doch mal die folgenden Zeile rein:

```
Rails.application.routes.draw do
  get "/articles", to: "articles#index"
end
```

D.h. wenn Du

```
http://localhost:3000/articles/
```

in Deinem Browser aufrufst, wird die Aktion Index im Controller Action ausgeführt.

Diesen sollten wir jetzt mal programmieren. Rails bietet eine Reihe von Hilfsmöglichkeiten & Tools an, die Dir dabei helfen können. Gib mal in ein Terminal ein:

```
bin/rails generate controller Articles index --skip-routes
```

Du siehst, unter anderem wird ein Controller für Artikel erzeugt.
