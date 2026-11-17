
Análisis de algoritmos
Esta es la primera parte que debes comprender y escribir en analisis.md.
Fragmento	Costo en peor caso	Justificación
F1	O(n)	Recorre los n elementos una sola vez.
F2	O(n²)	Tiene dos ciclos anidados que recorren n elementos.
F3	O(log n)	En cada repetición multiplica k por 2.
F4	O(n log n)	El ciclo exterior se repite n veces y el interior divide k entre 3.

Recurrencias por teorema maestro

Para \(T(n)=aT(n/b)+n^d\), comparamos \(a\) con \(b^d\).
- (i) \(T(n)=4T(n/3)+n\)
  - \(a=4,\ b=3,\ d=1\).
  - \(b^d=3^1=3\).
  - Como \(4>3\), domina la parte recursiva.
  - Resultado: \(\Theta(n^{\log_3 4})\).
- (ii) \(T(n)=2T(n/2)+n^2\)
  - \(a=2,\ b=2,\ d=2\).
  - \(b^d=2^2=4\).
  - Como \(2<4\), domina el trabajo fuera de la recursión.
  - Resultado: \(\Theta(n^2)\).
