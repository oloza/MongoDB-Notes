### mongo

DB-> collections -> documents
- las colecciones son las "tablas"
- los documentos son los objetos "registros" 
comandos:
* mongod ->para iniciar la BD
* mongo  ->para shell comandos
	* mongo shell->es un interprete de JS

comandos Shell mongo
* cls -> limpiar pantalla
* db ->muestra la base actual
* show dbs -> muestra todas las base de datos

las base de Mongo 
admin   0.000GB
config  0.000GB
local   0.000GB

* para crear una base de datos nueva
`>` use webstore
* insert data
`>` db.products.insert({"name":"laptop"})

* Eliminar DB
`>` db.dropDatabase()  -> elimina la base actual

`>` show collections   ->muestra las colecciones(tablas)

* Crear una coleccion

`>` db.createCollection("nomCollection")

* Eliminar una coleccion

`>` db.nomCollection.drop() 

* puede crear una collection insertando un dato

`>`  db.nameCollection.insert({"nombre":"olr"})

* en Mongo los objetos JSON son transformados a BSON
* para buscar
`>` db.nameCollection.find().pretty()

* despues del criterio se puede colocar llave:valor  1 mostrar, 0 no mostrar
`>` db.products.find({"tags":"computers"},{"name":1,"description":1, "_id":0})


* para la cantidad
`>` db.products.count()

* para una busqueda mas avanzada
`>` db.products.find().forEach(product => print("prod name:"+product.name))

* para actualizar, actualiza todo lo que está en keyboard incluso keyboard
`>` db.products.update({"name":"keyboard"},{"price":99.99})

* para insertar un nuevo campo
`>` db.products.update({"name":"laptop"},{$set:{"description":"lg grama laptop"}})

* insertar un nuevo registro con update  upsert
`>` db.products.update({"name":"desktop"},{$set:{"description":"gaming desktop"}},{upsert:true})

* incrementar en un campo
`>` db.products.update({"name":"keyboard"},{$inc:{"price":0.01}}) 

* modificar la clave del objeto, propiedad
`>` db.products.update ({"name":"laptop"},{$rename:{"name":0.01}}) 

