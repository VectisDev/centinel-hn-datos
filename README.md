# centinel-hn-datos — retirado

Este repositorio está retirado. **El trabajo continúa en
[VIGIL](https://github.com/VectisDev/Vigil).**

## Qué había aquí, y por qué no se conserva

Un panel publicado y un recolector programado cada quince minutos. El recolector
instalaba sus dependencias desde `_engine/requirements-prod.txt`, una ruta que no
existe —la real es `requirements/prod.txt`—, así que el paso de instalación falló
en **todas** sus ejecuciones y el pipeline nunca llegó a correr.

La consecuencia tiene dos caras. La buena: como nunca corrió, **nunca consultó el
portal del Consejo Nacional Electoral**, así que no generó carga sobre un servicio
público. La mala: el panel siguió publicado durante meses afirmando un estado que
no medía nada. Las cincuenta revisiones de datos que llegó a guardar tienen
`national`, `departments`, `forensics` y `alerts` vacíos, todas.

No se pierde ninguna observación al retirarlo, porque no hubo ninguna.

## Dónde están los datos de verdad

En VIGIL:

| ruta | qué |
|---|---|
| `tests/fixtures/hnd_2025/` | 68 capturas reales del portal del CNE del 3 de diciembre de 2025, con sello OpenTimestamps |
| `web/data/hnd_2025_series.json` | la serie temporal derivada de esas capturas |
| `web/data/calibration_hnd_2025.json` | la calibración del método |

El modo REPLAY de VIGIL las reproduce y la raíz de Merkle vuelve a cuadrar. Eso
es lo que hace comprobable el trabajo, y nada de ello vivió nunca aquí.

---

English: this repository is retired; the work continues at
[VIGIL](https://github.com/VectisDev/Vigil). Its collector installed dependencies
from a path that does not exist, so it failed on every run and the pipeline never
executed. It therefore never queried Honduras' electoral portal — no load on a
public service — but the panel stayed up for months claiming a status it was not
measuring, and all fifty data revisions it committed were empty. No observation is
lost by retiring it, because there was none. The real captures, timestamped and
replayable, live in VIGIL.
