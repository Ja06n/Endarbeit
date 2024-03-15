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
  3. def golden_ratio_convergence_chart(iterations):
    # Generiere die Fibonacci-Folge bis zur n-ten Iteration
    fib_sequence = fibonacci(iterations)
    # Berechne die Verhältnisse zwischen aufeinanderfolgenden Fibonacci-Zahlen
    # Verhindere Division durch Null mit einer Bedingung für den Fall fib_sequence[i] == 0
    ratios = [fib_sequence[i + 1] / fib_sequence[i] if fib_sequence[i] != 0 else 0 for i in range(iterations - 1)]
    # Berechne das goldene Verhältnis
    golden_ratio = (1 + np.sqrt(5)) / 2
    # Setze die Größe des Diagramms
    plt.figure(figsize=(10, 6))
    # Plotte die Fibonacci-Verhältnisse
    plt.plot(ratios, marker='o', label='Fibonacci-Verhältnisse')
    # Zeichne eine gestrichelte Linie für das goldene Verhältnis
    plt.axhline(y=golden_ratio, color='r', linestyle='--', label='Goldene Verhältnis')
    # Setze Diagramm-Titel und Achsenbeschriftungen
    plt.title('Konvergenz der Fibonacci-Verhältnisse gegen das Goldene Verhältnis')
    plt.xlabel('Iterationen')
    plt.ylabel('Fibonacci-Verhältnis')
    # Zeige eine Legende an
    plt.legend()
    # Aktiviere das Gitter im Diagramm
    plt.grid(True)
    # Zeige das Diagramm an
    plt.show()

  
  
