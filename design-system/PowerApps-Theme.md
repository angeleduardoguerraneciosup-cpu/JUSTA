# AESA Way – Tema para Power Apps

## 1. App → Formulas (nombres de color reutilizables)
```powerfx
colNavy      = ColorValue("#00427F");
colNavyDark  = ColorValue("#002060");
colInk       = ColorValue("#232B45");
colOrange    = ColorValue("#FBA10F");
colOrangeDk  = ColorValue("#C77700");
colSlate     = ColorValue("#5B6478");
colLine      = ColorValue("#D0D9E6");
colSurface   = ColorValue("#F4F6FA");
colSky       = ColorValue("#1AA7EC");
colGreen     = ColorValue("#4EA72E");
```

## 2. Pantalla de inicio (scrHome)
Subir a Medios: `assets/aesa-way-logo.png` → `imgLogo`, `assets/home-background.svg` → `imgBg`.

| Control | Propiedad | Valor |
|---|---|---|
| scrHome | Fill | `White` |
| scrHome | BackgroundImage | `imgBg` |
| imgLogo | Image | `aesa_way_logo` |
| imgLogo | Width / Height | `460` / `130` |
| imgLogo | X | `(Parent.Width - Self.Width)/2` |
| imgLogo | Y | `Parent.Height*0.14` |

## 3. Botones centrados (Diálogo de Desempeño, GPIT, RDP)
Tres botones apilados, mismo ancho, centrados horizontal y verticalmente.

```powerfx
// btnDialogo (Texto: "Diálogo de Desempeño")  |  btnGPIT ("GPIT")  |  btnRDP ("RDP")
Width   = 480
Height  = 72
X       = (Parent.Width - Self.Width)/2
Y       = Parent.Height*0.40            // btnGPIT: +96 · btnRDP: +192
Fill    = colNavy
Color   = White
HoverFill   = colNavyDark
PressedFill = colOrange
PressedColor= colInk
BorderColor = colOrange
BorderThickness = 0
RadiusTopLeft = 12   // idem las 4 esquinas
Font    = Font.'Segoe UI'
Size    = 22
FontWeight = FontWeight.Semibold
DisplayMode = DisplayMode.Edit
FocusedBorderColor = colOrange
FocusedBorderThickness = 3
```
Principal (Diálogo de Desempeño): usar `Fill = colOrange`, `Color = colInk` si se quiere destacar una acción.

OnSelect: `Navigate(scrDialogo)`, `Navigate(scrGPIT)`, `Navigate(scrRDP)`.

## 4. Resto de pantallas
- Encabezado: rectángulo `Fill = colNavy`, alto 80, logo AESA en blanco a la derecha, franja naranja `colOrange` de 6 px debajo.
- Fondo: `White`; tarjetas `colSurface` con borde `colLine`.
- Texto: títulos `colNavy`, cuerpo `colInk`, secundario `colSlate`.
- Estados: éxito `colGreen`, info `colSky`, alerta `colOrange`.
