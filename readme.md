# API REST y API GRAPHQL juntos

* #### Continuando con el trabajo sobre el servidor del último entregable, cambiar los métodos GET y POST de la API REST de ingreso de productos, por los query y mutations necesarios para implementarlos utilizando la interface GraphQL en la ruta /graphql. Los métodos PUT y DELETE quedarán bajo el control de la API REST y seguirán siendo funcionales, comprobando así, que en el proyecto puedan convivir escenarios API REST con API GraphQL.
* #### Realizar el ingreso de un producto y el listado total a través de la interface 'graphiql' y verificar los datos recibidos desde el backend.


Cree 2 funciones en GraphQL, una para listar los productos y otra para crear uno nuevo.

Las funciones de PUT y DEL siguen estando a cargo de la API.

<hr />

### Aplicación
http://localhost:8080/<br /><br />


Desde aqui se pueden crear, eliminar, actualizar y listar los productos.<br />
<br />
<hr />
<br />

### Interface GraphiQL
http://localhost:8080/graphql

Desde aqui se pueden ejecutar las funciones que defino en el root de GraphQL.
<br /><br />


Las mismas son:

```viewProductos```<br />
Que mmuestra el listado<br /><br />
```guardarProducto```<br />
Que crea uno nuevo.

```
query viewProductos {
  productos {
    ...articulosFields
  }
}

mutation addProducto {
  guardarProducto(title: "Manzanas", price: 95, thumbnail: "14") {
    ...articulosFields
  }
}

fragment articulosFields on Producto {
  title
  price
  thumbnail
}

```

Luego se puede desde la plataforma eliminar o actualizar productos y ver los cambios en GraphQL nuevamente.