Curar y medir
Esta parte tiene dos actividades: corregir el algoritmo lento y comparar los tiempos.
A. Corregir la función
En tu archivo Program.cs, busca esta función:
public static bool HayComprobantesRepetidosCurado(int[] comprobantes)
{
    throw new NotImplementedException("Escribe aquí tu cura.");
}


La idea es utilizar un HashSet<int>, que guarda los números que ya se revisaron.

Completa la función con esta lógica:
1. Crear un conjunto vacío llamado vistos.
2. Recorrer cada número del arreglo.
3. Si el número ya estaba en el conjunto, devolver true.
4. Si termina el recorrido sin encontrar repetidos, devolver false.
La línea clave es:
if (!vistos.Add(numero))


Add() devuelve false cuando ese número ya estaba guardado.

Costo esperado: O(n) en tiempo y O(n) en memoria adicional. El arreglo original no se modifica.
B. Medir los tiempos
Debes comparar los dos métodos:
- HayComprobantesRepetidosPorPares: O(n²).
- HayComprobantesRepetidosCurado: O(n) esperado.
Usa cuatro tamaños duplicados. Por ejemplo, si eliges n = 1.000, tus tamaños serán:
Medición	Cantidad
n	1.000
2n	2.000
4n	4.000
8n	8.000

Pero debes ajustar el tamaño: la función lenta con el tamaño mayor debe tardar entre 0,5 y 20 segundos.

Para cada tamaño:
- Haz una corrida de calentamiento.
- Haz tres corridas medidas.
- Calcula el promedio de las tres.
- Usa una lista sin repetidos.
La tabla que debes llenar con tus resultados reales es:
Tamaño	Pares (ms)	Cura (ms)	Veces más lento pares respecto a fila anterior
n	Tu medición	Tu medición	—
2n	Tu medición	Tu medición	Tiempo actual / anterior
4n	Tu medición	Tu medición	Tiempo actual / anterior
8n	Tu medición	Tu medición	Tiempo actual / anterior

No inventes los tiempos: tienen que salir de tu computadora.
3. P1.3 — Elegir el algoritmo
Aquí debes comparar las tres opciones con los datos del examen:
- \(n=250.000\) códigos.
- \(q=8.000\) consultas.
Opción 1: búsqueda lineal

En el peor caso revisa todos los códigos en cada consulta:

          250.000 \times 8.000 = 2.000.000.000


Aproximadamente 2.000 millones de comparaciones.

Opción 2: ordenar eficientemente y buscar en forma binaria

            log_2(250.000)\approx17,93


Ordenar cuesta aproximadamente:

            250.000 \times 17,93 = 4.482.500
  

Las 8.000 búsquedas cuestan aproximadamente:
  
            8.000 \times 17,93 = 143.440

Total aproximado:

            4.482.500+143.440=4.625.940


Opción 3: ordenar con algoritmo cuadrático y buscar en forma binaria

Si estimamos el ordenamiento como \(n^2\):

                  250.000^2=62.500.000.000


Más las búsquedas binarias, aproximadamente 143.440 operaciones.

¿Cuál elegir?

La opción 2 es la más conveniente: ordenar una vez con un algoritmo eficiente y después realizar las búsquedas binarias. Para respetar la memoria limitada, el ordenamiento debe hacerse sobre el mismo listado, sin duplicarlo.

¿Desde cuántas consultas cambiaría de opinión?

Comparando los costos simplificados:

                    q(250.000)=4.482.500+q(17,93)
El punto de equilibrio es aproximadamente 18 consultas. Desde unas 19 consultas, ordenar y buscar podría ser más conveniente que hacer búsquedas lineales, bajo este modelo de operaciones.
