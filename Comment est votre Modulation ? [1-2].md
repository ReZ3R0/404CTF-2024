![1-2M](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/1-2_M.png?raw=true)

**Fichier:
[flag.raw](https://github.com/ReZ3R0/404CTF-2024/blob/main/Files/flag.raw)

## Résolution du challenge avec Python:

    - L'indice "ASK" : Nous indique que la méthode de modulation utilisée est de type (Amplitude Shift Keying, ASK), où la porteuse change d'amplitude selon les données à transmettre.
    - L'objectif est de récupérer les données modulées (probablement une image cachée*), en interprétant correctement le signal brut.



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
  - numpy est utilisé pour manipuler les données.
  - PIL est utilisé pour manipuler les formats de fichiers d'image.
  - Le fichier signal est lu en tant que données de type float32.

![flag](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/Flag_1-2_M.png?raw=true)


* J'ai un peu galéré avec ce challenge avant de réussir en premier "Comment est votre modulation ? [2/2]", où nous devions reconstruire une image .png :grin:

