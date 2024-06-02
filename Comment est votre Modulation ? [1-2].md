![1-2M](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/1-2_M.png?raw=true)

*Fichier:*

[flag.raw](https://github.com/ReZ3R0/404CTF-2024/blob/main/Files/flag.raw)

## Résolution du challenge avec Python:

- L'indice "ASK" : Nous indique que la méthode de modulation utilisée est de type (Amplitude Shift Keying, ASK), où la porteuse change d'amplitude selon les données à transmettre.
- L'objectif est de récupérer les données modulées (probablement une image cachée), en interprétant correctement le signal brut.



```python3
import numpy as np
from PIL import Image
import io

file = 'flag.raw'

sampling_rate = 350000  # Fréquence d'échantillonnage en Hz
symbol_rate = 1000      # Débit en symboles/sec
carrier_freq = 7000     # Fréquence de la porteuse en Hz

signal = np.fromfile(file, dtype=np.float32)
```
  - J'utilise numpy et PIL pour manipuler les données.
  - Le fichier signal est lu en tant que données float32.


### Traitement du signal

```python3
points_per_symbol = int(sampling_rate / symbol_rate)
```
Calcul du nombre de points par symbole pour déterminer combien de points d'échantillonnage du fichier brut sont utilisés pour représenter un seul symbole du signal.
En divisant la fréquence d'échantillonnage par le débit. Dans notre cas, avec une fréquence d'échantillonnage de 350 kHz et un débit de 1 kHz, chaque symbole est représenté par 350 points du signal.


```python3
decoded_values = []
for i in range(125, len(signal), points_per_symbol):
    amplitude = abs(signal[i])  # Valeur absolue pour prendre l'amplitude
    decoded = round(amplitude * (256 - 1))
    decoded_values.append(decoded)
```
- Après plusieurs tests on commence à l'index 125 pour capturer l'amplitude maximale de ce symbole.
- Calcul de l'amplitude et décodage abs(signal[i]) prend la valeur absolue du point de signal à l'indice i.
  round(amplitude * (256 - 1)) convertit cette amplitude en une valeur entière dans la plage de 0 à 255, en supposant que chaque symbole peut représenter une valeur dans cette plage (valence de 256).
  Ce calcul ajuste l'amplitude du signal à une échelle de 0 à 255, qui est standard pour les valeurs de pixels dans les images en niveaux de gris.
- Stockage des valeurs décodées qui seront ensuite tentées d'être formées en une image. Chaque valeur dans decoded_values représente un pixel de l'image que l'on tente de reconstruire.
  Si les données sont correctement formatées et si elles représentent effectivement une image, alors la section suivante du script tentera de convertir cette liste de valeurs en une image visible.

```python3
png_buffer = bytes(decoded_values)

try:
    image = Image.open(io.BytesIO(png_buffer))
    image_path = 'flag.png'
    image.save(image_path)
    print(f"flag lisible dans flag.png")
except IOError as e:
    print(f"Erreur: {e}")
```
- On converties les valeurs décodées en un tampon de bytes.
- Ce tampon est ensuite utilisé pour tenter d'ouvrir l'image.
- Si les données décodées forment une image valide, elle est enregistrée. Sinon, j'affiche une une erreur.

![flag](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/Flag_1-2_M.png?raw=true)




