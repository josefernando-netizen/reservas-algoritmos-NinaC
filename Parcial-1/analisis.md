A. Análisis de los cuatro fragmentos
Fragmento	Complejidad	Justificación
F1	O(n)	Recorre una sola vez los n elementos.
F2	O(n²)	Tiene dos ciclos anidados de n iteraciones.
F3	O(log n)	Multiplica k por 2 en cada repetición.
F4	O(n log n)	Tiene n iteraciones exteriores y logarítmicas interiores.

B. Resolución de recurrencias
Recurrencia	a	b	d	Comparación	Resultado
\(4T(n/3)+n\)	4	3	1	4 mayor que 3	\(\Theta(n^{\log_3 4})\)
\(2T(n/2)+n^2\)	2	2	2	2 menor que 4	\(\Theta(n^2)\)
