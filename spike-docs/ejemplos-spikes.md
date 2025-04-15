# Ejemplos de Spikes Técnicos

A continuación se presentan dos ejemplos de Spikes bien estructurados, aplicados a contextos de Frontend y Backend.

---

## Spike – Frontend

### Problema / Duda Técnica  
¿Es posible aplicar Lazy Loading con React Router v6 sin afectar el renderizado inicial ni la experiencia del usuario?

### Objetivo del Spike  
Determinar si el uso de Lazy Loading en rutas secundarias mejora la carga inicial sin afectar la navegación.

### Timebox  
4 horas

### Entregables Esperados  
- Comparativa de rendimiento con y sin Lazy Loading  
- Rama temporal con prueba funcional  
- Documento técnico con decisión final

### Resultado / Conclusión  
Lazy Loading es viable para rutas secundarias. Reduce el tamaño del bundle inicial en un 38% y mejora el LCP en 1.2s. Se recomienda implementarlo parcialmente.

---

## Spike – Backend

### Problema / Duda Técnica  
¿Cómo se puede gestionar la autenticación entre microservicios de forma segura: usando JWT o API Keys?

### Objetivo del Spike  
Comparar ambas soluciones y determinar cuál se adapta mejor a nuestra arquitectura basada en Node.js y RabbitMQ.

### Timebox  
6 horas

### Entregables Esperados  
- Cuadro comparativo entre JWT y API Keys  
- Código de ejemplo básico para ambos enfoques  
- Recomendación técnica y riesgos asociados

### Resultado / Conclusión  
Se recomienda el uso de JWT firmados con clave secreta compartida. Ofrece mayor flexibilidad, escalabilidad y seguridad en entornos distribuidos.

---