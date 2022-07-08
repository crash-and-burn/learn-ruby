# A. Was sind Schleifen und Iteratoren?

Manchmal macht es Sinn, Code mehrfach auszuführen. Dazu bieten sich oft Schleifen an, die Code so lange ausführen, bis eine Bedingung eingetreten ist oder ein Zähler (Iterator) bis zur gewünschten Höhe hoch- oder runtergezählt wurde.

## times Schleife

Mit times (englisch für "mal") kannst Du einfach angeben, wie oft etwas ausgeführt werden soll.

Wie geht das in Ruby?

1. Öffne am besten direkt mal ein Terminal (wenn noch keines offen ist) und  
   tippe: `irb` das kennst Du ja.

Jetzt kannst Du z.B. fünf Mal etwas ausgeben:

`5.times { puts "Hallo!" }`

Schreibe doch mal ein kleines Programm, das 10 Mal etwas ausgibt!

## for Schleife

Manchmal willst Du genau angeben, von wann bis wann etwas ausgeführt wird. Das macht man mit einer for Schleife, in der man Start und Ende angeben kann:

Ein Beispiel:

```
for i in 1..10
  next if i % 2 == 0
  puts i
end
```

Was macht das Programm?

Schreibe doch mal ein Programm, das alle Zahlen von 11 bis 19 ausgibt.

## while und until

Es gibt noch andere Schleifentype, etwa `while` oder `until`.

```
i = 0
while i < 10
  puts i
end
```

Was macht das Programm?

## each

Eine schöne Schleife ist `each`, damit kann man einfach für jedes Element einer Liste bzw eines Arrays etwas ausführen.

Schreibe doch mal ein paar Vornamen Deiner Freunde in ein Array `freunde`.
Tipp: -> Wenn Du nicht mehr weist, wie man Arrays macht, schaue im Kapitel über Arrays nach!

Tippe doch mal folgendes ein:

```
freunde.each do |freund|
  puts freund
end
```

Was macht das Programm?
