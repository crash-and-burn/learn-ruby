# A. Was sind Ablauf-Kontrollen?

Um den Ablauf Deines Programmes zu Kontrollieren, kannst Du mit Ausdrücken arbeiten, die z.B. Zustand von Variablen abfragen.

## IF Anweisung

Eine if-Anweisung in Ruby wertet einen Ausdruck aus, der entweder wahr oder falsch zurückgibt. Wenn der Ausdruck wahr ist, führt Ruby den Codeblock aus, der auf if folgt, während Ruby nil zurückgibt, wenn der Ausdruck falsch ist.

Wie geht da in Ruby?

1. Öffne am besten direkt mal ein Terminal (wenn noch keines offen ist) und  
   tippe: `irb` das kennst Du ja.

Schreibe mal Dein Alter in eine Variable, z.B. so:

`alter = 10`

Wie kannst Du jetzt Eine IF-Anweisung einfügen, die das Alter abfragt? In etwa so:

```
if alter == 10
  puts "Du bist zehn Jahre alt!"
end
```

Klappt das? Dann setze doch mal das alter auf 11 und schaue, was passiert:

```
alter = 11
if alter == 10
  puts "Du bist zehn Jahre alt!"
end
```

## ELSE Anweisung

Du kannst natürlich auch mit ELSE Alternativen zu Deiner IF Anweisung ausführen:

```
if alter == 10
  puts "Du bist zehn Jahre alt!"
else
  puts "Du bist nicht zehn Jahre alt."
end
```

Was wird ausgegeben?
Was passiert, wenn Du alter wieder auf 10 setzt?

## Kombinationen mit AND und OR

Du kannst Ausdrücke auch kombinieren: Mit && (UND) oder || (ODER) kannst Du gleich mehrere Ausdrücke kombinieren.

Was fragt z.B.
`if alter == 10 || alter == 11` ?

Schreibe ein Programm, das das Alter ausgibt, wenn das Alter kleiner (`<`) als 10 oder größer (`>`) als 20 ist.
