Microsoft Windows [Versión 10.0.22000.675]
(c) Microsoft Corporation. Todos los derechos reservados.

C:\Users\emiit>mongo
MongoDB shell version v5.0.8
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("83228098-07b5-4bfb-beaa-18c0a0bbdc14") }
MongoDB server version: 5.0.8
================
Warning: the "mongo" shell has been superseded by "mongosh",
which delivers improved usability and compatibility.The "mongo" shell has been deprecated and will be removed in
an upcoming release.
For installation instructions, see
https://docs.mongodb.com/mongodb-shell/install/
================
Welcome to the MongoDB shell.
For interactive help, type "help".
For more comprehensive documentation, see
        https://docs.mongodb.com/
Questions? Try the MongoDB Developer Community Forums
        https://community.mongodb.com
---
The server generated these startup warnings when booting:
        2022-05-18T19:35:43.642-03:00: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
        2022-05-18T19:35:43.643-03:00: This server is bound to localhost. Remote systems will be unable to connect to this server. Start the server with --bind_ip <address> to specify which IP addresses it should serve responses from, or with --bind_ip_all to bind to all interfaces. If this behavior is desired, start the server with --bind_ip 127.0.0.1 to disable this warning
---
---
        Enable MongoDB's free cloud-based monitoring service, which will then receive and display
        metrics about your deployment (disk utilization, CPU, operation statistics, etc).

        The monitoring data will be available on a MongoDB website with a unique URL accessible to you
        and anyone you share the URL with. MongoDB may use this information to make product
        improvements and to suggest MongoDB products and deployment options to you.

        To enable free monitoring, run the following command: db.enableFreeMonitoring()
        To permanently disable this reminder, run the following command: db.disableFreeMonitoring()
---

LISTANDO BASES DE DATOS POR DEFECT

> show dbs
admin   0.000GB
config  0.000GB
local   0.000GB

CREANDO DB ECOMMERCE 

> use ecommerce
switched to db ecommerce

CREANDO LAS COLECCIONES PRODUCTOS Y MENSAJES

> db.createCollection("productos")
{ "ok" : 1 }
> db.createCollection("messages")
{ "ok" : 1 }

INSERTANDO LOS DOCS DE PRODUCTOS Y MENSAJES

> db.productos.insertMany([
...   { name: 'product1', description: '', code: 100, photo: '', price: 100, stock: 20 },
...   { name: 'product2', description: '', code: 101, photo: '', price: 150, stock: 20 },
...   { name: 'product3', description: '', code: 102, photo: '', price: 300, stock: 20 },
...   { name: 'product4', description: '', code: 103, photo: '', price: 250, stock: 20 },
...   { name: 'product5', description: '', code: 104, photo: '', price: 180, stock: 20 },
...   { name: 'product6', description: '', code: 105, photo: '', price: 4500, stock: 20 },
...   { name: 'product7', description: '', code: 106, photo: '', price: 1500, stock: 20 },
...   { name: 'product8', description: '', code: 107, photo: '', price: 2000, stock: 20 },
...   { name: 'product9', description: '', code: 108, photo: '', price: 3000, stock: 20 },
...   { name: 'product10', description: '', code: 109, photo: '', price: 5000, stock: 20 }
... ])
{
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("628582b67405150fb374954b"),
                ObjectId("628582b67405150fb374954c"),
                ObjectId("628582b67405150fb374954d"),
                ObjectId("628582b67405150fb374954e"),
                ObjectId("628582b67405150fb374954f"),
                ObjectId("628582b67405150fb3749550"),
                ObjectId("628582b67405150fb3749551"),
                ObjectId("628582b67405150fb3749552"),
                ObjectId("628582b67405150fb3749553"),
                ObjectId("628582b67405150fb3749554")
        ]
}
> db.messages.insertMany([
...   {author:'pamela', text: 'hola'},
... {author:'pablo', text: 'hola'},
... {author:'lola', text: 'hola'},
... {author:'dorys', text: 'hola'},
... {author:'rocio', text: 'hola'},
... {author:'miguel', text: 'hola'},
... {author:'juan', text: 'hola'},
... {author:'pedro', text: 'hola'},
... {author:'clara', text: 'hola'},
... {author:'mariano', text: 'hola'}
... ])
{
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("628583117405150fb3749555"),
                ObjectId("628583117405150fb3749556"),
                ObjectId("628583117405150fb3749557"),
                ObjectId("628583117405150fb3749558"),
                ObjectId("628583117405150fb3749559"),
                ObjectId("628583117405150fb374955a"),
                ObjectId("628583117405150fb374955b"),
                ObjectId("628583117405150fb374955c"),
                ObjectId("628583117405150fb374955d"),
                ObjectId("628583117405150fb374955e")
        ]
}

LISTANDO DBS CREADA CORRECTAMENTE ECOMMERCE:

> show dbs
admin      0.000GB
config     0.000GB
ecommerce  0.000GB
local      0.000GB

LISTANDO LOS PRODUCTOS:

> db.productos.find()
{ "_id" : ObjectId("628582b67405150fb374954b"), "name" : "product1", "description" : "", "code" : 100, "photo" : "", "price" : 100, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954c"), "name" : "product2", "description" : "", "code" : 101, "photo" : "", "price" : 150, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954d"), "name" : "product3", "description" : "", "code" : 102, "photo" : "", "price" : 300, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954e"), "name" : "product4", "description" : "", "code" : 103, "photo" : "", "price" : 250, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954f"), "name" : "product5", "description" : "", "code" : 104, "photo" : "", "price" : 180, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749550"), "name" : "product6", "description" : "", "code" : 105, "photo" : "", "price" : 4500, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749551"), "name" : "product7", "description" : "", "code" : 106, "photo" : "", "price" : 1500, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749552"), "name" : "product8", "description" : "", "code" : 107, "photo" : "", "price" : 2000, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749553"), "name" : "product9", "description" : "", "code" : 108, "photo" : "", "price" : 3000, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749554"), "name" : "product10", "description" : "", "code" : 109, "photo" : "", "price" : 5000, "stock" : 20 }

LISTANDO LOS MENSAJES:

> db.messages.find()
{ "_id" : ObjectId("628583117405150fb3749555"), "author" : "pamela", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb3749556"), "author" : "pablo", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb3749557"), "author" : "lola", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb3749558"), "author" : "dorys", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb3749559"), "author" : "rocio", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb374955a"), "author" : "miguel", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb374955b"), "author" : "juan", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb374955c"), "author" : "pedro", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb374955d"), "author" : "clara", "text" : "hola" }
{ "_id" : ObjectId("628583117405150fb374955e"), "author" : "mariano", "text" : "hola" }
> db.productos.insertOne([{ name: 'product1', description: '', code: 100, photo: '', price: 100, stock: 20 },
...
... ]}

CANTIDAD DE PRODUCTOS ALMACENADOS EN PRODUCTOS:

 > db.productos.find().length()

CANTIDAD DE PRODUCTOS ALMACENADOS EN MENSAJES:

> db.messages.find().length()

CRUD EN LA COLECCION:
	
	AGREGO OTRO PRODUCTO EN LA COLECCION DE PRODUCTOS:

> db.productos.insertOne({name: 'producto11', description: '',code:200,photo:'', price: 200, stock:20})
{
        "acknowledged" : true,
        "insertedId" : ObjectId("628585a47405150fb374955f")
}

	REVISO QUE SE HAYA CREADO Y APAREZCA EN LA COLECCION:

> db.productos.find()
{ "_id" : ObjectId("628582b67405150fb374954b"), "name" : "product1", "description" : "", "code" : 100, "photo" : "", "price" : 100, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954c"), "name" : "product2", "description" : "", "code" : 101, "photo" : "", "price" : 150, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954d"), "name" : "product3", "description" : "", "code" : 102, "photo" : "", "price" : 300, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954e"), "name" : "product4", "description" : "", "code" : 103, "photo" : "", "price" : 250, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954f"), "name" : "product5", "description" : "", "code" : 104, "photo" : "", "price" : 180, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749550"), "name" : "product6", "description" : "", "code" : 105, "photo" : "", "price" : 4500, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749551"), "name" : "product7", "description" : "", "code" : 106, "photo" : "", "price" : 1500, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749552"), "name" : "product8", "description" : "", "code" : 107, "photo" : "", "price" : 2000, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749553"), "name" : "product9", "description" : "", "code" : 108, "photo" : "", "price" : 3000, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749554"), "name" : "product10", "description" : "", "code" : 109, "photo" : "", "price" : 5000, "stock" : 20 }
{ "_id" : ObjectId("628585a47405150fb374955f"), "name" : "producto11", "description" : "", "code" : 200, "photo" : "", "price" : 200, "stock" : 20 }


PRODUCTOS CON PRECIO MENOR A 1000:

> db.productos.find({"price": {$lt: 1000}})
{ "_id" : ObjectId("628582b67405150fb374954b"), "name" : "product1", "description" : "", "code" : 100, "photo" : "", "price" : 100, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954c"), "name" : "product2", "description" : "", "code" : 101, "photo" : "", "price" : 150, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954d"), "name" : "product3", "description" : "", "code" : 102, "photo" : "", "price" : 300, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954e"), "name" : "product4", "description" : "", "code" : 103, "photo" : "", "price" : 250, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb374954f"), "name" : "product5", "description" : "", "code" : 104, "photo" : "", "price" : 180, "stock" : 20 }
{ "_id" : ObjectId("628585a47405150fb374955f"), "name" : "producto11", "description" : "", "code" : 200, "photo" : "", "price" : 200, "stock" : 20 }

PRODUCTOS ENTRE 1000 Y 30000:

> db.productos.find({"price": {$gte: 1000, $lte: 3000}})
{ "_id" : ObjectId("628582b67405150fb3749551"), "name" : "product7", "description" : "", "code" : 106, "photo" : "", "price" : 1500, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749552"), "name" : "product8", "description" : "", "code" : 107, "photo" : "", "price" : 2000, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749553"), "name" : "product9", "description" : "", "code" : 108, "photo" : "", "price" : 3000, "stock" : 20 }

PRODUCTOS MAYORES A 3000:

> db.productos.find({"price": {$gt: 3000}})
{ "_id" : ObjectId("628582b67405150fb3749550"), "name" : "product6", "description" : "", "code" : 105, "photo" : "", "price" : 4500, "stock" : 20 }
{ "_id" : ObjectId("628582b67405150fb3749554"), "name" : "product10", "description" : "", "code" : 109, "photo" : "", "price" : 5000, "stock" : 20 }

TRAER SOLO EL NOMBRE DEL 3ER PRODUCTO MAS BARATO. ES DE 180 PESOS CREO:

> db.productos.find({},{"name":1, "_id":0}).sort({"price": 1}).skip(2).limit(1)
{ "name" : "product5" }

ACTUALIZAR SOBRE TODOS, AGREGANDO STOCK DE 100 A TODOS ELLOS:

> db.productos.updateMany({}, {$set: {stock: 100}})
{ "acknowledged" : true, "matchedCount" : 11, "modifiedCount" : 11 }

REVISANDO QUE ESTE BIEN ACTUALIZADO:

> db.productos.find()
{ "_id" : ObjectId("628582b67405150fb374954b"), "name" : "product1", "description" : "", "code" : 100, "photo" : "", "price" : 100, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb374954c"), "name" : "product2", "description" : "", "code" : 101, "photo" : "", "price" : 150, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb374954d"), "name" : "product3", "description" : "", "code" : 102, "photo" : "", "price" : 300, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb374954e"), "name" : "product4", "description" : "", "code" : 103, "photo" : "", "price" : 250, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb374954f"), "name" : "product5", "description" : "", "code" : 104, "photo" : "", "price" : 180, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749550"), "name" : "product6", "description" : "", "code" : 105, "photo" : "", "price" : 4500, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749551"), "name" : "product7", "description" : "", "code" : 106, "photo" : "", "price" : 1500, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749552"), "name" : "product8", "description" : "", "code" : 107, "photo" : "", "price" : 2000, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749553"), "name" : "product9", "description" : "", "code" : 108, "photo" : "", "price" : 3000, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749554"), "name" : "product10", "description" : "", "code" : 109, "photo" : "", "price" : 5000, "stock" : 100 }
{ "_id" : ObjectId("628585a47405150fb374955f"), "name" : "producto11", "description" : "", "code" : 200, "photo" : "", "price" : 200, "stock" : 100 }

CAMBIANDO STOCK DE PRODUCTOS CON PRECIOS MAYORES A 4000 PESOS:

> db.productos.updateMany({"price": {$gt: 4000}}, {$set: {stock: 0}})
{ "acknowledged" : true, "matchedCount" : 2, "modifiedCount" : 2 }

REVISANDO:

> db.productos.find()
{ "_id" : ObjectId("628582b67405150fb374954b"), "name" : "product1", "description" : "", "code" : 100, "photo" : "", "price" : 100, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb374954c"), "name" : "product2", "description" : "", "code" : 101, "photo" : "", "price" : 150, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb374954d"), "name" : "product3", "description" : "", "code" : 102, "photo" : "", "price" : 300, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb374954e"), "name" : "product4", "description" : "", "code" : 103, "photo" : "", "price" : 250, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb374954f"), "name" : "product5", "description" : "", "code" : 104, "photo" : "", "price" : 180, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749550"), "name" : "product6", "description" : "", "code" : 105, "photo" : "", "price" : 4500, "stock" : 0 }
{ "_id" : ObjectId("628582b67405150fb3749551"), "name" : "product7", "description" : "", "code" : 106, "photo" : "", "price" : 1500, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749552"), "name" : "product8", "description" : "", "code" : 107, "photo" : "", "price" : 2000, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749553"), "name" : "product9", "description" : "", "code" : 108, "photo" : "", "price" : 3000, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749554"), "name" : "product10", "description" : "", "code" : 109, "photo" : "", "price" : 5000, "stock" : 0 }
{ "_id" : ObjectId("628585a47405150fb374955f"), "name" : "producto11", "description" : "", "code" : 200, "photo" : "", "price" : 200, "stock" : 100 }

BORRANDO TODOS LOS PRODUCTOS CON PRECIO MENOR A 1000:

> db.productos.deleteMany({"price": {$lt: 1000}})
{ "acknowledged" : true, "deletedCount" : 6 }

REVISANDO:

> db.productos.find()
{ "_id" : ObjectId("628582b67405150fb3749550"), "name" : "product6", "description" : "", "code" : 105, "photo" : "", "price" : 4500, "stock" : 0 }
{ "_id" : ObjectId("628582b67405150fb3749551"), "name" : "product7", "description" : "", "code" : 106, "photo" : "", "price" : 1500, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749552"), "name" : "product8", "description" : "", "code" : 107, "photo" : "", "price" : 2000, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749553"), "name" : "product9", "description" : "", "code" : 108, "photo" : "", "price" : 3000, "stock" : 100 }
{ "_id" : ObjectId("628582b67405150fb3749554"), "name" : "product10", "description" : "", "code" : 109, "photo" : "", "price" : 5000, "stock" : 0 }

CREANDO UN USUARIO COMO NOS INFORMA LA CONSIGNA, NOMBRE PEPE:

> use admin
switched to db admin
> db.createUser({user: "pepe", pwd: "asd456", roles: [ {role: "read", db: "ecommerce"} ]})
Successfully added user: {
        "user" : "pepe",
        "roles" : [
                {
                        "role" : "read",
                        "db" : "ecommerce"
                }
        ]
}

COMPROBANDO QUE NO PUEDE MODIFICAR:

> db.productos.insert({title:"productoPruebaUserPepe", price: 123456, thumbnail:"pruebauser.png"})
WriteCommandError({
        "ok" : 0,
        "errmsg" : "not authorized on ecommerce to execute command { insert: \"productos\", ordered: true, lsid: { id: UUID(\"41295edd-2cd3-4755-a129-2682af5dffd4\") }, $db: \"ecommerce\" }",
        "code" : 13,
        "codeName" : "Unauthorized"
})
>
