# Panel de Asesores · Venezuela y Argentina

Panel de asesores de Turisto (versión 2) para las rutas **Venezuela**, **Argentina** y **Arg / Vzla**. Usa los datos **reales**: el mismo Supabase (`oovinssezxntmnphprgg`) y los mismos Apps Script del panel anterior. Es el mismo panel v2 de Colombia y España, con la configuración de estas rutas.

## Qué cambia frente al panel de Colombia y España

- Tres rutas. Argentina y Arg / Vzla comparten un Apps Script: el panel le manda `?ruta=ARGENTINA` o `?ruta=ARGVZLA` y nunca le hace dos peticiones a la vez.
- Pausa del reparto por grupos, como en el panel v1:
  - **Venezuela**: Venezuela + Arg / Vzla (asesores venezolanos).
  - **Argentina y Arg / Vzla**: Argentina + Arg / Vzla (todos).
  - Si un grupo queda a medias, el panel lo muestra y deja completar la pausa o reanudar todo.
- Turno AM de 9:00 a 17:00 y PM de 18:00 a 23:00, hora de Caracas, en las tres rutas.
- Leads erróneos con revisión de la captura por IA (función que en Supabase se llama `verificar-captura-erroneo`; su URL es `super-action`).

## Qué hace

- Inicio de sesión con las mismas cuentas del panel anterior.
- Leads con comprobante de contacto obligatorio (solo leads asignados desde que se instaló este panel) y estados.
- Historial y estadísticas por periodo: hoy, 7, 30 o 90 días, todo o fechas a elegir.
- Registro en el turno: en una ruta o en todas. Primero la hoja de reparto (Apps Script) y después Supabase.
- Aviso cuando alguien figura en el turno del panel pero no en la hoja de reparto.
- Asignadora: rutas por asesor, anotar y sacar del turno, nombrar asignadores, bloquear, retirar, pausa del reparto, asignar a mano, revisión de equidad del reparto y ajustes.

## Antes de usarlo

En el Supabase de Venezuela/Argentina, en este orden:

1. `02_supabase_verificacion_ia.sql` (el mismo de Colombia/España). ✅ 6 nov
2. `06_venezuela_argentina_panel_v2.sql`. ✅ 6 nov
3. Función de IA desplegada (URL `super-action`) y el secreto `ANTHROPIC_API_KEY`. ✅ 6 nov
4. Con los asesores ya en este panel: Ajustes → Revisión con IA → Obligatoria.
