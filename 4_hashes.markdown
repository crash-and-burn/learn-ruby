# A. Was sind Hashes?

Was ist ein Hash? Ein Hash ist wie ein Wörterbuch.

Es hilft Dir, zwei Werte miteinander zu verbinden.

Wie etwa eine Bewertung zu einem Essen oder eine Telefonnummer zu einem Personennamen.

Wie geht da in Ruby?

1. Öffne am besten direkt mal ein Terminal (wenn noch keines offen ist) und  
   tippe: `irb` das kennst Du ja.

Erstelle Dir doch einfach mal ein Hash mit Telefon-Nummern!

`telefonnummern = { "Noa" => "0176-123456" }`

Wie kannst Du jetzt die Telefonnummer von Noa aufrufen?
Ganz ähnlich wie bei Listen/Arrays mit []:

`telefonnummern["Noa"]`

Klappt das? Dann weise Dir doch eine andere Nummer zu. Das geht so:

`telefonnummern["Noa"] = "02104-9876545"`

Das ist einfach, oder?

Dann setze doch mal mehr Telefonnummern in die Liste:

`telefonnummern = { "Noa" => "0176-123456", "Anna" => "0176-554444", "Tom" => "0176-3333333" }`

Gib doch mal die Telefonnummer von Anna aus. Und weise Tom eine neue Nummer zu!

Hashes bestehen immer aus Paaren, dem Schlüssel (englisch: "Key") und dem Wert (englisch: "Value"). In unserem Beispiel ist ein Schlüssel "Noa" und der dazugehörige Wert "0176-123456".

Natürlich kannst Du auch etwas anderes als Zeichenketten als Schlüssel oder Wert benutzen. Was meinst Du, könnte das (alles) sein? Probiere es aus!

## Methoden von Hashses

Auch Hashes haben natürlich Methoden in Ruby.

Z.B. kannst Du Dir wie bei Arrays und Zeichenketten die Größe ausgeben lassen mit size!

Oder Du kannst alle Werte direkt ausgeben. Im Beispiel z.B. alle Telefonnummern mit values (englisch für Werte). Tippe:

`telefonnummern.values`

Oder Du kannst mehrere Telefonnummern auf einmal ausgeben mit `values_at`:

`telefonnummern.values_at("Anna", "Tom")`

Oder Du kannst überprüfen, ob ein Schlüssel einen Werte hat. Ob also ein Namen, eine Telefonnumer hat:

`telefonnummern.has_key?("Noa")`
`telefonnummern.has_key?("Leo")`

Oder überprüfen, ob eine Telefonnumer vorkommt, sprich ob ein Werte (engl.: value) vorkommt:

`telefonnummern.value?("0211-654321")`

Einen neuen Eintrag erstellen kannst Du, in dem Du einem neuen Schlüssel einen Wert hinzufügst:

`telefonnummern["Bernd"] = "123123"`

ÜBerprüfe die neue Liste, in Du telefonnumern ausgibst.

Du willst einen Eintrag löschen? Kein Problem:

`telefonnummern.delete("Bernd")`
