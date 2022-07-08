# A. Lerne Listen (Array) kennen

1. Öffne ein Terminal (wenn noch keines offen ist) und tippe:
   `irb`
   das öffnet eine "Interaktiven Ruby Shell", in der Du Ruby direkt ausführen kannst - die Du ja schon kennst.

2. Letztes mal hast Du Zeichenketten kennengelernt. Eine Kette (oder Liste) von einzelnen Zeichen.
   Überlege: Was ist eine Zeichenkette (englisch: Array)?

Antwort: Richtig, eine Liste von beliebigen Dingen wie Zahlen, Zeichen o.ä..

Listen werden in Ruby in eckigen Klammern angegeben, ihre Elemente mit Komma getrennt, also z.B. so:

`liste = [1, 2, 3, 4, 5]`

Tippe das direkt mal in die IRB!

Du kannst jedes Element in der Liste mit seiner Position ("Index") direkt ansprechen. Probier mal aus:

`liste[1]`
oder
`liste[3]`

Wie könntest Du das erste Element der Liste ausgeben?

Du kannst übrigens auch beliebige Elemente von..bis ausgeben, probiere einmal aus:

`liste[1..3]`

Was ist das Ergebnis?

## Methoden von Listen

1. Größe

Auch Listen haben in Ruby spezielle Methoden.
Erinnerst Du Dich noch, wie Du die Größe von Zeichenketten bestimmt hast?
Probiere aus, ob das auch bei Listen geht!

2. Elemente hinzufügen

Du kannst Elemente einfach mit `<<` zu einer Liste hinzufügen.
Probiere es aus:

`liste << 6`

Probiere eigene Zahlen aus!

3. Elemente suche

Du kannst schauen, ob eine Liste Elemente enthält mit include? (englisch für "beinhaltet?")

Probiere aus:

`liste.include?(6)`

Was ist das Ergebnis?
(true = richtig, false = falsch)

Probiere aus, ob Deine Zahlen in der Liste sind?

4. Position ermitteln

Du kannst Dir auch die Position von Elementen in Deiner Liste ausgeben lassen!

`liste.index(3)`

Gib mal die Elemente an Position 2 und 4 aus!

## Weitere Listen

Kann man Listen wohl nur mit Zahlen machen?
Wie könnte eine Liste mit Buchstaben aussehen?
Wie eine mit Wörtern?

Schreibe zwei Beispiele auf!
