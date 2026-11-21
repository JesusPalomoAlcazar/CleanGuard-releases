# CleanGuard

Utilidad de mantenimiento para Windows 11: limpieza de archivos temporales y cachés, gestor de programas
de inicio, limpiador del registro con copia de seguridad previa e instalación de actualizaciones de Windows y de
programas (con winget), reparación de Windows (DISM, SFC, chkdsk y puntos de restauración), mantenimiento (Windows Update, red y
componentes) y diagnóstico de discos, memoria y batería.

Desarrollado por [Jesús Palomo](https://jesuspalomoalcazar.github.io/).

## Descarga

Descarga `CleanGuard.exe` de la última versión en
[Releases](https://github.com/JesusPalomoAlcazar/CleanGuard-releases/releases/latest).
CleanGuard avisa automáticamente cuando hay una versión nueva.

**No requiere instalación** ni tener .NET instalado: guarda `CleanGuard.exe` donde quieras y ábrelo. Por eso no
aparece en el menú Inicio ni en «Aplicaciones instaladas»; si quieres, crea tú un acceso directo.

- **Actualizar:** descarga la versión nueva y sustituye el `.exe` anterior.
- **Desinstalar:** borra `CleanGuard.exe`. Si quieres eliminarlo todo, borra también la carpeta
  `%LocalAppData%\CleanGuard`, donde se guardan los registros de actividad, las copias de seguridad del registro
  (si la borras, ya no podrás deshacer reparaciones anteriores) y los informes de batería y de configuración de red.

## Aviso importante: el programa no está firmado

CleanGuard **no está firmado digitalmente**: firmar un programa requiere un certificado de pago que por ahora este
proyecto no tiene. Por eso Windows no reconoce al editor y puede mostrar avisos o bloquearlo. Esto no significa que contenga
virus, pero solo deberías ejecutarlo si confías en el origen: descárgalo únicamente desde esta página.

### Si aparece «Windows protegió su PC» (SmartScreen)

1. Pulsa **Más información**.
2. Pulsa **Ejecutar de todas formas**.

Este aviso puede aparecer de nuevo con cada versión nueva.

### Si Windows bloquea el programa sin opción de ejecutarlo (Smart App Control)

Si tienes **Smart App Control** activado, Windows bloquea los programas sin firmar y no ofrece forma de ejecutarlos.
La única manera de usar CleanGuard es desactivarlo:

*Seguridad de Windows → Control de aplicaciones y navegador → Configuración de Smart App Control → Desactivado*

**Antes de hacerlo, ten en cuenta:**

- Es una protección de seguridad de Windows; desactivarla es decisión tuya.
- En algunas versiones de Windows, **una vez desactivado no se puede volver a activar sin reinstalar Windows**.
- Microsoft Defender y SmartScreen siguen funcionando aunque lo desactives.

## Permisos de administrador

Al abrirse, CleanGuard pide permisos de administrador. Son necesarios para limpiar carpetas del sistema
(como `C:\Windows\Temp` o los restos de Windows Update), gestionar los programas de inicio de todo el equipo,
reparar el registro, instalar actualizaciones y ejecutar las herramientas de reparación de Windows.

## Seguridad

- **Analizar nunca borra ni modifica nada.** Tú eliges qué se limpia.
- Solo se borran archivos dentro de carpetas conocidas y con más de 24 horas de antigüedad. Las excepciones son la
  papelera de reciclaje (si la marcas, se vacía entera), las copias que deja «Reiniciar Windows Update», que se
  borran por carpetas enteras, y lo que borra la propia herramienta de Windows (optimización de distribución e
  instalación anterior de Windows). La instalación anterior de Windows sale desmarcada: borrarla impide volver a ella.
- Los programas de inicio se deshabilitan sin borrarlos; se pueden volver a habilitar.
- Antes de reparar el registro se guarda una copia `.reg` de cada clave afectada. Si la copia falla, no se modifica
  nada. La última reparación se puede deshacer con doble clic en el indicador **MODO SEGURO**.
- En **Actualizaciones**, buscar no instala nada: tú marcas qué actualizaciones de Windows y qué programas se
  instalan. Si Windows necesita reiniciar, CleanGuard te lo pregunta antes.
- En **Reparación**, lo que cambia el equipo se ejecuta solo cuando lo confirmas y no se corta a medias. La reparación
  completa del disco y la prueba de memoria se programan para el reinicio y se pueden anular antes. Reiniciar
  Windows Update no borra sus carpetas: las guarda con otro nombre. Antes de restablecer la red se guarda tu
  configuración actual en un archivo.
- Todo queda registrado en `%LocalAppData%\CleanGuard\logs`.
