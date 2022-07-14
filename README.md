# Event loop

- Javascript tiene una ejecución síncrona y secuencial, es decir, se ejecuta solo una línea de código a la vez y cuando finaliza la ejecución de una línea se ejecuta la siguiente línea, hasta que aparece una línea con alguna función asíncrona.
Event loop es quien se encarga de gestionar las ejecuciones asíncronas, las que se ejecutarán en algún momento futuro.

### Funcionamiento basico de Event loop:

- Funciona con una pila o stack (call stack) y una cola (callback queue).
- El código síncrono se pone en la pila o stack y se va ejecutando línea por línea.
- La cola (callback queue) no es más que una lista donde el primer elemento insertado, será el primer elemento en ser extraído, también conocido como sistema FIFO (first in, first out).

![e17fb4d8c34e48bdadfQS986cd355c40e4](https://user-images.githubusercontent.com/77214476/179074381-450da51c-777d-45c9-a21b-c49d7eded8df.png)

- Cuando ejecutamos código asíncrono, le estamos indicando a Event loop un evento en un punto futuro y una función a la que llamaremos Callback. Event loop pondrá esa función en la cola cuando se produzca tal evento, por ejemplo cuando hayan transcurrido 2s.
- Para que una función se ejecute en la Callback queue se deben producir dos condiciones:
Que no haya ninguna función ejecutándose en el Call stack, ni ninguna función por delante en la Callback queue.
- Cuando estas dos condiciones ocurren, Event loop tomará el callback y lo ubicara en el Call stack y se ejecutará de manera secuencial todo el código del callback.
