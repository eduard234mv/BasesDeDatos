# Ejercicios Modelo Conceptual (Entidad-Relación)

## Ejercicio 1:
Un hospital registra información de sus pacientes.

> De cada paciente se almacena los siguiente:
- Identificador
- Nombre
- Fecha de nacimiento

> De cada expediente médico se debe almacenar:
- Número de expediente
- Fecha de apertura
- Tipo de sangre

> Reglas de negocio
- Cada paciente debe tener exactamente un expediente médico
- Cada expediente médico pertenenece a un único paciente
- No puede existir un expediente sin paciente
- No puede existir un paciente sin expediente

### Diagrama del ejercicio 1
![Solución ejemplo 1](../img/ejercicio1.png)


## Ejercicio 2:
Una universidad administra profesores y cursos

> De cada profesor se almacena:
- Numero de Profesor
- nombre
- especialidad

> De cada curso se almacena 
- numero de curso
- nombre del curso
- créditos

> Reglas del negocio:<br>
1. Un profesor puede impartir varios cursos
2. Un curso solamente puede ser impartido 
por un profesor
3. Puede existir un profesor que actualmente no imparta cursos
4. Todo cursso debe estar asignado a un profesor 

> Lo que se debe realizar:
- Identificar y Dibujar las Entidades
- Identificar y Dibujar la relación<br>
**IMPARTE**
- Determinar la razón de cardinalidad
- Determinar la participación 

### Diagrama del ejercicio 2
![Diagrama 2](../img/ejercicio2.png)

### Solucion del Ejercicio 


## Ejercicio 3:
Una escuela administra alumnos y materias 

> De cada alumno se almacena:
- Matricula
- Nombre
- Semestre  

> De cada materia se almacena:
- Clave de la materia
- Nombre de la materia
- Créditos

> Reglas del negocio:
1. Un alumno puede inscribirse en varias materias
2. Una materia puede tener muchos alumnos inscritos
3. Puede existir una materia sin alumnos inscritos 
4. Todo alumno debe estar inscrito en al menos una materia
5. De cada inscripción se desea almacenar:
    - Fecha de inscripción
    - Calificación final

Nota: La relación se debe llamar **INSCRIBE**

### Diagrama del ejercicio 3
![Diagrama 3](../img/ejercicio3.png)


## Ejercicio 4
Una empresa de dedica a la venta de productos al por mayor, y necesita registrar lo siguiente:

> Identificar del cliente:
- Nombre del cliente, el cual es una persona moral

> De los pedidos de ventas:
- Numero de pedido
- Fecha del pedido 

> De los productos:
- Numero del producto
- Nombre del producto
- Precio del producto

> Reglas del negocio 
1. Un cliente puede realizar muchos pedidos
2. Cada pedido pertenece a un cliente
3. Un pedido contiene varios  productos
4. Un producto puede aparecer en muchos pedidos 
5. Un pedido debe contener al menos un producto 
6. Un producto puede no haber sido vendido
7. El detalle del pedido no existe sin pedido
8. El detalle del pedido no existe sin producto
9. El detalle del pedido alamacena cantidad vendida y precio de venta

### Diagrama del ejercicio 4
![Diagrama 4](../img/ejercicio4.png)

## Ejercicio 5
### Diagrama del ejercicio 5
![Diagrama 5](../img/ejercicio5.png)

## Ejercicio 6
### Diagrama del ejercicio 6
![Diagrama 6]()