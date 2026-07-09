# Aufgabe 08: Graustufen und Bildanalyse

Dieses Repository enthält den Code und die Ergebnisse für die Belegaufgabe **„Aufgabe 08: Graustufen und Bildanalyse“** im Kurs **Programmierkonzepte und Algorithmen** (HTW Berlin,  Semester 2026).

Aufgaben des Projekts sind:

- a. Laden Sie ein RGB-Bild und wandeln Sie es in ein Graustufenbild um.
- b. Passen Sie anschließend Helligkeit und Kontrast des Bildes an.
- c. Berechnen Sie zum Schluss das Histogramm der Grauwerte und stellen Sie es geeignet dar
- (d. Laufzeit und Speedup verlgleichen)

Die Aufgaben werden auf 2 Laptops mit unterschiedlichen Specs ausgeführt:

| Laptop | Prozessor | GPU |
| ------ | --------- | --- |
| 1 | Intel(R) Core(TM) Ultra 7 258V, 2200 MHz, 8 Kerne, 8 logische Prozessoren | Intel(R) Arc(TM) 140V GPU, 16 GB |
| 2 | Intel(R) Core(TM) i7-10870H CPU @ 2.20 GHz, 8 Kerne, 16 logische Prozessoren | NVIDIA GeForce RTX 3050 Laptop GPU, 4 GB |

Es werden 3 Varianten verglichen werden:


| Variante | Name                 | Aufgabe                                   |
| -------- | ----------------------- | ------------------------------------------- |
| 1        | Baseline / CPU      |  ohne Parallelisierung       |
| 2        | OpenCV/ CPU |  optimierte Bibliothek für Bildverarbeitung |
| 3        | PyOpenCL / GPU |  mit Parallelisierung             |

## Ergebnisse:

a. + b.

<table width="100%">
  <tr>
    <td width="30%"><img src="images_input/1.nature_small.jpeg" width="100%"></td>
    <td align="center" width="5%">></td>
    <td width="30%"><img src="images_output/8a.png" width="100%"></td>
    <td align="center" width="5%">></td>
    <td width="30%"><img src="images_output/8b.png" width="100%"></td>
  </tr>
  <tr>
    <td align="center">Originalbild</td>
    <td></td>
    <td align="center">8a: Graustufenbild</td>
    <td></td>
    <td align="center">8b: Helligkeit/Kontrast erhöht</td>
  </tr>
</table>

c.

<table width="100%">
  <tr>
    <td width="50%"><img src="images_output/1.nature_small.png" width="100%"></td>
    <td width="50%"><img src="images_output/2.nature_medium.png" width="100%"></td>
  </tr>
  <tr>
    <td align="center">640×415</td>
    <td align="center">1024×663</td>
  </tr>
  <tr>
    <td width="50%"><img src="images_output/3.nature_large.png" width="100%"></td>
    <td width="50%"><img src="images_output/4.nature_mega.png" width="100%"></td>
  </tr>
  <tr>
    <td align="center">1280×829</td>
    <td align="center">2048×1327</td>
  </tr>
</table>

d.
<h3>Laptop 1</h3>

<table width="100%">
  <tr>
    <td width="50%"><img src="images_output/Laptop1_runtime.png" width="100%"></td>
    <td width="50%"><img src="images_output/Laptop1_speedup.png" width="100%"></td>
  </tr>
  <tr>
    <td align="center">Laptop 1: Laufzeitvergleich CPU vs. PyOpenCL</td>
    <td align="center">Laptop 1: Speedup CPU vs. PyOpenCL</td>
  </tr>
  <tr>
    <td width="50%"><img src="images_output/Laptop1_runtime2.png" width="100%"></td>
    <td width="50%"><img src="images_output/Laptop1_speedup2.png" width="100%"></td>
  </tr>
  <tr>
    <td align="center">Laptop 1: Laufzeitvergleich CPU vs. PyOpenCL vs. OpenCV</td>
    <td align="center">Laptop 1: Speedup CPU vs. PyOpenCL und OpenCV</td>
  </tr>
</table>

<h3>Laptop 2</h3>

<table width="100%">
  <tr>
    <td width="50%"><img src="images_output/Laptop2_runtime.png" width="100%"></td>
    <td width="50%"><img src="images_output/Laptop2_speedup.png" width="100%"></td>
  </tr>
  <tr>
    <td align="center">Laptop 2: Laufzeitvergleich CPU vs. PyOpenCL</td>
    <td align="center">Laptop 2: Speedup CPU vs. PyOpenCL</td>
  </tr>
  <tr>
    <td width="50%"><img src="images_output/Laptop2_runtime2.png" width="100%"></td>
    <td width="50%"><img src="images_output/Laptop2_speedup2.png" width="100%"></td>
  </tr>
  <tr>
    <td align="center">Laptop 2: Laufzeitvergleich CPU vs. PyOpenCL vs. OpenCV</td>
    <td align="center">Laptop 2: Speedup CPU vs. PyOpenCL und OpenCV</td>
  </tr>
</table>



| Laptop | Bildgröße | CPU-Zeit in s | PyOpenCL-Zeit in s | OpenCV-Zeit in s | Speedup PyOpenCL | Speedup OpenCV |
| ------ | --------: | ------------: | -----------------: | ---------------: | ----------------: | -------------: |
| Laptop 1 | 640×415 | 0.001519 | 0.000843 | 0.000266 | 1.803074 | 5.717592 |
| Laptop 1 | 1024×663 | 0.004478 | 0.003081 | 0.000389 | 1.453387 | 11.498905 |
| Laptop 1 | 1280×829 | 0.036199 | 0.006760 | 0.000560 | 5.354889 | 64.600783 |
| Laptop 1 | 2048×1327 | 0.080978 | 0.014617 | 0.001083 | 5.539958 | 74.748139 |
| Laptop 2 | 640×415 | 0.006349 | 0.004885 | 0.000225 | 1.299629 | 28.255228 |
| Laptop 2 | 1024×663 | 0.016662 | 0.007390 | 0.000326 | 2.254660 | 51.063590 |
| Laptop 2 | 1280×829 | 0.026199 | 0.010545 | 0.001247 | 2.484481 | 21.004249 |
| Laptop 2 | 2048×1327 | 0.070870 | 0.019683 | 0.002698 | 3.600474 | 26.264106 |

## Interpretation
Die Ergebnisse zeigen deutliche Unterschiede zwischen den drei Implementierungsvarianten.

Die einfache CPU-Baseline ist die langsamste Variante, besonders bei größeren Bildern. Das ist zu erwarten, weil das Bild Schritt für Schritt mit NumPy-Operationen auf der CPU verarbeitet wird. Dabei werden große Arrays mehrfach gelesen und geschrieben, was zusätzliche Speicherzugriffe und Laufzeit verursacht.

PyOpenCL ist auf beiden Laptops schneller als die Baseline. Der Vorteil wird vor allem bei größeren Bildern sichtbar, weil mehr Pixel parallel auf der GPU verarbeitet werden können. Gleichzeitig hat PyOpenCL aber auch Overhead. Die Bilddaten müssen in ein eindimensionales Array umgewandelt, in GPU-Buffer kopiert, vom OpenCL-Kernel verarbeitet und anschließend wieder in den Arbeitsspeicher zurückkopiert werden. Bei kleinen Bildern wirkt sich dieser Overhead stärker aus, wodurch der Speedup kleiner sein kann.

OpenCV ist in fast allen Messungen die schnellste Variante. Das liegt daran, dass OpenCV stark optimierte native C/C++-Funktionen für Bildverarbeitung verwendet. Diese Funktionen sind deutlich effizienter als die einfache eigene CPU-Implementierung und vermeiden außerdem einen großen Teil des manuellen GPU-Overheads von PyOpenCL.

Der Vergleich zwischen Laptop 1 und Laptop 2 zeigt, dass die Laufzeit nicht nur vom Namen der CPU oder GPU abhängt. Auch Treiber, OpenCL-Implementierung, OpenCV-Version, Speicherbandbreite, Energieeinstellungen und Hintergrundprozesse können das Ergebnis beeinflussen. Besonders bei kleinen Bildern sind die gemessenen Laufzeiten sehr kurz, sodass kleine Unterschiede auch durch Messrauschen entstehen können.

Insgesamt zeigt die Aufgabe, dass Bildverarbeitung ein datenparalleles Problem ist. Parallelisierung mit PyOpenCL kann die Laufzeit verbessern, besonders bei größeren Bildern. Für diese konkrete Aufgabe ist OpenCV jedoch die beste praktische Lösung, weil es am schnellsten und gleichzeitig am einfachsten zu verwenden ist. PyOpenCL ist trotzdem sinnvoll, um zu verstehen, wie GPU-Parallelisierung intern funktioniert.

## Getting Started

### Dependencies

- Python 3.10+
- NumPy
- Matplotlib
- PyOpenCL
- OpenCV

### Installing

Repository klonen:

```bash
git clone url
cd 
```

## Authors 
Maxim Schmidt HTW Berlin (M.Sc. Applied Computer Science) Maxim.Schmidt@Student.HTW-Berlin.de

Sarra Malek HTW Berlin (M.Sc. Applied Computer Science) Sarra.Malek@Student.HTW-Berlin.de

## License  

This project is licensed under the MIT License.

## Acknowledgments

https://documen.tician.de/pyopencl/index.html </br>
https://opencv-tutorial.readthedocs.io/en/latest/
