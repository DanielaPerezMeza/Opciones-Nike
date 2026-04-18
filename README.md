# Opciones-Nike

README: ANÁLISIS COMPLETO DE OPCIONES - NIKE INC. (NKE)
EJERCICIO DE AUMENTO DE NOTA - PARCIAL 1 O 2
Estudiante: Daniela Perez
Fecha de Generación: 17 de abril de 2026

1. RESUMEN EJECUTIVO DEL ANÁLISIS

En este ejercicio analicé dos opciones europeas de la acción de Nike (NKE). Estudié cómo cambia su precio según el valor de la acción y el tiempo, usando también las griegas (Delta, Gamma, Theta, Vega y Rho) para entender su sensibilidad.
Trabajé con datos reales del 17 de abril de 2026, donde la acción estaba en $46.06, y evalué tres momentos: 1 mes, 6 meses y el vencimiento (21 meses).
Analicé una opción call con strike de $52.50, que está fuera del dinero (OTM), y una opción put con strike de $50.00, que está dentro del dinero.
vimos cómo influyen el tiempo, la volatilidad y el precio del activo en el valor de las opciones.

DATOS DE MERCADO REALES (17/04/2026):
• Acción: NKE (Nike Inc.)
• Precio Actual (S₀): $46.06
• Fecha Inicial: 17/04/2026
• Fecha Vencimiento: 17/12/2027
• Duración Total: 1.7262 años comerciales (21 meses simulados)
• Días Hábiles: 435 días (base 252 días/año)

OPCIONES ANALIZADAS:
 OPCIÓN CALL:
   • Strike (K): $52.50
   • Volatilidad Implícita Inicial: 41.70%
   • Estado: Levemente OTM (Out of The Money)

 OPCIÓN PUT:
   • Strike (K): $50.00
   • Volatilidad Implícita Inicial: 31.40%
   • Estado: Ligeramente ITM (In The Money)

2. ANÁLISIS DETALLADO DE TABLAS GENERADAS

TABLA 1: SIMULACIÓN TEMPORAL MENSUAL

   <img width="743" height="275" alt="image" src="https://github.com/user-attachments/assets/eea03a0f-349f-4ebf-b464-5b1fce7d25ca" />

Esta tabla define la evolución de los parámetros macroeconómicos y temporales 
durante la vida de la opción.

Observaciones Clave:
En el inicio (mes 0), el tiempo al vencimiento es de 1.7262 años y la tasa SOFR es de 3.72%. A los 6 meses, el tiempo se reduce a 1.2330 años con una tasa de 3.70%, y al vencimiento (mes 21) el tiempo llega a 0, con una tasa de 3.65%.
Vemos que la tasa SOFR disminuye de forma progresiva desde 3.72% hasta 3.65%, lo que sugiere un escenario de tasas ligeramente más bajas o estables en el tiempo.
Por otro lado, los días hábiles restantes también disminuyen de manera proporcional, pasando de 435 días al inicio hasta 0 en el vencimiento.

TABLA 2: CONVEXIDAD - OPCIÓN CALL

<img width="519" height="187" alt="image" src="https://github.com/user-attachments/assets/c13ff4f8-5f4f-4e56-bc1d-80a6f1aa55ae" />

Muestra la relación entre el precio del subyacente (S) y el precio teórico de 
la opción Call.

Análisis:
Esta tabla muestra cómo varía el precio de la opción Call según el precio del subyacente.
Cuando S = $52.50 (ATM), el precio ($12.87) corresponde totalmente a valor temporal. Si el precio sube a $70.00 (ITM), la opción aumenta a $26.21 y ya incluye valor intrínseco. En cambio, si baja a $30.00 (OTM), su valor es bajo ($2.31) y sin valor intrínseco.
Se evidencia el comportamiento típico de una Call: ganancias potenciales altas al alza y pérdida limitada a la prima.

TABLA 3: CONVEXIDAD - OPCIÓN PUT 

<img width="523" height="165" alt="image" src="https://github.com/user-attachments/assets/8bc30cd2-7ccd-4a90-bb1c-35d5aa5738af" />

Muestra la relación entre el precio del subyacente (S) y el precio teórico de 
la opción Put.

Análisis:
Cuando S = $50.00 (ATM), el precio es $6.95 y corresponde totalmente a valor temporal. Si el precio baja a $30.00 (ITM), la opción aumenta a $18.20, predominando el valor intrínseco. En cambio, cuando sube a $70.00 (OTM), el precio baja a $2.43 y solo tiene valor temporal.
Se observa que en precios muy bajos de la acción aparece un valor temporal negativo, lo cual es un efecto del modelo teórico utilizado. Sin embargo, en la práctica, el precio de mercado no sería menor que su valor intrínseco.

TABLAS 4-6: GRIEGAS CALL (Mes 1, Mes 6, Mes 21)

<img width="688" height="178" alt="image" src="https://github.com/user-attachments/assets/34860dd7-5c1c-4cbf-9121-e0802cf48081" />


<img width="688" height="159" alt="image" src="https://github.com/user-attachments/assets/69f418b1-4cbd-4c61-8106-1aed24b938bb" />


<img width="687" height="175" alt="image" src="https://github.com/user-attachments/assets/510e9c52-e4ea-4da6-a66a-1c14eb78c62c" />

En el mes 1, el Delta cambia de forma gradual (de 0.008 a 0.98), el Gamma alcanza su punto máximo cerca de precios entre $32 y $34, y el Theta es negativo pero moderado.

Para el mes 6, el Delta se vuelve más pronunciado, el Gamma se concentra más cerca del precio de ejercicio ($52.50) y el Theta sigue siendo negativo, con mayor efecto.

En el vencimiento (mes 21), el comportamiento se vuelve tipo “escalón”: el Delta es 1 si el precio está por encima del strike y 0 si está por debajo. Las demás griegas tienden a cero en casi todos los puntos, excepto exactamente en el strike.

TABLAS 7-9: GRIEGAS PUT (Mes 1, Mes 6, Mes 21)

<img width="690" height="175" alt="image" src="https://github.com/user-attachments/assets/7162d378-ee21-4213-9836-82eeffa85342" />


<img width="689" height="157" alt="image" src="https://github.com/user-attachments/assets/a4cd6e81-6f5b-40be-89d7-e69426befc5d" />


<img width="688" height="112" alt="image" src="https://github.com/user-attachments/assets/73a7a3a5-facc-440f-8cd7-6d1ec6a5da85" />

En el mes 1, el Delta es negativo (entre -0.98 y -0.01) y el Gamma presenta un comportamiento similar al de la Call, pero centrado en el strike de $50.00.

En el mes 6, se mantiene un comportamiento parecido al de la Call, donde el Delta se acerca más rápido a -1 o a 0 dependiendo de si el precio baja o sube.

En el vencimiento (mes 21), el Delta es -1 cuando el precio está por debajo del strike y 0 cuando está por encima. Las demás griegas toman valores cercanos a cero.

3. ANÁLISIS VISUAL DE GRÁFICAS GENERADAS

GRÁFICA 1: DASHBOARD COMPARATIVO CALL vs PUT

<img width="1361" height="539" alt="image" src="https://github.com/user-attachments/assets/6a51eab0-1bd3-4b43-ab5f-06971f59435c" />

La gráfica compara el comportamiento de la Call y la Put.
La Call muestra una curva creciente que aumenta más rápido cuando sube el precio de la acción, mientras que la Put es descendente, con mayor valor cuando el precio es bajo. En ambos casos se marcan los precios de ejercicio.
En el Delta, la Call va de 0 a 1 y la Put de -1 a 0, cambiando principalmente cerca del strike.
En el Gamma, ambas tienen forma de campana, pero la Put es un poco más alta, lo que indica mayor sensibilidad cerca del precio de ejercicio.

Panel Superior Izquierdo (Convexidad CALL):
• Curva azul ascendente con forma de "hockey stick".
• Línea punteada roja en S=$52.50 marca el Strike.
• Se aprecia la suavidad de la transición OTM→ITM debido al tiempo restante 
  (1.64 años).

Panel Superior Derecho (Convexidad PUT):
• Curva roja descendente.
• Máximo valor en S bajos, tendiendo a 0 en S altos.
• Línea punteada roja en S=$50.00.

Panel Inferior Izquierdo (Delta Comparativo):
• Delta CALL (azul): Curva logística creciente de 0 a 1.
• Delta PUT (rojo): Curva logística creciente de -1 a 0.
• Punto de cruce en Delta=0 (para Put) y Delta=0.5 (aprox para Call) cerca 
  de los respectivos strikes.

Panel Inferior Derecho (Gamma Comparativo):
• Ambas curvas en forma de campana.
• La Gamma del PUT (roja) es ligeramente mayor y más ancha que la del CALL 
  (azul), reflejando una estructura de volatilidad donde el Put tiene mayor 
  sensibilidad al movimiento del subyacente en zonas cercanas al dinero.

GRÁFICAS 2-4: GRIEGAS CALL (Mes 1, Mes 6, Mes 21)

<img width="1362" height="542" alt="image" src="https://github.com/user-attachments/assets/58524317-ef9c-4edb-ad45-3c7211a3e588" />


<img width="1365" height="521" alt="image" src="https://github.com/user-attachments/assets/d775325e-025a-4d20-9dbb-ddf8e3156f50" />


<img width="1360" height="570" alt="image" src="https://github.com/user-attachments/assets/7af01236-24ff-4f4b-88b0-6d7bc818f28d" />

En el mes 1, las curvas son más suaves y amplias, y el Vega es alto, lo que indica mayor sensibilidad a la volatilidad.

En el mes 6, las curvas se vuelven más estrechas, el Gamma se concentra cerca del strike y el Theta aumenta, reflejando una pérdida más rápida de valor en el tiempo.

Al final del periodo (mes 21), todas las griegas se estabilizan, mostrando que el valor de la opción depende únicamente de si el precio está por encima o por debajo del strike.

GRÁFICAS 5-7: GRIEGAS PUT (Mes 1, Mes 6, Mes 21)

<img width="1362" height="545" alt="image" src="https://github.com/user-attachments/assets/cc536800-7d7b-4bd0-92b9-6b98d56fda36" />


<img width="1362" height="556" alt="image" src="https://github.com/user-attachments/assets/c86cffc5-19fc-4aff-99e3-05267e8d5ae2" />


<img width="1360" height="553" alt="image" src="https://github.com/user-attachments/assets/84929c2e-78ea-411a-a38d-1538e0e895db" />

En el mes 1, el Delta empieza cerca de -1 cuando el precio es bajo y sube hacia 0. El Gamma alcanza su punto máximo un poco por debajo del strike.

En el mes 6, el Gamma se concentra más cerca del precio de ejercicio y el Theta sigue siendo negativo, pero con menor impacto que en la Call.

Al final del periodo (mes 21), el Delta cambia bruscamente de -1 a 0 justo en el nivel del strike.

4. CONCLUSIONES MATEMÁTICAS Y FINANCIERAS

En general, las opciones pierden valor con el paso del tiempo, y este efecto se intensifica a medida que se acerca el final del periodo. La sensibilidad del Delta (Gamma) es mayor cuando el precio está cerca del strike, lo que implica un mayor riesgo y necesidad de ajustes en ese punto.
Al inicio, las opciones son más sensibles a cambios en la volatilidad, pero este efecto desaparece al final. Finalmente, la Call ofrece mayor potencial de ganancia en escenarios alcistas, mientras que la Put actúa como protección ante caídas, reflejando la forma en que el mercado valora estos riesgos.

A. EVOLUCIÓN TEMPORAL (TIME DECAY):
El Theta es negativo en ambos tipos de opción durante Mes 1 y Mes 6, lo que 
confirma que el poseedor de la opción (posición larga) pierde valor temporal 
cada día que pasa. Este efecto se acelera conforme nos acercamos al vencimiento 
(Mes 6 muestra valores de Theta más negativos en zonas ATM que Mes 1).

B. RIESGO GAMMA:
El riesgo Gamma (sensibilidad del Delta) es máximo cuando la opción está "At 
The Money" (ATM). En Mes 6, el Gamma es significativamente más alto cerca del 
Strike que en Mes 1, lo que implica que el hedging (cobertura delta) debe ser 
más frecuente y preciso conforme se acerca la fecha de expiración.

C. SENSIBILIDAD A VOLATILIDAD (VEGA):
Ambas opciones tienen Vega positivo y alto en los primeros meses (Vega > 0.20), 
indicando que son instrumentos ideales para apostar a un aumento en la 
volatilidad implícita del mercado. Sin embargo, al vencimiento (Mes 21), Vega 
cae a 0, ya que la incertidumbre desaparece.

D. ASIMETRÍA DE RIESGO:
• La CALL ofrece ganancia potencial ilimitada si NKE sube fuertemente.
• La PUT ofrece protección contra caídas, con un piso de ganancia en S=0.
• La diferencia en las Volatilidades Implícitas (Call 41.7% vs Put 31.4%) 
  sugiere un "Volatility Skew" donde el mercado está dispuesto a pagar más 
  prima por protección alcista (Calls) o bien refleja la estructura de 
  sonrisa de volatilidad típica de acciones con tendencia histórica alcista.
