# Opciones-Nike

README: ANÁLISIS COMPLETO DE OPCIONES - NIKE INC. (NKE)
EJERCICIO DE AUMENTO DE NOTA - PARCIAL 1 O 2
Estudiante: Daniela Perez
Fecha de Generación: 17 de abril de 2026

1. RESUMEN EJECUTIVO DEL ANÁLISIS

Este documento presenta el análisis exhaustivo de dos opciones europeas sobre la 
acción de Nike Inc. (NKE), cotizada en NYSE. Se han modelado las curvas de 
convexidad (precio vs subyacente) y las 5 griegas (Delta, Gamma, Theta, Vega, 
Rho) para escenarios temporales de 1 mes, 6 meses y vencimiento (mes 21).

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
• Mes 0 (Inicio): T=1.7262 años, SOFR=3.720%
• Mes 6: T=1.2330 años, SOFR=3.700%
• Mes 21 (Vencimiento): T=0.0000 años, SOFR=3.650%
• La tasa SOFR decrece linealmente desde 3.72% hasta 3.65%, reflejando un 
  escenario de política monetaria ligeramente expansiva o estabilizadora.
• Los días hábiles restantes disminuyen proporcionalmente (435 → 0).

TABLA 2: CONVEXIDAD - OPCIÓN CALL
<img width="519" height="187" alt="image" src="https://github.com/user-attachments/assets/c13ff4f8-5f4f-4e56-bc1d-80a6f1aa55ae" />

Muestra la relación entre el precio del subyacente (S) y el precio teórico de 
la opción Call.

Análisis:
• En S=$52.50 : Precio=$12.87 | Valor Temporal=$12.87 (100% del valor)
• En S=$70.00 : Precio=$26.21 | Valor Temporal=$8.71 (33% del valor)
• En S=$30.00 : Precio=$2.31 | Valor Intrínseco=$0.00
• Se observa la asimetría positiva típica de las Calls: potencial de ganancia 
  ilimitado a la derecha, pérdida limitada a la prima a la izquierda.

TABLA 3: CONVEXIDAD - OPCIÓN PUT 
<img width="523" height="165" alt="image" src="https://github.com/user-attachments/assets/8bc30cd2-7ccd-4a90-bb1c-35d5aa5738af" />

Muestra la relación entre el precio del subyacente (S) y el precio teórico de 
la opción Put.

Análisis:
• En S=$50.00 : Precio=$6.95 | Valor Temporal=$6.95
• En S=$30.00 : Precio=$18.20 | Valor Intrínseco=$20.00
• En S=$70.00 : Precio=$2.43 | Valor Temporal=$2.43
• Nota: Se observa un valor temporal negativo teórico en S muy bajos ($18-$36), 
  lo cual indica que el modelo Black-Scholes con la IV dada genera precios 
  ligeramente por debajo del valor intrínseco en zonas de profundo ITM, un 
  artefacto matemático común cuando la IV es baja para opciones muy ITM con 
  mucho tiempo restante. En la práctica, el precio de mercado nunca sería menor 
  al intrínseco.

TABLAS 4-6: GRIEGAS CALL (Mes 1, Mes 6, Mes 21)
<img width="688" height="178" alt="image" src="https://github.com/user-attachments/assets/34860dd7-5c1c-4cbf-9121-e0802cf48081" />

<img width="688" height="159" alt="image" src="https://github.com/user-attachments/assets/69f418b1-4cbd-4c61-8106-1aed24b938bb" />

<img width="687" height="175" alt="image" src="https://github.com/user-attachments/assets/510e9c52-e4ea-4da6-a66a-1c14eb78c62c" />

• Mes 1: Delta transicional suave (0.008 a 0.98). Gamma máximo de 0.0201 cerca 
  de S=$32-$34. Theta negativo moderado (-0.011).
• Mes 6: Delta más inclinado. Gamma se concentra más cerca del Strike ($52.50). 
  Theta se intensifica (-0.010).
• Mes 21 (Vencimiento): Función escalón. Delta=1 para S>K, Delta=0 para S<K. 
  Gamma, Theta, Vega y Rho son 0.0 en todo el rango, excepto en el punto 
  exacto del strike donde son teóricamente infinitos (delta de Dirac).

TABLAS 7-9: GRIEGAS PUT (Mes 1, Mes 6, Mes 21)
<img width="690" height="175" alt="image" src="https://github.com/user-attachments/assets/7162d378-ee21-4213-9836-82eeffa85342" />

<img width="689" height="157" alt="image" src="https://github.com/user-attachments/assets/a4cd6e81-6f5b-40be-89d7-e69426befc5d" />

<img width="688" height="112" alt="image" src="https://github.com/user-attachments/assets/73a7a3a5-facc-440f-8cd7-6d1ec6a5da85" />

• Mes 1: Delta negativo (-0.98 a -0.01). Gamma simétrico a la Call pero 
  desplazado al Strike de $50.00.
• Mes 6: Comportamiento similar al mes 6 de la Call, con Delta acercándose a 
  -1 o 0 más rápidamente según la dirección del mercado.
• Mes 21: Delta=-1 para S<K, Delta=0 para S>K. El resto de griegas son 0.

3. ANÁLISIS VISUAL DE GRÁFICAS GENERADAS

GRÁFICA 1: DASHBOARD COMPARATIVO CALL vs PUT

<img width="1361" height="539" alt="image" src="https://github.com/user-attachments/assets/6a51eab0-1bd3-4b43-ab5f-06971f59435c" />

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

• Mes 1: Las curvas son anchas y suaves. Vega alcanza su máximo (~0.25) cerca 
  de S=$58, indicando que la opción es muy sensible a cambios en la 
  volatilidad implícita en este horizonte.
• Mes 6: Las curvas se estrechan. Gamma alcanza su pico (~0.025) más cerca del 
  Strike $52.50. Theta se vuelve más pronunciado (pérdida de valor temporal 
  más rápida).
• Mes 21: Todas las curvas de griegas (Delta, Gamma, Theta, Vega, Rho) son 
  líneas planas en 0 o 1. Esto confirma el comportamiento determinista al 
  vencimiento: la opción vale max(S-K, 0). No hay incertidumbre (Vega=0), 
  no hay tiempo que perder (Theta=0), no hay curvatura (Gamma=0).

GRÁFICAS 5-7: GRIEGAS PUT (Mes 1, Mes 6, Mes 21)

<img width="1362" height="545" alt="image" src="https://github.com/user-attachments/assets/cc536800-7d7b-4bd0-92b9-6b98d56fda36" />

<img width="1362" height="556" alt="image" src="https://github.com/user-attachments/assets/c86cffc5-19fc-4aff-99e3-05267e8d5ae2" />

<img width="1360" height="553" alt="image" src="https://github.com/user-attachments/assets/84929c2e-78ea-411a-a38d-1538e0e895db" />

• Mes 1: Delta parte de -1 en S bajos y sube hacia 0. Gamma tiene su pico 
  (~0.024) cerca de S=$38-$40, ligeramente por debajo del Strike $50, lo cual 
  es consistente con el skew de volatilidad o la asimetría del modelo.
• Mes 6: El pico de Gamma se desplaza y se hace más agudo cerca de S=$50. 
  Theta es negativo (pérdida de valor) pero menos agresivo que en la Call 
  OTM.
• Mes 21: Comportamiento escalón inverso a la Call. Delta salta de -1 a 0 en 
  S=$50.

4. CONCLUSIONES MATEMÁTICAS Y FINANCIERAS
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
