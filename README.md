# Blockchain Descentralizada con PYTHON

Este proyecto presenta una implementación simple de una blockchain descentralizada en Python utilizando la biblioteca Flask. La estructura del proyecto se divide en varios archivos, cada uno con su funcionalidad específica.

### Archivos Principales

1. **Block1.py:** Contiene la implementación de la blockchain. Aquí se definen los bloques, la prueba de trabajo (proof of work) y las funciones relacionadas con la cadena de bloques.

2. **cripto.py:** Este archivo representa la implementación básica de una criptomoneda. Define cómo se crean y gestionan las transacciones, y cómo se lleva el registro de las monedas de los usuarios.

3. **cript_nodo_5001.py:** Primer nodo de la red. Este archivo establece un nodo que puede minar bloques y conectarse con otros nodos para descentralizar la red.

4. **cript_nodo_5002.py:** Segundo nodo de la red.

5. **cript_nodo_5003.py:** Tercer nodo de la red.

## Conexión entre Nodos

Cada nodo se comunica con otros mediante el uso de archivos JSON. Se ha implementado un mecanismo simple para que los nodos se conecten entre sí y formen una red descentralizada.

## Configuración en Postman

Para conectar los nodos, se podría utilizar Postman. En cada pestaña para los nodos 5001, 5002 y 5003, se debe realizar la siguiente configuración:

1. Ir a la sección "Body".
2. Seleccionar la opción "raw".
3. Cambiar el tipo de texto a "JSON".
4. Copiar y pegar el contenido del archivo `nodes.json` para cada nodo.

Ejemplos:

- Para el Nodo 5001:

```json
{
    "nodes": ["http://127.0.0.1:5002", "http://127.0.0.1:5003"]
}
```

- Para el Nodo 5002:

```json
{
    "nodes": ["http://127.0.0.1:5001", "http://127.0.0.1:5003"]
}
```

- Para el Nodo 5003:

```json
{
    "nodes": ["http://127.0.0.1:5002", "http://127.0.0.1:5001"]
}
```

## Conexión y Minería

Una vez que los nodos están en ejecución, se pueden realizar peticiones POST para conectar los nodos y comenzar a minar la blockchain. Ejemplos:

- Para conectar el Nodo 5001:

```http
POST http://127.0.0.1:5001/connect_node
```

- Para conectar el Nodo 5002:

```http
POST http://127.0.0.1:5002/connect_node
```

- Para conectar el Nodo 5003:

```http
POST http://127.0.0.1:5003/connect_node
```

Luego, se pueden realizar peticiones de minería para agregar bloques a la blockchain:

```http
GET http://127.0.0.1:5001/mine_block
GET http://127.0.0.1:5002/mine_block
GET http://127.0.0.1:5003/mine_block
```

¡Con esto, los nodos se conectan, minan bloques y forman una red descentralizada de blockchain!
