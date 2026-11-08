# CleanGuard

Utilidad de mantenimiento para Windows 11: limpieza de archivos temporales y cachés, gestor de programas
de inicio y limpiador del registro con copia de seguridad previa.

Desarrollado por [Jesús Palomo](https://jesuspalomoalcazar.github.io/).

## Descarga

Descarga `CleanGuard.exe` de la última versión en
[Releases](https://github.com/JesusPalomoAlcazar/CleanGuard-releases/releases/latest).
CleanGuard avisa automáticamente cuando hay una versión nueva.

**No requiere instalación** ni tener .NET instalado: guarda `CleanGuard.exe` donde quieras y ábrelo. Por eso no
aparece en el menú Inicio ni en «Aplicaciones instaladas»; si quieres, crea tú un acceso directo.

- **Actualizar:** descarga la versión nueva y sustituye el `.exe` anterior.
- **Desinstalar:** borra `CleanGuard.exe`. Si quieres eliminarlo todo, borra también la carpeta
  `%LocalAppData%\CleanGuard`, donde se guardan los registros de actividad y las copias de seguridad del registro
  (si la borras, ya no podrás deshacer reparaciones anteriores).

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
(como `C:\Windows\Temp` o los restos de Windows Update), gestionar los programas de inicio de todo el equipo y
reparar el registro.

## Seguridad

- **Analizar nunca borra ni modifica nada.** Tú eliges qué se limpia.
- Solo se borran archivos dentro de carpetas conocidas y con más de 24 horas de antigüedad. La excepción es la
  papelera de reciclaje: si la marcas, se vacía entera.
- Los programas de inicio se deshabilitan sin borrarlos; se pueden volver a habilitar.
- Antes de reparar el registro se guarda una copia `.reg` de cada clave afectada. Si la copia falla, no se modifica
  nada. La última reparación se puede deshacer con doble clic en el indicador **MODO SEGURO**.
- Todo queda registrado en `%LocalAppData%\CleanGuard\logs`.
