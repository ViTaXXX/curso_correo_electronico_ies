# Caso 2: Envío de correo desde usuarios del servidor a correos de internet

## Desde el aula

En el caso de la configuración de nuestra red del instituto, sólo puede enviar correo el servidor de correo de `satelite.gonzalonazareno.org`. Por lo tanto tenemos que configurar nuestro servidor para que utilice este servidor como relay para enviar nuestros correos, para que sea más sencillo hemos creado un alias llamado `mail.gonzalonazareno.org`. Para ello, modificamos la siguiente directiva en el fichero de configuración:

	relayhost = mail.gonzalonazareno.org


## Desde tu servidor VPS

¿Qué necesitamos para que desde nuestro VPS podamos mandar correos al exterior?:

* Con la configuración básica del servidor, seríamos capaces de enviar el correo (no necesitamos un relay).
* Quizás no sea necesario para el envío de correos, pero estaría muy bien que ya tengamos configurado en nuestro DNS el registro MX apuntando a nuestra máquina.
* Necesitamos implementar varias técnicas para asegurar que el servidor de correo al que mandamos nuestro correo confíe en nuestro servidor de correos.
* Necesitamos que nuestra IP esté "limpia", es posible que si mandamos el correo desde un servidor que utilice una ip dinámica, seguramente gmail /hotmail/yahoo lo rechaza, por estar en una lista de bloqueo, al intentar enviar un correo nos salen registro de este tipo:
 un correo nos salen registro de este tipo:

	![postfix6](img/postfix4.jpg)

En el siguiente apartado profundizaremos en los mecanismos necesarios para asegurar el envío de nuestro correos.
