# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.
#
**Antes de la práctica:** No tenía claro cómo controlar los recursos, cómo se construyen imágenes propias ni cómo se comportan cuando fallan.

**Después de la práctica:** comprendí que los contenedores se pueden configurar y monitorear para que funcionen de forma estable. Aprendí a: limitar memoria y CPU , usar healthchecks para saber si un servicio realmente funciona, crear imágenes con un Dockerfile, aprovechar la caché de capas, identificar y eliminar imágenes huérfanas, y usar políticas de reinicio para decidir qué hace Docker cuando un contenedor se detiene.

**Problema solucionado:** Al construir la imagen con `FROM centos:7`, el paso `RUN yum update -y` falló con el error "Cannot find a valid baseurl for repo: base/7/x86_64", porque los repositorios de CentOS 7 ya no están disponibles. Lo solucioné agregando una línea al Dockerfile, justo después del `FROM`, que redirige los repositorios a `vault.centos.org`:

**Comandos adicionales utilizados:**
- `echo %NUMBER_OF_PROCESSORS%`: consultar el número de procesadores lógicos del equipo (en CMD de Windows).
- `docker info --format "{{.NCPU}}"`: consultar cuántos procesadores ve Docker para los contenedores.
  
**Beneficio profesional:** Estos conocimientos me permiten crear imágenes propias, controlar los recursos de cada contenedor y hacer que los servicios se recuperen solos ante fallos, lo que es útil para desplegar aplicaciones de forma estable en proyectos reales.
