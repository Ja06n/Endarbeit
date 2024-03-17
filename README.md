# Der Einfluss der Fibonacci-Folge und des goldenen Schnitts auf die modern Architektur 
Der Fokus dieser Arbeit liegt auf der Fibonacci-Folge und dem goldenen Schnitt und ihrem Einfluss auf die moderne Architektur. Es wird zuerst einen kleinen Einblick in das Leben des berühmten Leonardo da Pisa, besser bekannt als Fibonacci, geben. Außerdem werden die verschiedenen Anwendungsgebiete der Fibonacci-Folge, der Zusammenhang zwischen der Fibonacci-Folge und dem goldenen Schnitt, auch anhand verschiedener Beispiele dargestellt. In einem weiteren Abschnitt wird die Architektur, sowohl moderne als auch antike Architektur aus dem antiken Griechenland, und der Zusammenhang zur Fibonacci-Folge und dem goldenen Schnitt bearbeitet.
Der praktische Teil umfasst mehrere Python Programme die in Jupyter Notebook erstellt wurden. Das Haupt-Programm wird mithilfe verschiedener Bibliotheken ein Bild laden, erkennen und anschließend auswerten. Beim Starten des Programms, erscheint sich ein Dateiauswahldialog. Damit selektiert man eine Bilddatei (Dateitypen jpg., jpeg., png. und bmp.), welche dann auch angezeigt wird. Mit der Maus können dann zwei beliebige Strecken eingezeichnet werden. Das Programm berechnet daraufhin die Länge der Strecken und auch deren Verhältnis zueinander. Liegt das Verhältnis nah am goldenen Schnitt, also mit einem Verhältnis von ca. 1,62 wird das Verhältnis in grün dargestellt ansonsten in gelb.
In diesem Git-Hub Repository kann man alle Codeteile dieses praktischen Teils, die man auch in der Arbeit findet, an einem Ort finden. Außerdem wird in dieser Readme-Datei eine kleine Vorführung jedes einzelnen Codes gemacht. Für den Hauptcode ist eine Bildschirmaufnahme erstellt worden für die anderen Codes wird es Screenshots geben, die jeden einzelnen Schritt so ausführlich wie möglich erklärt.

  # Konvergenz mit Fibonacci
  In diesem Programm wird die Konvergenz, also die Annäherung, wenn man bei jeweils zwei aufeinanderfolgenden Fibonacci-Zahlen die große durch die kleine teilt. Ein Beispiel: Nehmer wir die fünfte Fibonacci-    Zahl (5) und die sechste Fibonacci Zahl (8) und teilen nun 8 durch 5 (= 1,6). Führen wir das Programm mal aus und die einzelnen Schritte des Programms werden nähergebracht.
  
  1. import matplotlib.pyplot as plt
     import numpy as np
     Diese beiden Teile des Codes dienen dazu, die beiden für den Code essentiellen Bibliotheken zu laden, ohne die das Programm einfach Sinnlos wäre.
  2. def fibonacci(n):
    fib_sequence = [0, 1]
    for i in range(2, n):
        fib_sequence.append(fib_sequence[-1] + fib_sequence[-2])
     return fib_sequence
     In diesem Teil des Codes wird die Fibonacci-Folge definiert, also wird er genutzt um im späteren Verlauf des Codes die Fibonacci-Zahlen zu berechnen.
  3. Hier wird die Graphik definiert und später, wenn der Benutzer die gewünschte Anzehl an Iterationen eingegeben hat, ausgeführt. Wie gesagt, kann der Benutzer selbst entscheiden, wie viele Iterationen oder Wiederholungen gewünscht sind. Das sieht dann folgendermaßen aus:
![grafik](https://github.com/Ja06n/Endarbeit/assets/137494390/454712bf-8fb4-45c1-9073-e7bb4727d3fd)

  5. Wenn das geschehen ist, wird der Code ausgeführt und die Graphik wird angezeigt. Hier wird wieder das Beispiel mit der fünften und sechsten Fibonacci-Zahl gezeigt.
  ![grafik](https://github.com/Ja06n/Endarbeit/assets/137494390/aa279a2c-3583-473b-8141-854c43b67d37)


  # Rekursive Formel und Binet-Formel Anwendung
  Diese beiden Programme machen im gro´ßen und ganzen das selbe, sie generieren die Fibonacci-Folge bis zu einem gewissen Grad. Das entscheidet der Benutzer, indem er wieder in das, sich beim Start des Programms öffnende Fenster, die gewünschte Anzahl an Iterationen eingibt. 
  ## Die Rekursive Formel
  1. Zuerst wird mit folgendem Befehl die Rekursive Formel definiert und mit einem if, else Befehl wird die berechnung der Fibonacci-Zahlen deutlicher:
     def fibonacci_recursive(n):
    if n <= 1: 
        return n (Basisfall, wenn n kleiner/gleich 1 ist, wird einfach n zurückgegeben)
    else:
        return fibonacci_recursive(n-1) + fibonacci_recursive(n-2) (Ansonsten werden die beiden vorherigen Fibonacci-Zahlen miteinander summiert)
  2. Im nächsten Schritt wird zuerst die Benutzereingabe definiert und auch Sonderfälle angegeben.
  3. Dann wird das Programm ausgeführt, nur wenn man auch eine gültige Zahl eingegeben hat! (Zahl muss eine ganze sein)
  4. Mit der letzten Zeile wird kontrolliert ob das Programm direkt ausgeführt wird und nicht über andere Seiten, whatever importiert wird: if_name_=="_main_":

  ## Die Binet Formel
  1. Als aller erstes wird die Bibliothek math aufgerufen, um die ganzen Berechnungen zu machen.
  2. Dann wird die Formel definiert mit folgendem Befehl: (ist zuständig  für die Berechnung der Fibonacci-Zahl)
     def binet_formula(n):
    phi = (1 + math.sqrt(5)) / 2
    psi = (1 - math.sqrt(5)) / 2
    fib_n = int((math.pow(phi, n) - math.pow(psi, n)) / math.sqrt(5))
    fib_n_minus_1 = int((math.pow(phi, n - 1) - math.pow(psi, n - 1)) / math.sqrt(5))
    return fib_n / fib_n_minus_1
  3. Im dritten Schritt wird die Hauptfunktion definiert.
     def main():
    try:
        position = int(input("Geben Sie die Position in der Fibonacci-Folge ein: ")) (Funktion für die Benutzereingabe)
        if position < 0:
            print("Bitte geben Sie eine nicht-negative Position ein.")
        elif position == 0:
            print("Der Wert an Position 0 ist 0.")
        else:
            result_ratio = binet_formula(position)
            print(f"Das Verhältnis von Fibonacci-Zahl an Position {position} zu Position {position - 1} ist: {result_ratio:.10f}")
    except ValueError:
        print("Ungültige Eingabe. Bitte geben Sie eine ganze Zahl ein.")

  4. Zum Schluss folgt dann wieder folgender Befehl: if_name_=="_main_":

# Fibonacci-Spirale zeichnen
Dieses Programm zeichnet die Fibonacci-Spirale, als erstes werden Quadrate gezeichnet, die in iherer Seitenlänge der Fibonacci-Folge entsprechen und dann wird die Spirale (jeweils ein Viertelkreis pro Quadrat) in die Quadrate gezeichnet. Es wird wierderum nach der Anzahl Iterationen gefragt und das Programm wird ausgeführt.

1. Als aller erstes werden, wie bei jedem Programm, die verschiedenen Bibliotheken geladen. In diesem Fall sind das die turtle-Bibliothek für die Grafik und die math-Bibliothek für die Berechnung der Radien und der Seitenlängen der Quadrate. (import turtle und import math)
2. wn = turtle.Screen()  
wn.setup(1000, 800)  -> Fenstergröße
myTurtle = turtle.Turtle()  
myTurtle.pensize(3)   -> Stiftgröße
AnzQuadrate = int(input("Geben Sie die Anzahl der Iterationen ein: ")) -> Anzahl Wiederholungen
Diese Codezeilen dienen dazu ein Fenster zu erstellen, wo dann später die Spirale gezeichnet wird, es wird die Größe des Fensters angegeben (1000 mal 800 Pixel), die Stiftgröße und es wird wieder nach der Anzahl der Wiederholungen gefragt.

3. def main(quadrate):
    valueOne = 0
    valueTwo = 1
    fib = 1
    for i in range(quadrate):
        myTurtle.right(90) 
        drawSq(fib * 20)   
        fib = valueOne + valueTwo
        valueOne = valueTwo
        valueTwo = fib
   Man definiert die Hauptfunktion, die zur Berechnung der Fibonacci-Zahlen zum zeichnen der Seitenlängen der Quadrate dient.

4. def drawSq(seitenlaenge): 
    for n in range(6): -> Die 6 dient dazu, dass der Cursor wieder an der richtigen Stelle zu zeichnen anfängt. Der Cursor fährt sozusagen 6 Linien.
        myTurtle.forward(seitenlaenge)  Bewege die Turtle vorwärts um die Seitenlänge
        myTurtle.left(90)   Drehe die Turtle um 90 Grad nach links
   Man definiert die Funktion um die Quadrate zu zeichnen, die bereits in der vorherigen Funktion berechnet wurden.

5. def sprial(quadrate):
    myTurtle.color("red")  # Setze die Stiftfarbe auf Rot
    myTurtle.speed(10)      # Setze die Zeichengeschwindigkeit auf 2 (mittlere Geschwindigkeit)
    angle = 90
    valueOne = 0
    valueTwo = 1
    fib = 1
    myTurtle.right(90 + (quadrate % 4) * 90)     
    myTurtle.penup() 
    myTurtle.setpos(0, 0)  
    myTurtle.pendown()    
    for i in range(quadrate): -> Das hier ist eine Schleife, die bewirkt, dass man egal welche Zahl angeben kann und die Spirale trotzdem nach den Funktionen und Definitionen gezeichnet werden kann.
        arc(fib * 20, angle)  -> Berechnet die Winkel zum zeichnen der Spirale.
        fib = valueOne + valueTwo
        valueOne = valueTwo
        valueTwo = fib

    Man definiert die Spirale, also wie sie gezeichnet wird.

6. def arcLine(n, laenge, winkel): 
    for i in range(n): 
        myTurtle.forward(laenge) 
        myTurtle.left(winkel) 
def arc(r, winkel): 
    bogenlaenge = 2 * math.pi * r * abs(winkel) / 360   -> Dient zur berechnung der Bogenlänge
    n = int(bogenlaenge / 4) + 1  
    schrittlaenge = bogenlaenge / n 
    schritt_winkel = float(winkel) / n 
    myTurtle.left(schritt_winkel / 2) 
    arcLine(n, schrittlaenge, schritt_winkel) 
    myTurtle.right(schritt_winkel / 2) 

   Diese beiden Definitionen sind dafür zuständig die Spirale zu zeichnen beziehungsweise den Bogen.

### Die Hauptprogrammschleife
7. main(AnzQuadrate) -> Rufe die Hauptfunktion auf, um die Fibonacci-Quadrate zu zeichnen
sprial(AnzQuadrate) -> Rufe die Funktion auf, um die rote Spirale zu zeichnen
wn.exitonclick() -> Schließe das Turtle-Fenster, wenn es angeklickt wird

Hier ein Beispiel mit der Zahl 6:


