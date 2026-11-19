# Idomo

Conecta esta casa con Idomo para que el panel técnico y la app puedan consultarla y aplicar cambios de configuración, siempre a pedido de una persona con permiso.

## Qué hace y qué no

- **Abre una conexión hacia Idomo.** No abre puertos en tu red.
- **Solo hace lo que está en su lista:** consultar el estado de la casa, poner un equipo o una de sus luces en un ambiente (como "Área" en los ajustes de cada entidad), cambiarle el nombre a un equipo, a una tecla o a un ambiente, crear un ambiente, ocultar entidades, deshabilitar un dispositivo repetido, deshacer esos cambios, prender y apagar lo que la app permite, correr las escenas Me voy, Buenas noches y Peli de Idomo y las escenas que arme tu familia, elegir qué equipos entran en cada una, y abrir el video en vivo de una cámara para quien tenga permiso.
- **Los nombres quedan en Home Assistant.** Cambiar un nombre o un ambiente nunca cambia el identificador de una entidad, así que tus automatizaciones siguen andando.
- **Mientras alguien tiene la app abierta**, le avisa cada cambio de la casa apenas pasa (una luz prendida desde la pared, una puerta que se abre). Manda lo mismo que la consulta del estado, nada más, y deja de mandar cuando nadie mira.
- **Las escenas son scripts de Home Assistant.** Las que arma tu familia desde la app se guardan como `script.idomo_propia_…`, con el mismo editor de scripts de Home Assistant, y qué entra en Me voy, Buenas noches y Peli se guarda como etiquetas en cada entidad. Corren dentro de la casa, con o sin internet, y las podés ver en **Ajustes → Automatizaciones y escenas**.
- **Una escena puede correr sola**, a una hora o al amanecer o atardecer, si tu familia lo elige en la app. Eso se guarda como una automatización de Home Assistant por escena ("… · cuándo corre"), que podés ver, pausar o borrar en **Ajustes → Automatizaciones y escenas**. Cuando corre sola, el add-on le avisa a Idomo cómo quedó, para que se vea en la app. Una escena que cierra o arma algo nunca corre sola: solo cuando alguien la toca.
- **Lo de seguridad, con cuidado:** no oculta ni deshabilita cerraduras, alarma, cámaras ni sirenas; a esos equipos solo les puede cambiar el nombre o el ambiente. Una escena puede **cerrar** una cerradura o el portón y **armar** la alarma, solo si el titular lo eligió, y después verifica que haya quedado así. **Nunca abre ni desarma nada.**
- **No saca de la casa** video, audio, imágenes, ubicaciones ni coordenadas. Para ver una cámara en vivo, solo pasa la negociación de la conexión: el video va directo de la cámara, o del servicio de la marca, al teléfono.
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
