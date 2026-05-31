# Aufgabe 08: Graustufen und Bildanalyse

Dieses Repository enthält den Code und die Ergebnisse für die Belegaufgabe **„Aufgabe 08: Graustufen und Bildanalyse“** im Kurs **Programmierkonzepte und Algorithmen** (HTW Berlin,  Semester 2026).

Aufgaben des Projekts sind:

- a. Laden Sie ein RGB-Bild und wandeln Sie es in ein Graustufenbild um.
- b. Passen Sie anschließend Helligkeit und Kontrast des Bildes an.
- c. Berechnen Sie zum Schluss das Histogramm der Grauwerte und stellen Sie es geeignet dar
- (d. Laufzeit und Speedup verlgleichen)

Die Aufgaben werden auf 2 Laptops mit unterschiedlichen Specs ausgeführt:

1. Laptop:
- Prozessor  Intel(R) Core(TM) Ultra 7 258V, 2200 MHz, 8 Kern(e), 8 logische(r) Prozessor(en)
- GPU: Intel(R) Arc(™) 140V GPU (16GB)

2. Laptop: xxx


Es werden 3 Varianten verglichen werden:


| Variante | Name                 | Aufgabe                                   |
| -------- | ----------------------- | ------------------------------------------- |
| 1        | Baseline / CPU      | Version ohne Parallelisierung       |
| 2        | OpenCV/ CPU |  Bibliothek zum Vergleich |
| 3        | PyOpenCL / GPU |  parallele OpenCL-Version             |

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

<table width="100%">
  <tr>
    <td width="50%"><img src="images_output/runtime.png" width="100%"></td>
    <td width="50%"><img src="images_output/speedup.png" width="100%"></td>
  </tr>
  <tr>
    <td align="center">Laufzeitvergleich CPU vs. PyOpenCL</td>
    <td align="center">Speedup CPU vs. PyOpenCL</td>
  </tr>
</table>



| Laptop   | Bildgröße | CPU-Zeit in s | PyOpenCL-Zeit in s | OpenCV-Zeit | Speedup |
| -------- | --------: | -------: | ------------: | ----------: | ------: |
| Laptop 1 |   640×415 | 0.001719 | 0.000930 | – | 1.847721 |
| Laptop 1 |  1024×663 | 0.004899 | 0.003035 | – | 1.614145 |
| Laptop 1 |  1280×829 | 0.032464 | 0.006912 | – | 4.696922 |
| Laptop 1 | 2048×1327 | 0.081066 | 0.016662 | – | 4.865241 |
| Laptop 2 |   640×415 |        … |             … |           … |       … |
| Laptop 2 |  1024×663 |        … |             … |           … |       … |
| Laptop 2 |  1280×829 |        … |             … |           … |       … |
| Laptop 2 | 2048×1327 |        … |             … |           … |       … |

## Interpretation


## Getting Started

### Dependencies

- Python 3.10+
- NumPy
- Matplotlib
- PyOpenCL
- OpenCV
- (Openpyxl)

### Installing

Repository klonen:

```bash
git clone url
cd 
```

## Authors 
Maxim Schmidt HTW Berlin (M.Sc. Applied Computer Science) Maxim.Schmidt@Student.HTW-Berlin.de

xxxxxxx

## License  


## Acknowledgments 


