Alternativa 1: Búsqueda lineal

La búsqueda lineal revisa los elementos uno por uno hasta encontrar el código solicitado. En el peor caso puede revisar los 250.000 códigos por consulta.

Para 8.000 consultas:

250.000 × 8.000 = 2.000.000.000 comparaciones.

Su complejidad es O(n).

Alternativa 2: Ordenamiento eficiente y búsqueda binaria

Consiste en ordenar una sola vez los 250.000 códigos y posteriormente utilizar búsqueda binaria.

El ordenamiento tiene un costo aproximado de 4.482.500 operaciones y las 8.000 consultas necesitan aproximadamente 143.440 comparaciones.

Total aproximado: 4.625.940 operaciones.

Su complejidad es O(n log n + q log n).

Alternativa 3: Ordenamiento cuadrático y búsqueda binaria

Esta alternativa utiliza un ordenamiento cuadrático, como burbuja, y después realiza búsqueda binaria.

El ordenamiento tiene un costo aproximado de orden O(n²), por lo que resulta demasiado lento para 250.000 elementos.
