# A. Lerne Zeichenketten kennen: Strings

1. Öffne ein Terminal (wenn noch keines offen ist) und tippe:
   `irb`
   das öffnet eine "Interaktiven Ruby Shell", in der Du Ruby direkt ausführen kannst - die Du ja schon kennst.

2. Überlege: Was ist ein String (englisch für "Zeichenkette")?

Antwort: Richtig, eine Kette von Zeichen, eine Liste von Zeichen.

Zeichenketten werden in Ruby in Anführungszeichen angegeben, also z.B. so:

`"Marmelade"`

Tippe das direkt mal in die IRB!

3. Überlege: Was ist der Unterschied zwischen Zeichenketten und Variablen?

Anwort: Zeichenketten sind Daten und Variablen sind Platzhalter bzw. Namen für Daten.

In den letzten Beispielen hatte wir als Daten immer Zahlen den Variablen zugwiesen, um damit z.B. das Alter auszurechnen oder Summen zu bilden. Aber: Überraschung! Du kannst auch Zeichenketten in Variablen schreiben!

Z.B. so (schreib das direkt mal in die IRB):

`brotbelag = "Marmelade"`

Was ist in brotbelag jetzt drin? Tippe brotbelag und überzeuge Dich davon!

# B. Lerne Methoden kennen

1. Was kann man mit Zeichenketten alles machen?

Es gibt viele Dinge, die Du mit Zeichenketten alles machen kannst!

Z.B. die Größe rausfinden (direkt in die IRB tippen!):

`"Marmelade".size`

(size ist englisch und heisst Größe)

Oder Du kannst die Zeichenketten in Grossbuchstaben ausgeben (In IRB tippen!):

`"Marmelade".upcase`

Wir nennen so etwas Methoden! Und in Ruby gibt es viele fertig für Zeichenketten davon.

2. Methoden anwenden

Führe die folgenden Methoden direkt in IRB aus und schreibe das Ergebnis auf!
Schreibe auch auf, was die Methode jeweils macht!

`"Marmelade".gsub("Marme", "Papa")`

`"Marmelade".chars`

(Tipp für die nächsten: True ist englisch für "richtig / wahr" und False ist englisch für "falsch")

`"Marmelade".include?("mel")`
`"Marmelade".include?("xyz")`

`"Marmelade".start_with? "Mar"`
`"Marmelade".end_with? "lade"`

Wenn Du mal einen String ausgeben möchtest, tippe:
`puts "Marmelade"`

Erinnerst Du Dich noch an die Variable brotbelag?
Gebe die doch einmal aus!

Kannst Du die anderen Methoden, die Du eben auf die Zeichnkette direkt angewendet hast, auch auf brotbelag anwenden? Wie sähe das aus?

Tippe einige Beispiele in irb!

3. Dinge verbinden

Kleine Wiederholung:
Wir haben bei Zahlen gelernt, daß man sie addieren bzw zusammenrechnen kann, tippe z.B.:

`2 + 3`

Was kommt raus?

Wir konnten auch Variablen zusammenrechnen, tippe z.B.:

`a = 3`

`b = 5`

`a + b`

Was kommt raus?

Meinst Du, man kann auch Zeichenketten "zusammenrechnen"?

Was passiert, wenn Du z.B. das folgende eintippst:

`"Brot" + "Aufstrich"`

Man kann übrigens auch Variablen anderen zuweisen - und die gleich auch mit Zeichenketten kombinieren!
Probiere das folgende gleich mal in der IRB aus:

`essen = "Brot mit " + brotbelag`

Was kommt raus als Essen?
Gib es aus!
