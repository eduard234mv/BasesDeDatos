# Diccionario de Datos de base de datos Productos

1.Informacion General

| Elemnto | Valor |
| :--- | :--- |
| Proyecto | Sistema de control de Productos |
| vercion | 1.0 |
| Fecha | Junio 2026 |
| Elaboro | JOSE EDUARDO MARCELO VEGA |
| SGBD | SQLServer |

2. Descrpcion del sistema de base de datos

- Categoria
- Producto

Permite controlar las categorias y los productos registrados dentro del sistema.

3. Catalogo de Restricciones

| codigo | Significado |
| :--- | :--- |
| Pk | Primary key |
| FK | Foreig key |
| NN | NOT NULL |
| UQ | Unique |
| AI | Auto Increment |
| CK | CHECK |
| DF | Default |

4. Diccionario de datos

**Tabla:** Categoria

**Descripcion:** _Almacena las categorias de los productos_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_categoria | INT | - | PK,IA,NN | Identificador unico de la categoria |
| nombre | VARCHAR | 100 | NN | Nombre de la categoria |

---

**Tabla:** Producto

**Descripcion:** _Almacena la informacion de los productos_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_producto | INT | - | PK,IA,NN | Identificador unico del producto |
| nombre | VARCHAR | 100 | NN | Nombre del producto |
| existencia | INT | - | NN,CK(>=0) | Cantidad disponible del producto |
| precio | DECIMAL | 10,2 | NN,CK(>0) | Precio del producto |
| id_categoria | INT | - | FK,NN | Categoria a la que pertenece |

5. Relacion del sistema

| Relacion | Cardinalidad | Descripcion |
|:----------|:---------:|----------:|
| Categoria -> Producto | 1:N | Una categoria tiene muchos productos |

6. Matriz de claves Foraneas

| Tabla | Campo FK | Referncia |
|:----------|:---------:|----------:|
| Producto | id_categoria | Categoria (id_categoria) |

7. Integridad Referencial

| regla | Decripcion |
| :--- | :--- |
| IR-01 | No se puede registrar un producto con una categoria inexistente |

8. Reglas del negocio

| codigo | Regla |
| :--- | :--- |
| RN-01 | Un producto pertenece solo a una categoria |
| RN-02 | Una categoria puede tener muchos productos |
| RN-03 | La existencia del producto no puede ser negativa |
| RN-04 | El precio del producto debe ser mayor que cero |

9. Diagrama Relacional

![solucion Eje1](productos.drawio.png)

# Diccionario de Datos de base de datos Alumnos

1.Informacion General

| Elemnto | Valor |
| :--- | :--- |
| Proyecto | Sistema de control Escolar |
| vercion | 1.0 |
| Fecha | Junio 2026 |
| Elaboro | JOSE EDUARDO MARCELO VEGA|
| SGBD | SQLServer |

2. Descrpcion del sistema de base de datos

- Alumno
- Materia
- Inscripcion

Permite controlar las materias que cursan los alumnos y las calificaciones obtenidas.

3. Catalogo de Restricciones

| codigo | Significado |
| :--- | :--- |
| Pk | Primary key |
| FK | Foreig key |
| NN | NOT NULL |
| UQ | Unique |
| AI | Auto Increment |
| CK | CHECK |
| DF | Default |

4. Diccionario de datos

**Tabla:** Alumno

**Descripcion:** _Almacena la informacion de los alumnos_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_alumno | INT | - | PK,IA,NN | Identificador unico del alumno |
| nombre | VARCHAR | 50 | NN | Nombre del alumno |
| apellido_paterno | VARCHAR | 50 | NN | Apellido paterno |
| apellido_materno | VARCHAR | 50 | NN | Apellido materno |
| semestre | INT | - | NN | Semestre que cursa |

---

**Tabla:** Materia

**Descripcion:** _Almacena la informacion de las materias_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_materia | INT | - | PK,IA,NN | Identificador unico de la materia |
| nombre | VARCHAR | 100 | NN | Nombre de la materia |
| creditos | INT | - | NN,CK(>0) | Creditos de la materia |

---

**Tabla:** Inscripcion

**Descripcion:** _Almacena las inscripciones de los alumnos_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_inscripcion | INT | - | PK,IA,NN | Identificador unico de la inscripcion |
| fecha_inscripcion | DATE | - | NN | Fecha de inscripcion |
| calificacion | DECIMAL | 4,2 | NN | Calificacion obtenida |
| id_alumno | INT | - | FK,NN | Alumno inscrito |
| id_materia | INT | - | FK,NN | Materia inscrita |

5. Relacion del sistema

| Relacion | Cardinalidad | Descripcion |
|:----------|:---------:|----------:|
| Alumno -> Inscripcion | 1:N | Un alumno puede tener muchas inscripciones |
| Materia -> Inscripcion | 1:N | Una materia puede tener muchos alumnos inscritos |

6. Matriz de claves Foraneas

| Tabla | Campo FK | Referncia |
|:----------|:---------:|----------:|
| Inscripcion | id_alumno | Alumno (id_alumno) |
| Inscripcion | id_materia | Materia (id_materia) |

7. Integridad Referencial

| regla | Decripcion |
| :--- | :--- |
| IR-01 | No se puede registrar una inscripcion para un alumno inexistente |
| IR-02 | No se puede registrar una inscripcion para una materia inexistente |

8. Reglas del negocio

| codigo | Regla |
| :--- | :--- |
| RN-01 | Un alumno puede inscribirse a muchas materias |
| RN-02 | Una materia puede tener muchos alumnos inscritos |
| RN-03 | Cada inscripcion corresponde a un solo alumno y una sola materia |
| RN-04 | La calificacion pertenece a una sola inscripcion |

9. Diagrama Relacional

![solucion Eje4](alumno.drawio.png)


# Diccionario de Datos de base de datos Ventas

1.Informacion General

| Elemnto | Valor |
| :--- | :--- |
| Proyecto | Sistema de control de Ventas |
| vercion | 1.0 |
| Fecha | Junio 2026 |
| Elaboro | JOSE EDUARDO MARCELO VEGA|
| SGBD | SQLServer |

2. Descrpcion del sistema de base de datos

- Clientes
- Pedido
- Productos
- Detalle

Permite controlar los pedidos realizados por los clientes y los productos vendidos en cada pedido.

3. Catalogo de Restricciones

| codigo | Significado |
| :--- | :--- |
| Pk | Primary key |
| FK | Foreig key |
| NN | NOT NULL |
| UQ | Unique |
| AI | Auto Increment |
| CK | CHECK |
| DF | Default |

4. Diccionario de datos

**Tabla:** Clientes

**Descripcion:** _Almacena la informacion de los clientes_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_cliente | INT | - | PK,IA,NN | Identificador unico del cliente |
| nombre_cliente | VARCHAR | 100 | NN | Nombre completo del cliente |

---

**Tabla:** Pedido

**Descripcion:** _Almacena la informacion de los pedidos_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_pedido | INT | - | PK,IA,NN | Identificador unico del pedido |
| fecha_pedido | DATE | - | NN | Fecha en que se realiza el pedido |
| costo_venta | DECIMAL | 10,2 | NN | Costo total de la venta |
| id_cliente | INT | - | FK,NN | Cliente que realiza el pedido |

---

**Tabla:** Productos

**Descripcion:** _Almacena la informacion de los productos_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_producto | INT | - | PK,IA,NN | Identificador unico del producto |
| nombre_producto | VARCHAR | 100 | NN | Nombre del producto |
| precio | DECIMAL | 10,2 | NN,CK(>0) | Precio del producto |

---

**Tabla:** Detalle

**Descripcion:** _Almacena el detalle de los productos vendidos en cada pedido_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_detalle | INT | - | PK,IA,NN | Identificador unico del detalle |
| cantidad_vendida | INT | - | NN,CK(>0) | Cantidad vendida |
| id_pedido | INT | - | FK,NN | Pedido al que pertenece |
| id_producto | INT | - | FK,NN | Producto vendido |

5. Relacion del sistema

| Relacion | Cardinalidad | Descripcion |
|:----------|:---------:|----------:|
| Clientes -> Pedido | 1:N | Un cliente puede realizar muchos pedidos |
| Pedido -> Detalle | 1:N | Un pedido puede contener muchos productos |
| Productos -> Detalle | 1:N | Un producto puede aparecer en muchos pedidos |

6. Matriz de claves Foraneas

| Tabla | Campo FK | Referncia |
|:----------|:---------:|----------:|
| Pedido | id_cliente | Clientes (id_cliente) |
| Detalle | id_pedido | Pedido (id_pedido) |
| Detalle | id_producto | Productos (id_producto) |

7. Integridad Referencial

| regla | Decripcion |
| :--- | :--- |
| IR-01 | No se puede registrar un pedido para un cliente inexistente |
| IR-02 | No se puede registrar un detalle para un pedido inexistente |
| IR-03 | No se puede registrar un detalle para un producto inexistente |

8. Reglas del negocio

| codigo | Regla |
| :--- | :--- |
| RN-01 | Un cliente puede realizar muchos pedidos |
| RN-02 | Un pedido pertenece solamente a un cliente |
| RN-03 | Un pedido puede contener uno o varios productos |
| RN-04 | Un producto puede venderse en muchos pedidos |
| RN-05 | La cantidad vendida debe ser mayor que cero |

9. Diagrama Relacional

![solucion Eje5](ventas.drawio.png)


# Diccionario de Datos de base de datos Empresa

1.Informacion General

| Elemnto | Valor |
| :--- | :--- |
| Proyecto | Sistema de control de Empresa |
| vercion | 1.0 |
| Fecha | Junio 2026 |
| Elaboro | JOSE EDUARDO MARCELO VEGA |
| SGBD | SQLServer |

2. Descrpcion del sistema de base de datos

- Employee
- Department
- Project
- Dependent

Permite controlar la informacion de los empleados, departamentos, proyectos y dependientes de la empresa.

3. Catalogo de Restricciones

| codigo | Significado |
| :--- | :--- |
| Pk | Primary key |
| FK | Foreig key |
| NN | NOT NULL |
| UQ | Unique |
| AI | Auto Increment |
| CK | CHECK |
| DF | Default |

4. Diccionario de datos

**Tabla:** Employee

**Descripcion:** _Almacena la informacion de los empleados_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| ssn | VARCHAR | 15 | PK,NN | Numero de seguro social del empleado |
| first_name | VARCHAR | 50 | NN | Nombre del empleado |
| last_name | VARCHAR | 50 | NN | Apellido del empleado |
| birthdate | DATE | - | NN | Fecha de nacimiento |
| address | VARCHAR | 150 | NN | Direccion del empleado |
| sex | CHAR | 1 | NN | Sexo del empleado |
| salary | DECIMAL | 10,2 | NN | Salario del empleado |
| department_number | INT | - | FK,NN | Departamento al que pertenece |

---

**Tabla:** Department

**Descripcion:** _Almacena la informacion de los departamentos_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| number | INT | - | PK,IA,NN | Identificador del departamento |
| name | VARCHAR | 100 | UQ,NN | Nombre del departamento |
| manager_ssn | VARCHAR | 15 | FK,NN | Gerente del departamento |
| startdate | DATE | - | NN | Fecha de inicio del gerente |

---

**Tabla:** Project

**Descripcion:** _Almacena la informacion de los proyectos_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| number | INT | - | PK,IA,NN | Identificador del proyecto |
| name | VARCHAR | 100 | NN | Nombre del proyecto |
| location | VARCHAR | 100 | NN | Ubicacion del proyecto |
| department_number | INT | - | FK,NN | Departamento que controla el proyecto |

---

**Tabla:** Dependent

**Descripcion:** _Almacena la informacion de los dependientes_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| id_dependent | INT | - | PK,IA,NN | Identificador del dependiente |
| name | VARCHAR | 100 | NN | Nombre del dependiente |
| sex | CHAR | 1 | NN | Sexo del dependiente |
| birthdate | DATE | - | NN | Fecha de nacimiento |
| relationship | VARCHAR | 50 | NN | Parentesco con el empleado |
| ssn | VARCHAR | 15 | FK,NN | Empleado al que pertenece |

---

**Tabla:** Works_On

**Descripcion:** _Almacena las horas que un empleado trabaja en un proyecto_

| Campo | tipo | Longitud | Restricciones | Descripcion |
| :--- | :--- | :--- | :--- | :--- |
| ssn | VARCHAR | 15 | PK,FK,NN | Empleado asignado |
| number | INT | PK,FK,NN | Proyecto asignado |
| hours | DECIMAL | 5,2 | NN | Horas trabajadas |

5. Relacion del sistema

| Relacion | Cardinalidad | Descripcion |
|:----------|:---------:|----------:|
| Department -> Employee | 1:N | Un departamento tiene muchos empleados |
| Employee -> Department | 1:1 | Un empleado administra un departamento |
| Department -> Project | 1:N | Un departamento controla muchos proyectos |
| Employee -> Dependent | 1:N | Un empleado puede tener varios dependientes |
| Employee -> Project | N:M | Un empleado puede trabajar en varios proyectos |
| Employee -> Employee | 1:N | Un empleado puede supervisar a otros empleados |

6. Matriz de claves Foraneas

| Tabla | Campo FK | Referncia |
|:----------|:---------:|----------:|
| Employee | department_number | Department (number) |
| Department | manager_ssn | Employee (ssn) |
| Project | department_number | Department (number) |
| Dependent | ssn | Employee (ssn) |
| Works_On | ssn | Employee (ssn) |
| Works_On | number | Project (number) |

7. Integridad Referencial

| regla | Decripcion |
| :--- | :--- |
| IR-01 | No se puede registrar un empleado con un departamento inexistente |
| IR-02 | No se puede asignar un gerente que no exista |
| IR-03 | No se puede registrar un proyecto para un departamento inexistente |
| IR-04 | No se puede registrar un dependiente para un empleado inexistente |
| IR-05 | No se puede asignar un empleado a un proyecto inexistente |

8. Reglas del negocio

| codigo | Regla |
| :--- | :--- |
| RN-01 | Un departamento puede tener muchos empleados |
| RN-02 | Un departamento puede controlar muchos proyectos |
| RN-03 | Un empleado puede tener varios dependientes |
| RN-04 | Un empleado puede trabajar en varios proyectos |
| RN-05 | Un proyecto puede tener varios empleados asignados |
| RN-06 | Cada departamento tiene un solo gerente |
| RN-07 | Un empleado puede supervisar a varios empleados |

9. Diagrama Relacional

![solucion Eje6](empresa.drawio.png)