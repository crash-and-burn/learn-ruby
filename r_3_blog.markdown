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

## Model, View, Controller (MVC)

Öffne doch mal Deinen neuen Ordner in VSCode. Dann können wir ein wenig programmieren.

Rails basiert auf dem MVC Pattern, d.h.

- es besteht aus Modellen, die Deine Daten & Objekte repräsentieren.
- es besteht aus Views (engl.: Ansichten, Darstellungen) die etwas darstellen können und
- es besteht aus Controllern, d.h. Programmteilen die kontrollieren, was gemacht werden soll (z.B. eine Benutzereingabe wegspeichern).

Was für Bestandteile hat denn ein Blog?
Ein Blog besteht zumeist aus Artikeln (englisch: articles), die jemand in sein Tagebuch bzw seinen Blog schreibt. Also beschäftigen wir uns damit, wie wir Artikel anzeigen und erstellen können.

### Controller

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

Schau doch mal diesen an, was drin steht:
`app/controllers/articles_controller.rb`

Was für eine Methode wurde eingefügt?

### Views

Wenn Du die Ausgabe ändern möchtest, erstelle folgende Datei:

`app/views/articles/index.html.erb`

Füge mal folgende Zeile ein:

```
<h1>Hallo mein Freund!</h1>
```

Jetzt rufe mal `http://localhost:3000/articles` im Browser auf.
Was siehst Du?

Schreibe weitere Zeilen Text da runter, z.B. mit:

```
<p>Das ist weiterer Text...</p>
```

Wie sieht das aus?

Schreibe weitere Sätze, die Dir einfallen.

Diese Buchstaben zwischen den spitzen Klammern <> nennt man Tags.
Tags sind Bestandteil der Seitenbeschreibungssprache [HTML (HyperText Markup Language)](https://de.wikipedia.org/wiki/Hypertext_Markup_Language). Sie definieren zusammen eine Seite, die ein Browser anzeigen kann.

Probiere mal folgende Tags aus, in dem Du Sie um einzelne Wörter oder Buchstaben gruppierst:

```
<b></b>
<i></i>
<em></em>
<h2></h2>
<h3></h3>
```

Was passiert jeweils?

Schreibe mal eine HTML Seite, die zwei Überschriften und drei Absätze mit Text enthält. Den Inhalt kannst Du Dir ansonsten frei ausdenken.

### Model

Ein Model ist eine Ruby-Klasse, die zur Darstellung von Daten verwendet wird. Darüber hinaus können Modelle in Rails mit der Datenbank kommunizieren.

Rails bietet wieder ein Tool, mit dem Du ein Model und seine Attribute generieren kannst.
Attribute können verschiedene Eigenschaften darstellen, also für einen Artikel z.B. der Titel (engl.: title) oder der Inhalt (engl.: body), die verschiedene Typen sein können. Der Titel zB könnte eine einfache Zeichenkette (String) sein, während der Inhalt ein langer Text sein kann. Generiere doch mal so ein Model für Artikel:

```
bin/rails generate model Article title:string body:text
```

Schau Dir den Befehl noch einmal an. Was macht er? Wie heissen die Attribute?
Wie würde der Befehl lauten, wenn Du zusätzlich zu Titel und Inhalt noch einen Autor (engl.: author) bzw seinen Namen mit angeben wollen würdest? Welchen Datentyp würdest Du dafür nehmen?

Wie Du bei der ausführung vielleicht gesehen hast, wurde direkt auch eine Migration (d.h. eine Änderungsanweisung) für die Datenbank angelegt. Für die einmal aus:

```
bin/rails db:migrate
```

Prima! Jetzt kennt die Datenbank auch das Schema Deines Models, und Rails kann das Model in die Datenbank schreiben.

Was kann man nun mit diesen Models anfangen bzw wie kann man die in die Datenbank wegspeichern?

Öffne mal eine Konsole (ähnlich wie bei Ruby) mit folgendem Befehl:

```
bin/rails console
```

Hier kannst Du Ruby ausführen, aber auch die ganzen Ergänzungen von Rails.
So kannst Du z.B. einen neuen Artikel (engl.: new article) anlegen. Gib mal ein:

```
article = Article.new(title: "Mein erster Artikel", body: "Ich bin ein Artikel... Toll!")
```

Was war noch mal article in diesem Fall bzw wie nennt man das?
Was steht in article?

Speichere (engl.: save) mal den Artikel:

```
article.save
```

Du kannst auf gespeicherte Models in der Datenbank z.B. so darauf zugreifen:

```
Article.find(1)
```

wobei die Zahl die Position bzw. den Index meint
oder

```
Article.first
```

Was könnt das machen?

Oder gib mal alle Artikel aus mit:

```
Article.all
```

Jetzt lege doch mal einen weiteren Artikel an mit Text den Du Dir ausdenkst und speichere in ab.
Was gibt `Article.all` jetzt aus?

### Eine Liste von Artikeln ausgeben

Um alle Artikel in unserer Anwendung auszugeben, müssen wir zwei Dinge tun.

1. den Controller ändern, daß er alle Artikel einliest und bereitstellt (der Controller kontrolliert ja, was unsere Anwendung machen soll), und
2. Die View so ändern, daß auch alle Artikel ausgegeben werden.

Öffne mal den Controller in VSCode: `app/controllers/articles_controller.rb` so daß Du ihn ändern kannst.

Füge mal die Zeile in die Methode index ein:
`@articles = Article.all`
Wie eben in der Konsole werden damit alle Artikel in die globale Variable @articles eingelesen und zur Verfügung gestellt.

Das sollte dann insgesamt so aussehen:

```
class ArticlesController < ApplicationController
  def index
    @articles = Article.all
  end
end
```

Jetzt fehlt nur noch die View. Öffne mal `app/views/articles/index.html.erb` in VSCode.
Und füge folgende Zeilen nach dem </h1> ein:

```
<ul>
  <% @articles.each do |article| %>
    <li>
      <%= article.title %>
    </li>
  <% end %>
</ul>
```

Erinnerst Du Dich noch an [Schleifen in Ruby](6_schleifen.markdown) und insbesondere die Schleife `each`? Sonst schau noch mal schnell rein.

Was macht wohl diese Schleife hier?
Kannst Du das beschreiben?

Schaue Dir das Ergebnis mal an:

```
http://localhost:3000/articles/
```
