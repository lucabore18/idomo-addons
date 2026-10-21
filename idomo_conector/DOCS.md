# Idomo

Conecta esta casa con Idomo para que el panel técnico y la app puedan consultarla y aplicar cambios de configuración, siempre a pedido de una persona con permiso.

## Qué hace y qué no

- **Abre una conexión hacia Idomo.** No abre puertos en tu red.
- **Solo hace lo que está en su lista:** consultar el estado de la casa, poner un equipo en un ambiente, ocultar entidades, deshabilitar un dispositivo repetido y deshacer esos cambios.
- **No toca nada de seguridad:** no oculta ni deshabilita cerraduras, alarma, cámaras ni sirenas. No abre ni desarma nada.
- **No saca de la casa** video, audio, cámaras, ubicaciones ni coordenadas.
- El token de Home Assistant que usa es el del Supervisor, y nunca sale de la casa.

Si el add-on se detiene o se desinstala, la casa sigue funcionando exactamente igual.

## Configuración

| Opción | Qué poner |
| --- | --- |
| `gateway` | La dirección del gateway de Idomo (te la da Idomo) |
| `casa_id` | El identificador de esta casa en Idomo |

## La primera vez

Al arrancar por primera vez, el add-on genera su clave y muestra la pública en el registro (pestaña **Registro**), en una línea que dice "clave nueva". Idomo la registra para esta casa. Hasta que esté registrada, el add-on no puede conectarse.

La clave privada queda guardada en el add-on y entra en las copias de seguridad de Home Assistant.
