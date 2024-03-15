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
  3. Hier wird die Graphik definiert und später, wenn der Benutzer die gewünschte Anzehl an Iterationen eingegeben hat, ausgeführt. Wie gesagt, kann der Benutzer selbst entscheiden, wie viele Iterationen oder Wiederholungen gewünscht sind. Das sieht dann folgendermaßen aus: ![grafik](https://github.com/Ja06n/Endarbeit/assets/137494390/454712bf-8fb4-45c1-9073-e7bb4727d3fd)

  4. Wenn das geschehen ist, wird der Code ausgeführt und die Graphik wird angezeigt. Hier wir wieder das Beispiel mit der fünften und sechsten Fibonacci-Zahl gezeigt.
  5. ![grafik](https://github.com/Ja06n/Endarbeit/assets/137494390/aa279a2c-3583-473b-8141-854c43b67d37)


  
  
