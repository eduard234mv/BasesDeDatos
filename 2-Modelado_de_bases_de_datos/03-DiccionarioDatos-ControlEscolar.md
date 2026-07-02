# Diccionario de Datos de base de datos Productos

1.Informacion General

| Elemnto | Valor |
| :--- | :--- |
| Proyecto | Sistema de control de Productos |
| vercion | 1.0 |
| Fecha | Junio 2026 |
| Elaboro | Juan Antonio Hernandez Martinez |
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