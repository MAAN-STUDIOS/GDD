# Requerimientos

**Niveles de relevancia**:

- `[Crítico]`: Esencial para un prototipo jugable.
- `[Importante]`: Ideal para un segundo prototipo más completo.
- `[Opcional]`: Útil después del prototipo; se puede implementar más adelante.

## Funcionales

### Jugabilidad Principal

- `[Crítico]` Sistema de historia ramificada: Narrativa simple que avanza con descubrimiento de logs o eventos.
- `[Crítico]` Exploración procedural de mapas: Mapas generados con semilla (aunque básicos).
- `[Crítico]` Sistema de supervivencia realista: Oxígeno, hambre y descanso con efectos mínimos en gameplay.
- `[Crítico]` Manejo de recursos: Recolección de elementos esenciales (agua, comida, oxígeno, energía).
- `[Importante]` Sistema de progresión del personaje: Mejoras básicas aplicables entre sesiones o en partida.
- `[Importante]` Gestión de riesgo-recompensa: Loot aleatorio, posibilidad de trampas y penalización por muerte.
- `[Opcional]` Eventos dinámicos: Alteraciones temporales del entorno (bloqueos, tormentas, etc.).
- `[Opcional]` Finales múltiples: Variaciones narrativas al completar el objetivo.
- `[Importante]` Progresión entre runs: Conservación de historia y mejoras modulares entre sesiones.
- `[Importante]` Campo de visión limitado: Visibilidad parcial (145°) por raycasting o técnica equivalente.
- `[Importante]` Sistema de crafting rápido: Crear objetos básicos desde el inventario.

### IA y Enemigos

- `[Crítico]` Sistema de enemigos Flood: IA simple con detección, patrullaje y ataque.
- `[Crítico]` Escalada de dificultad: Flood más peligrosos conforme avanza la partida.
- `[Importante]` Entorno influenciado por enemigos: Tiles orgánicos o elementos mutados generados por enemigos.
- `[Importante]` Jefes especiales y mutaciones: Al menos un mini-jefe con habilidades únicas.

### Multijugador

- `[Crítico]` Partidas privadas y públicas: Creación y conexión simple entre jugadores con semilla compartida.
- `[Crítico]` Loot tras muerte: Inventario visible y recuperable por otros jugadores tras la muerte.
- `[Importante]` Cooperación o traición: Interacción libre entre jugadores (aliarse o atacarse).
- `[Importante]` Comunicación in-game: Chat de texto básico.
- `[Opcional]` Matchmaking filtrado: Búsqueda por dificultad, entorno o número de jugadores.
- `[Opcional]` Reputación o karma: Impacto de decisiones sociales en el juego.
- `[Opcional]` Resumen al final de sesión: Estadísticas de jugador o partida.

### Mundo y Ambientación

- `[Crítico]` Ecosistemas diversos: Al menos dos biomas con diferencias visuales y de gameplay (ej. estación vs
  planeta).
- `[Crítico]` Narrativa ambiental: Detalles visuales y objetos que revelan fragmentos de historia sin texto explícito.
- `[Importante]` Regeneración por semilla: Mostrar, guardar y reutilizar semillas de mapa.
- `[Opcional]` Zonas seguras: Lugares sin enemigos donde se puede descansar o intercambiar.
- `[Opcional]` Entornos dinámicos: Cambios climáticos, efectos de gravedad o radiación.

### Personalización

- `[Importante]` Trajes personalizables: Cambios visuales o estadísticos por módulos.
- `[Importante]` Sistema modular de mejoras: Slots de casco, torso, piernas, visor, mochila.
- `[Importante]` Crafteo avanzado: Construcción limitada de herramientas y armas.
- `[Opcional]` Estilos alternativos desbloqueables: Apariencias especiales para traje o HUD.

### Interfaces y Feedback

- `[Crítico]` HUD contextual e inmersivo: Salud, oxígeno, sueño, hambre y minimapa.
- `[Crítico]` Resumen de progreso persistente: Bitácora de historia descubierta.
- `[Importante]` Mejoras permanentes pre-run: Gasto de recursos raros en mejoras iniciales.
- `[Opcional]` Leaderboard o ranking por sesión: Tabla comparativa al final de partida.
- `[Importante]` Indicadores visuales y auditivos: Feedback mínimo en eventos importantes (daño, detección,
  descubrimiento).

---

## No Funcionales

### Rendimiento

- `[Crítico]` Tiempo de carga optimizado: El juego debe iniciar en menos de 10 segundos desde el menú principal.
- `[Crítico]` Soporte para mundos grandes: El sistema debe manejar mapas generados por semilla sin caídas de FPS ni
  stuttering.
- `[Crítico]` Multijugador fluido: Las interacciones deben mantener latencia por debajo de 100 ms en condiciones
  normales.
- `[Importante]` Uso eficiente de memoria: Carga dinámica de sprites, audio y entidades solo cuando son necesarias.
- `[Importante]` Consumo bajo en frontend: El motor basado en canvas debe mantener un rendimiento aceptable sin WebGL.

### Escalabilidad y Red

- `[Importante]` Escalabilidad del servidor: Capacidad de escalar vertical/horizontalmente para sesiones concurrentes.
- `[Crítico]` Persistencia de progreso narrativo: Los fragmentos de historia deben guardarse aunque el jugador muera o
  cierre sesión.
- `[Importante]` Sincronización mínima: WebSocket optimizado para sincronizar lo esencial (jugadores, enemigos,
  eventos).
- `[Importante]` Soporte para sesiones concurrentes: Varios jugadores en mapas distintos sin conflictos de datos.
- `[Opcional]` Resiliencia ante desconexión: Reconexion automática y recuperación de estado.

### Seguridad

- `[Crítico]` Sistema anti-cheat: Detección y bloqueo de trampas comunes sin afectar el rendimiento.
- `[Importante]` Integridad del progreso: Validación en backend de datos críticos del jugador (no confiar en cliente).
- `[Crítico]` Control de acceso a partidas: Contraseña o invitación única para partidas privadas.
- `[Opcional]` Moderación básica: Silenciar, bloquear o reportar jugadores desde la interfaz.

### Experiencia de Usuario

- `[Crítico]` Diseño inmersivo del HUD: Visual limpio, información mínima pero clara, adaptable a contexto.
- `[Importante]` Narrativa envolvente audiovisual: Sonido e iluminación que reaccionen al entorno y narrativa.
- `[Importante]` Accesibilidad: Subtítulos, reconfiguración de controles, modo de daltonismo y tamaño de texto.
- `[Importante]` Feedback inmediato: Animaciones o sonidos tras acciones importantes como daño o descubrimientos.
- `[Opcional]` Tiempo de aprendizaje razonable: Tutorial opcional integrado en la primera zona.

### Mantenibilidad

- `[Crítico]` Modularidad del código: Separación clara por entidades y componentes (jugador, mapa, IA).
- `[Importante]` Estructura por componentes: Reutilización de mecánicas como IA, crafting, interfaz o físicas.
- `[Importante]` Logs detallados del servidor: Registro de errores y eventos clave durante las sesiones.
- `[Opcional]` Soporte para expansión: Arquitectura que permita agregar nuevas clases, armas, biomas o modos.
- `[Opcional]` Documentación interna: Comentarios y estándares consistentes dentro del código base.

