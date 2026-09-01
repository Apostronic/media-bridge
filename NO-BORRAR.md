# NO BORRAR - archivos con dependencia viva

> Generado el 2026-09-01, tras restaurar 52 archivos que una limpieza borro por error.
> Los archivos de esta lista estan enlazados desde algo que YA salio a produccion: la firma
> de correo de todo el equipo, el sitio web publicado y correos ya enviados. Borrarlos rompe
> piezas que ya estan en manos de sus destinatarios, y eso no se deshace reenviando nada.

## Antes de borrar CUALQUIER archivo de `media/`

Un archivo no es "produccion consumida" porque lo parezca por el nombre o la fecha.
Comprobar las tres superficies:

1. **Workspace** - `grep -r "media-bridge/main/media/" <carpeta del workspace>`
   (ojo: `ripgrep` filtra por `.gitignore` y se salta las firmas; usar `grep` a secas).
2. **Sitio en vivo** - descargar las paginas de mowiapp.com (ES/EN/PT) y buscar
   `media-bridge/main/media/`. El JS global del snippet 3895 tambien puede enlazar archivos.
3. **Correo** - revisar `canales/email/**/*.html` y los `.zip` de campana. La mayoria usa el
   CDN de Mailchimp, pero NO todos: hay correos que apuntan a este repo.

Si aparece en cualquiera de las tres, no se borra.

## Como restaurar si ya se borro

Nada se pierde: el archivo sigue en el historial de git.

```bash
git log --diff-filter=D --name-only --pretty=format:"%h %s"   # hallar el commit del borrado
git checkout <commit>^ -- "media/<archivo>"                    # restaurar desde su padre
```

## Donde se usa cada grupo

| Grupo | Lo enlaza |
|---|---|
| `GIF_Firma_v12` | `firma-generador-mowi.html`, `firma-mowi-dani.html`, `firma-marketing-mowi.html`, `firmas-departamentos-mowi.html` |
| `firma-foto-*` y fotos con nombre completo | El generador de firmas del equipo (una por persona) |
| `cotizador-demo-h-optA-madrid-usd-*` | Portadas del sitio en vivo, en los 3 idiomas (`/`, `/en/`, `/pt/`) |
| `cotizador-manager-demo-20260806-224822.webp` | `email-cotizador-C-autonomia.html` y `email-cotizador-D-portugues.html` (correos ya enviados) |

## Lista

### GIF de la firma de correo (1)

- `GIF_Firma_v12-20260729-141546.gif`

### Cotizador - sitio en vivo y correos del lanzamiento (3)

- `cotizador-demo-h-optA-20260814-150924.webp`
- `cotizador-demo-h-optA-madrid-usd-20260827-142535.webp`
- `cotizador-manager-demo-20260806-224822.webp`

### Fotos de firma del equipo (55)

- `firma-foto-alei-ruiz.png`
- `firma-foto-alejandra-deleon.png`
- `firma-foto-alejandra-santana.png`
- `firma-foto-alonso-de-la-rosa.png`
- `firma-foto-amanda-duarte.png`
- `firma-foto-ana-figueroa.png`
- `firma-foto-analia-aguirre.png`
- `firma-foto-barbara-benitez.png`
- `firma-foto-brenda-quijada.png`
- `firma-foto-carlos-contreras.png`
- `firma-foto-carlos-moreno.png`
- `firma-foto-crisleidys-tocuyo.png`
- `firma-foto-dani-bastardo.png`
- `firma-foto-danyerson-bastardo.png`
- `firma-foto-david-forero.png`
- `firma-foto-dorian-lescano.png`
- `firma-foto-edward-forero.png`
- `firma-foto-enrique-aldama.png`
- `firma-foto-fabian-da-silva.png`
- `firma-foto-fernando-marques.png`
- `firma-foto-gabriela-centurion.png`
- `firma-foto-gabriella-castro.png`
- `firma-foto-gonzalo-da-cunha.png`
- `firma-foto-iliana-nieves.png`
- `firma-foto-ismaily-jhoe.png`
- `firma-foto-jason-reina.png`
- `firma-foto-jessica-carvajal.png`
- `firma-foto-jesus-perez.png`
- `firma-foto-jorge-acosta.png`
- `firma-foto-jose-baptista.png`
- `firma-foto-juan-daniel-guariman.png`
- `firma-foto-karol-palma.png`
- `firma-foto-leticia-martins.png`
- `firma-foto-lorena-rodriguez.png`
- `firma-foto-luis-mosquera.png`
- `firma-foto-mariangela-colina.png`
- `firma-foto-marketing-mowi-20260804-130311.png`
- `firma-foto-mary-lucena.png`
- `firma-foto-mayra-guedes.png`
- `firma-foto-mercedes-villalba.png`
- `firma-foto-miguel-maurera.png`
- `firma-foto-nestor-mayora.png`
- `firma-foto-oriana-gonzalez.png`
- `firma-foto-pablo-medrano.png`
- `firma-foto-silvia-marcano.png`
- `firma-foto-sofia-gil.png`
- `firma-foto-tamiris-leite.png`
- `firma-foto-valeria-silva.png`
- `firma-foto-veronica-urbano.png`
- `firma-foto-whisgel-gonzalez.png`
- `firma-foto-willians-valera.png`
- `firma-foto-wleimer-briceno.png`
- `firma-foto-xiorimar-albarran.png`
- `firma-foto-yasmin-silva.png`
- `firma-foto-yudith-alcala.png`

### Fotos de firma (nombre completo) (13)

- `Amanda-Rodrigues-Duarte-20260803-114131.png`
- `Ana-Leticia-Figueroa-de-Sá-20260803-114148.png`
- `Carlos-Moreno-20260803-114201.png`
- `Fabian-Da-silva-20260803-114216.png`
- `Gabriella-Castro-Odorico-20260803-114231.png`
- `Iliana-Luisianne-Nieves-Molina-20260803-114244.png`
- `Jesica-Del-Valle-Carvajal-Hernandez-20260803-114257.png`
- `Juan-Daniel-Guariman-Carreño-20260803-114309.png`
- `Leticia-Martins-Araruna-de-Melo-20260803-114326.png`
- `Oriana-Lourdes-González-Requena-20260803-114343.png`
- `Veronica-Luciana-Da-Cunha-20260803-120414.png`
- `Whisgel-Jesús-Gonzalez-Abella-20260803-114355.png`
- `Wleymer-Abdel-Briceño-Méndez-20260803-114412.png`

## Excluidos a proposito (NO restaurar)

Se retiraron deliberadamente porque este repositorio es PUBLICO:

- `minidumps-rtx3050-0x133-*.zip` - volcados de memoria de Windows
- `kit-claude-laptop-remota-*.zip` - kit de configuracion
