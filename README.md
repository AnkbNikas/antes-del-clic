# Antes del Clic

Verificador de enlaces y códigos QR que revela el destino real de una URL y detecta señales de phishing **sin visitarla nunca** y **sin enviar nada a ningún servidor**. Todo el análisis ocurre en el propio navegador.

🔗 **Pruébala aquí:** https://ankbnikas.github.io/antes-del-clic/

## Por qué existe

España concentra una parte muy alta de las estafas de código QR (quishing) a nivel mundial. El mecanismo habitual se repite: una pegatina falsa sobre el QR real de un parquímetro, una carta de restaurante o un aviso de paquetería, que lleva a una web que imita a una marca conocida (DGT, Correos, un banco...).

Esta herramienta analiza ese tipo de enlaces antes de abrirlos, sin depender de ninguna API de pago ni enviar la URL a terceros.

## Qué detecta

**Suplantación de marcas conocidas** (administración, bancos, mensajería, energía, aerolíneas, grandes plataformas):
- El dominio oficial incrustado dentro de otro dominio distinto
- Imitaciones casi idénticas por distancia de edición (ej. "corrreos" en vez de "correos")
- Mismo nombre pero extensión de dominio equivocada

**Trucos técnicos de URL:**
- Direcciones IP en lugar de un dominio
- Usuario/contraseña antes de una «@» para camuflar el dominio real
- Codificación punycode y homoglifos (letras de otro alfabeto que se ven casi iguales a las latinas)
- Caracteres Unicode invisibles o de cambio de dirección de escritura
- Codificación porcentual doble
- Parámetros de redirección hacia otro dominio

**Otras señales:**
- Extensiones de dominio muy baratas y habituales en phishing, y extensiones de país inusuales para servicios españoles
- Exceso de subniveles o guiones en el dominio
- Palabras de urgencia típicas de mensajes de phishing
- Ausencia de HTTPS
- Discrepancia entre el texto visible de un enlace y su destino real

Cada señal detectada suma puntos a una puntuación de riesgo orientativa (bajo / medio / alto), con el motivo exacto de cada aviso.

## Cómo usarla

1. Abre https://ankbnikas.github.io/antes-del-clic/
2. Pega una URL, un enlace completo (`<a href="...">`), el texto copiado de un email, o haz una foto de un código QR desde el móvil
3. Pulsa «Analizar enlace»
4. Revisa el destino real, la puntuación de riesgo y los motivos detectados

Si pegas varios enlaces a la vez, la herramienta los analiza todos y muestra primero el de mayor riesgo, con una lista para consultar el resto.

## Privacidad

Todo el análisis se ejecuta en el navegador de quien lo usa. Ninguna URL, imagen de QR o dato introducido sale del dispositivo ni se envía a este repositorio, a un servidor propio, ni a ninguna API de terceros — tampoco la lectura del QR, que se hace con una librería que corre en local.

## Ejecutarla en local

Es un único archivo HTML, sin instalación ni servidor:

```bash
git clone https://github.com/AnkbNikas/antes-del-clic.git
cd antes-del-clic
# abre index.html directamente en el navegador
```

## Limitaciones

Es una herramienta de apoyo basada en heurísticas, no un servicio de reputación de dominios ni un sustituto del criterio de quien la usa. Puede haber falsos positivos y falsos negativos. Ante la duda, no introduzcas datos personales o de pago y verifica por otro canal oficial.

## Tecnología

HTML, CSS y JavaScript sin frameworks ni proceso de build. Lectura de QR mediante [jsQR](https://github.com/cozmo/jsQR).

## Autora

[Nieves Casquero](https://www.linkedin.com/in/nieves-kaskero/) — Perito Judicial Informático (Colegiada AEPEJU)

## Licencia

MIT — ver [LICENSE](LICENSE)
