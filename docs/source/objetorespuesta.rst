Objeto de Respuesta
===================

El resultado de la petición será en un objeto en formato JSON (http://www.json.org)

Este objeto de respuesta seguirá la siguiente estructura:

::

	{
		“Result”:[{
				“col1”:”valor1”
			},{
				“col2”:”valor2”
			}
			...
		],
		“NumResult”:”0”,
		“Error”:{
			“Código”:”xx”,
			“Descripcion”:”Descripción del error”
		}
	}

* El elemento **Result** contendrá un array de objetos JSON con los resultados de la consulta. En caso de que no se hayan encontrado resultados, o surja algún error, el Array no contendrá ningún elemento.
* El elemento **NumResult** tendrá como valor la longitud del array contenido en el elemento **Result**.
* El elemento **Error** contiene un objeto en formato JSON con otros dos elementos, **Código y Descripción**. Estos valores podrán ser consultados en éste documento en la sección de catálogos. Si la ejecución del servicio fuera satisfactoria, el elemento **Error** estará vacío.

