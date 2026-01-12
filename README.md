# Entwurfsmuster

Chain of Responsibility

Beispiel:
Ein Support-System, das Anfragen je nach Schwierigkeitsgrad bearbeitet:

Level 1 → einfacher Support
Level 2 → technischer Support
Level 3 → Experte

Zentrale Charakteristika des Musters:
Mehrere Objekte können eine Anfrage bearbeiten
Die Anfrage wird entlang einer Kette weitergereicht
Jeder Handler entscheidet selbst:
bearbeiten oder an den nächsten weiterleiten
Der Absender kennt nicht den konkreten Empfänger
Lose Kopplung zwischen Sender und Empfängern

TemplateMethod

Beispiel:
Wir machen Getränke: Kaffee und Tee. Der Ablauf ist immer gleich, nur einzelne Schritte variieren.

Einzelne Schritte des Ablaufs werden:
fix vorgegeben oder von Unterklassen überschrieben
Die Reihenfolge der Schritte bleibt immer gleich
Verwendet Vererbung
Kontrolliert den Ablauf über eine Template-Methode

Decorator

Beispiel:
Wir wollen Getränke mit optionalen Extras zubereiten (z. B. Milch, Zucker), ohne die Grundklasse zu ändern.
Der Decorator erweitert das Verhalten dynamisch.

Erkennt man sofort:
Grundklasse bleibt unverändert (Kaffee)
Verhalten wird dynamisch zur Laufzeit durch Decorators erweitert
Mehrere Decorators können gestapelt werden

Builder
Beispiel
Wir wollen ein Objekt mit vielen optionalen Parametern erstellen (z. B. ein Sandwich oder Auto), ohne einen riesigen Konstruktor mit vielen Parametern zu schreiben.
Erkennt man sofort:
Komplexe Objekte werden Schritt für Schritt aufgebaut
Optionales Setzen von Parametern möglich
Vermeidet riesige Konstruktoren
Method Chaining macht Code sauber und lesbar
Sandwich [Brot=Weizenbrot, Belag=Schinken, Ketchup=true, Mayo=false]
public static class Builder {
        private String brot;
        private String belag;
        private boolean ketchup;
        private boolean mayo;
}
Sandwich sandwich = new Sandwich.Builder("Weizenbrot")
    .belag("Schinken")
    .ketchup(true)
    .mayo(false)
    .build();

Adapter

Beispiel
Wir haben eine alte Schnittstelle, die wir nicht ändern können, und wollen sie in ein neues System einfügen, das eine andere Schnittstelle erwartet.

Adapter übersetzt eine Schnittstelle in eine andere
Alte Klasse wird wiederverwendet, ohne sie zu ändern
Neues System arbeitet einheitlich mit der neuen Schnittstelle


Observer:

Beispiel: Wir wollen, dass mehrere Objekte (Observer) automatisch benachrichtigt werden, wenn sich der Status eines anderen Objekts (Subject) ändert – z. B. Wetterstation und Anzeigen.
