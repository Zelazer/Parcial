# Respuestas del parcial

1. ¿Qué error encontraste en la validación de `stock`?
A la hora de definir el campo, el ge (valor mayor o igual a) estaba en 0, lo que permitia que se crearan juegos con 0 en stock, se cambio a 1 para evitar este error

2. ¿Qué hacía que un juego pareciera creado pero no quedara persistido?
Porque despues de crear el juego hay que hacerle commit a la session para que los registros nuevos queden guardados en la base de datos

3. ¿Qué problema tenía el endpoint que lista juegos?
Al ser una lista de todos los juegos, entonces en el response_model deberia especificarse que se espera una lista de juegos con list[GameResponse]

4. ¿Cómo solucionaste la consulta de un ID inexistente?
Se valido el caso en el que session.get no trajera ningun dato, si esto sucedia entonces se enviaba un HTTPException con status code de 404, y en detalle se le agrega el mensaje de "Game not found"

5. ¿Por qué DELETE podía responder correctamente y aun así no eliminar el registro de SQLite?
Porque despues no se le hacia commit a la session para que realmente se eliminara el registro en la base de datos
