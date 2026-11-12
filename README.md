# reloj-bot

Reloj que lanza cada 30 minutos el workflow `bot.yml` de otro repositorio (indicado en el secreto `BOT_REPO`), usando una clave limitada guardada en el secreto `BOT_TOKEN`.

El cron de GitHub Actions se salta muchos turnos, así que este workflow no depende de él: cada ejecución dura unas 5,5 horas, lanza el bot cada 30 minutos y al terminar se encadena con la siguiente. El cron solo sirve de respaldo para reiniciar la cadena si se corta.

- Arrancar o reiniciar: Actions → `reloj` → Run workflow → `bucle`.
- Probar una sola vez: Run workflow → `prueba`.
- Parar: Actions → `reloj` → Disable workflow (y cancelar la ejecución en curso).
