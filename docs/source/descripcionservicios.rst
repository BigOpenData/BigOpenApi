Descripción de los servicios
=============================

A continuación se describen los servicios implementados

+------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| mostrarRecursos                                                                                                                                         |
+========================+================================================================================================================================+
| Descripción            || Servicio que devuelve una lista con los nombres de los recursos disponibles.                                                  |
+------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| Tipo servicio          || REST                                                                                                                          |
+------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| Parámetros             |                                                                                                                                |
+------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| Resultado              || Devuelve un array con los diferentes recursos disponibles.                                                                    |
|                        ||                                                                                                                               |
|                        || **Formato**:                                                                                                                  |
|                        ||                                                                                                                               |
|                        |                                                                                                                                |
|                        | * **tab_name** :  Nombre del recurso                                                                                           |
+------------------------+--------------------------------------------------------------------------------------------------------------------------------+
| Ejemplo de llamada     | `http://<servidor>:9090/BigOpenApi/mostrarRecursos`                                                                            |
+------------------------+--------------------------------------------------------------------------------------------------------------------------------+
.. _http://<servidor>:9090/BigOpenApi/mostrarRecursos: http://<servidor>:9090/BigOpenApi/mostrarRecursos                                                                                                                  
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
| describirRecursos                                                                                                                                                      |
+========================+===============================================================================================================================================+
| Descripción            || Servicio que devuelve la estructura del recurso solicitado.                                                                                  |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
| Tipo servicio          || REST                                                                                                                                         |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
| Parámetros             ||                                                                                                                                              |
|                        |                                                                                                                                               |
|                        | * **dsTabla**: Nombre del recurso                                                                                                             |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
| Resultado              || Devuelve un array con los diferentes recursos disponibles.                                                                                   |
|                        ||                                                                                                                                              |
|                        || **Formato**:                                                                                                                                 |
|                        ||                                                                                                                                              |
|                        |                                                                                                                                               |
|                        | * **tab_name** :  Nombre del recurso                                                                                                          |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
| Ejemplo de llamada     | `http://<servidor>:9090/BigOpenApi/describirRecurso?dsTabla=<nombreRecurso>`_                                                                 |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+

.. _http://<servidor>:9090/BigOpenApi/describirRecurso?dsTabla=<nombreRecurso>: http://<servidor>:9090/BigOpenApi/describirRecurso?dsTabla=<nombreRecurso>

+------------------------+--------------------------------------------------------------------------------------------------------------------+
| probarRecursos                                                                                                                              |
+========================+====================================================================================================================+
| Descripción            || Servicio que devuelve 100 elementos del recurso solicitado de forma rápida,                                       |
|                        || para poder comprobar el tipo de información contenida en el recurso.                                              |
|                        ||                                                                                                                   |
|                        || Si la ejecución es correcta, la respuesta se realizará mediante un **archivo de**                                 |
|                        || **texto** plano con el objeto Resultado en formato JSON. En cambio, en caso                                       |
|                        || de error se devolverá, **en forma de mensaje**, el objeto JSON de respuesta                                       |
|                        || informando del error.                                                                                             |                                         
+------------------------+--------------------------------------------------------------------------------------------------------------------+
| Tipo servicio          || Servlet                                                                                                           |
+------------------------+--------------------------------------------------------------------------------------------------------------------+
| Parámetros             ||                                                                                                                   |
|                        |                                                                                                                    |
|                        | * **dsTabla**: Nombre del recurso                                                                                  |
+------------------------+--------------------------------------------------------------------------------------------------------------------+
| Resultado              || Array en formato JSON con los registros contenidos en el recurso.                                                 |
|                        ||                                                                                                                   |
|                        || **Formato**:                                                                                                      |
|                        ||                                                                                                                   |
|                        |                                                                                                                    |
|                        | * **claveRecurso** :  valor                                                                                        |
+------------------------+--------------------------------------------------------------------------------------------------------------------+
| Ejemplo de llamada     | `http://<servidor>:9090/BigOpenApi/probarRecurso?dsTabla=<nombreRecurso>`_                                         |
+------------------------+--------------------------------------------------------------------------------------------------------------------+

.. _http://<servidor>:9090/BigOpenApi/probarRecurso?dsTabla=<nombreRecurso>: http://<servidor>:9090/BigOpenApi/probarRecurso?dsTabla=<nombreRecurso>

+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| contarResultados                                                                                                                                                                                                |
+========================+========================================================================================================================================================================================+
| Descripción            || Devuelve el número de registros coincidentes para los campos y expresiones                                                                                                            |
|                        || regulares enviadas como parámetros para un recurso. Este servicio permite                                                                                                             |
|                        || prever la cantidad de información que sería devuelta por el método                                                                                                                    |
|                        || **filtrarResultados** para un mismo filtro.                                                                                                                                           |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Tipo servicio          || REST                                                                                                                                                                                  |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Parámetros             || Permite enviar una lista de campos y expresiones regulares a cumplir. Los                                                                                                             |
|                        || campos y expresiones regulares se validarán en orden, es decir, el primer                                                                                                             | 
|                        || parámetro campo se validará con la primera expresión regular enviada. Por                                                                                                             |               
|                        || tanto, deberá existir el mismo número de campos como de expresiones                                                                                                                   |
|                        || regulares.                                                                                                                                                                            |                                                                              
|                        ||                                                                                                                                                                                       |
|                        |                                                                                                                                                                                        |
|                        | * **dsTabla**: nombre del recurso                                                                                                                                                      |
|                        | * **dsCampo**: nombre del campo del recurso por el que se desea filtrar                                                                                                                |
|                        | * **regex**: expresión regular que se desea validar para un campo específico                                                                                                           |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Resultado              || Array en formato JSON con el número de registros coincidentes con el filtro.                                                                                                          |
|                        ||                                                                                                                                                                                       |
|                        || **Formato**:                                                                                                                                                                          |
|                        ||                                                                                                                                                                                       |
|                        |                                                                                                                                                                                        |
|                        | * **claveRecurso** :  valor                                                                                                                                                            |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Ejemplo de llamada     | `http://<servidor>:9090/BigOpenApi/contarResultados?dsTabla=<nombreRecurso>&dsCampo=<campo1>&regex=<regex1>&dsCampo=<campo2>&regex=<regex2>`_                                          |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _http://<servidor>:9090/BigOpenApi/contarResultados?dsTabla=<nombreRecurso>&dsCampo=<campo1>&regex=<regex1>&dsCampo=<campo2>&regex=<regex2>: http://<servidor>:9090/BigOpenApi/contarResultados?dsTabla=<nombreRecurso>&dsCampo=<campo1>&regex=<regex1>&dsCampo=<campo2>&regex=<regex2>

+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| filtrarResultados                                                                                                                                                                                                |
+========================+=========================================================================================================================================================================================+
| Descripción            || Devuelve los registros coincidentes para los campos y expresiones regulares                                                                                                            |
|                        || enviadas como parámetros para un recurso.                                                                                                                                              |
|                        ||                                                                                                                                                                                        |
|                        || Si la ejecución es correcta, la respuesta se realizará mediante un **archivo de**                                                                                                      |
|                        || **texto** plano con el objeto Resultado en formato JSON. En cambio, en caso                                                                                                            |
|                        || de error se devolverá, **en forma de mensaje**, el objeto JSON de respuesta                                                                                                            |
|                        || informando del error.                                                                                                                                                                  |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Tipo servicio          || Servlet                                                                                                                                                                                |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Parámetros             || Permite enviar una lista de campos y expresiones regulares a cumplir. Los                                                                                                              |
|                        || campos y expresiones regulares se validarán en orden, es decir, el primer                                                                                                              |
|                        || parámetro campo se validará con la primera expresión regular enviada. Por                                                                                                              |
|                        || tanto, deberá existir el mismo número de campos como de expresiones                                                                                                                    |
|                        || regulares.                                                                                                                                                                             |
|                        ||                                                                                                                                                                                        |
|                        |                                                                                                                                                                                         |
|                        | * **dsTabla**: nombre del recurso                                                                                                                                                       |
|                        | * **dsCampo**: nombre del campo del recurso por el que se desea filtrar                                                                                                                 |
|                        | * **regex**: expresión regular que se desea validar para un campo específico                                                                                                            |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Resultado              || Array en formato JSON con los registros coincidentes con el filtro                                                                                                                     |
|                        ||                                                                                                                                                                                        |
|                        || **Formato**:                                                                                                                                                                           |
|                        ||                                                                                                                                                                                        |
|                        |                                                                                                                                                                                         |
|                        | * **claveRecurso** :  valor                                                                                                                                                             |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Ejemplo de llamada     | `http://<servidor>:9090/BigOpenApi/filtrarResultados?dsTabla=<nombreRecurso>&dsCampo=<campo1>&regex=<regex1>&dsCampo=<campo2>&regex=<regex2>`_                                          |
+------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _http://<servidor>:9090/BigOpenApi/filtrarResultados?dsTabla=<nombreRecurso>&dsCampo=<campo1>&regex=<regex1>&dsCampo=<campo2>&regex=<regex2>: http://<servidor>:9090/BigOpenApi/filtrarResultados?dsTabla=<nombreRecurso>&dsCampo=<campo1>&regex=<regex1>&dsCampo=<campo2>&regex=<regex2>

+------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| buscarEnUnRadio                                                                                                                                                                                                    |
+========================+===========================================================================================================================================================================================+
| Descripción            || Este servicio permite geolocalizar registros contenidos en un radio para                                                                                                                 |
|                        || aquellos recursos que tengan disponible campos de coordenadas geográficas                                                                                                                |
|                        || (latitud y longitud).                                                                                                                                                                    |
|                        ||                                                                                                                                                                                          |
|                        || Si la ejecución es correcta, la respuesta se realizará mediante un **archivo de**                                                                                                        |
|                        || **texto** plano con el objeto Resultado en formato JSON. En cambio, en caso                                                                                                              |
|                        || de error se devolverá, **en forma de mensaje**, el objeto JSON de respuesta                                                                                                              |
|                        || informando del error.                                                                                                                                                                    |
+------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Tipo servicio          || Servlet                                                                                                                                                                                  |
+------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Parámetros             ||                                                                                                                                                                                          |
|                        |                                                                                                                                                                                           |
|                        | * **dsTabla**: nombre del recurso.                                                                                                                                                        |
|                        | * **centro**: punto central del área a filtrar. Debe ser expresado con formato “latitud,longitud”.                                                                                        |
|                        | * **metros**: distancia a buscar desde el centro solicitado.                                                                                                                              |
|                        | * **fecha**: fecha de los registros solicitados en formato yyyyMMdd. Éste campo no es obligatorio, pero permite agilizar las búsquedas.                                                   |
+------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Resultado              || Array en formato JSON con los registros contenidos en el área solicitada.                                                                                                                |
|                        ||                                                                                                                                                                                          |
|                        || **Formato**:                                                                                                                                                                             |
|                        ||                                                                                                                                                                                          |
|                        |                                                                                                                                                                                           |
|                        | * **claveRecurso** :  valor                                                                                                                                                               |
+------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Ejemplo de llamada     | `http://<servidor>:9090/BigOpenApi/buscarEnUnRadio?dsTabla=<nombreRecurso>&centro=<latitud1>,<longitud1>&metros=<númeroMetros>& fecha=<yyyyMMdd>`_                                        |
+------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _http://<servidor>:9090/BigOpenApi/buscarEnUnRadio?dsTabla=<nombreRecurso>&centro=<latitud1>,<longitud1>&metros=<númeroMetros>& fecha=<yyyyMMdd>: http://<servidor>:9090/BigOpenApi/buscarEnUnRadio?dsTabla=<nombreRecurso>&centro=<latitud1>,<longitud1>&metros=<númeroMetros>& fecha=<yyyyMMdd>

+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| buscarEnUnPoligono                                                                                                                                                                                                                                                          |
+========================+====================================================================================================================================================================================================================================================+
| Descripción            || Este servicio permite geolocalizar registros contenidos en un polígono para                                                                                                                                                                       |
|                        || aquellos recursos que tengan disponible campos de coordenadas geográficas                                                                                                                                                                         |
|                        || (latitud y longitud).                                                                                                                                                                                                                             |
|                        ||                                                                                                                                                                                                                                                   |
|                        || Si la ejecución es correcta, la respuesta se realizará mediante un **archivo de**                                                                                                                                                                 |
|                        || **texto** plano con el objeto Resultado en formato JSON. En cambio, en caso                                                                                                                                                                       |
|                        || de error se devolverá, **en forma de mensaje**, el objeto JSON de respuesta                                                                                                                                                                       |
|                        || informando del error.                                                                                                                                                                                                                             |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Tipo servicio          || Servlet                                                                                                                                                                                                                                           |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Parámetros             || Permite enviar una lista de coordenadas que marcarán los vértices del polígono                                                                                                                                                                    |
|                        || solicitado. Las coordenadas deberán ser enviadas en el orden en el que se                                                                                                                                                                         |
|                        || quiere que se unan los puntos.                                                                                                                                                                                                                    |
|                        ||                                                                                                                                                                                                                                                   |
|                        |                                                                                                                                                                                                                                                    |
|                        | * **dsTabla**: Nombre del recurso                                                                                                                                                                                                                  |
|                        | * **coordenadas**: punto geográfico del polígono a filtrar. Debe ser expresado con formato “latitud,longitud”.                                                                                                                                     |
|                        | * **fecha**: fecha de los registros solicitados en formato yyyyMMdd. Éste campo no es obligatorio, pero permite agilizar las búsquedas.                                                                                                            |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Resultado              || Array en formato JSON con los registros contenidos en el polígono solicitado.                                                                                                                                                                     |
|                        ||                                                                                                                                                                                                                                                   |
|                        || **Formato**:                                                                                                                                                                                                                                      |
|                        ||                                                                                                                                                                                                                                                   |
|                        |                                                                                                                                                                                                                                                    |
|                        | * **claveRecurso** :  valor                                                                                                                                                                                                                        |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Ejemplo de llamada     | `http://<servidor>:9090/BigOpenApi/buscarEnUnPoligono?dsTabla=<nombreRecurso>&coordenadas=<latitud1>,<longitud1>&coordenadas=<latitud2>,<longitud3>&coordenadas=<latitud2>,<longitud3>&fecha=<yyyyMMdd>`_                                          |
+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _http://<servidor>:9090/BigOpenApi/buscarEnUnPoligono?dsTabla=<nombreRecurso>&coordenadas=<latitud1>,<longitud1>&coordenadas=<latitud2>,<longitud3>&coordenadas=<latitud2>,<longitud3>&fecha=<yyyyMMdd>: http:/<servidor>:9090/BigOpenApi/buscarEnUnPoligono?dsTabla=<nombreRecurso>&coordenadas=<latitud1>,<longitud1>&coordenadas=<latitud2>,<longitud3>&coordenadas=<latitud2>,<longitud3>&fecha=<yyyyMMdd>
