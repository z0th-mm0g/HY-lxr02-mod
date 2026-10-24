
<img width="1280" height="60" alt="Screenshot 2026-10-24 at 11 27 23 AM" src="https://github.com/user-attachments/assets/8b7099b8-e39a-40cf-949b-4016445a163c" />

# Heal Youth mod para el Erica Synths LXR-02

Firmware modificado (no oficial) para el Erica Synths LXR-02, basado en el firmware
oficial open source v1.7 de Erica Synths (GPL-3.0). Autor del mod: Heal Youth // Zwolle Poxi.

> Firmware modificado: úsalo bajo tu propio riesgo. Erica Synths no da soporte para firmware
> modificado. Siempre podés volver al oficial instalando su `.img` por la SD.

## Qué agrega

- **Beat repeat (FX `rpt`)**: stutter sincronizado al tempo. `typ` = fwd / rev / rnd,
  `len` = largo (1/4 … 1/128, se muestra el nombre), `prb` = chance por paso
  (0 = apagado, 127 = trabado), `pit` = pitch por repetición (centro = nada, ±2 semitonos
  por vuelta, tope 1 octava), `shr` = cada vuelta más corta.
- **Bitcrusher (FX `bit`)**: `bit` bits, `dwn` downsample, `jit` jitter, `vol` volumen.
- **PERF, segunda solapa**: `prb`, dry/wet y `hum`. Con SHIFT apretado: `len`, `pit` y `shr`.
- **Humanize (`hum`)**: velocidad al azar (hasta ±31), solo cambia el volumen.
- **CPU meter (`cpu`)**: segunda página de ajustes globales.
- La pantalla de arranque dice "Heal Youth mod".

Recordá mandar las voces al bus de FX (salida = FX en la página de mezcla de cada voz).

## Instalar

1. Copiá el `LXR_V2_V1.7_HY*.img` a la raíz de la SD (FAT32). Que sea el único `LXR*.img`.
2. Prendé el LXR con el encoder apretado hasta ver "LXR Updater" y esperá "Update OK!".
3. Apagalo del todo y prendelo de nuevo.

## Compilar

Igual que el firmware oficial (ver README.md), pero usá el **Arm GNU Toolchain 11.3**:
con otros compiladores (por ejemplo el GCC 13 de Ubuntu) la pantalla del LXR quedó con la
fila de abajo vacía.

```sh
cmake --preset release -DARM_TOOLCHAIN_DIR=<carpeta bin del toolchain 11.3>
cmake --build --preset release
```
<img width="1320" height="64" alt="Screenshot 2026-10-24 at 11 27 17 AM" src="https://github.com/user-attachments/assets/4e9dcd45-7830-4d12-b7e3-004b7764bcc0" />
