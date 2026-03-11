📋 Itinerario de "Fase 1: Auditoría y Resiliencia"

## Caso 2: Gestión de almacenamiento y Logs (Logrotate)
- Un servidor web que no gestiona sus logs termina colapsando el disco duro, y una vez lleno, el sistema operativo empieza a corromperse (no puede escribir archivos temporales).
- Reto: Crear un log de 100MB artificialmente para ver cómo el sistema gestiona el espacio. Luego, configurar logrotate para que el servidor archive y borre logs antiguos sin que tú tengas que intervenir.
- Qué aprenderás: Gestión de almacenamiento (df -h, du), particiones y mantenimiento preventivo.