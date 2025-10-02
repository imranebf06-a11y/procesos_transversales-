# Streamlit – Procesos Transversales (Producción → Inventarios → Almacenes → Transporte)

Simulador interactivo para visualizar cómo pequeños cambios en **demanda**, **capacidad de producción**, **políticas de inventario**, **capacidad de almacén** y **transporte** generan **cuellos de botella** y afectan al **nivel de servicio**.

## Ejecutar
```bash
pip install -r requirements.txt
streamlit run app.py
```
Indicadores Clave de Rendimiento (KPIs)
Los KPIs principales indican el desempeño general del sistema y la utilización de los recursos:
Nivel de servicio (%): 92.8%. Esto representa la
 proporción de demanda atendida.
Utilización producción (%): 100.0%.
Utilización picking (%): 78.8%. (El valor en la barra de la gráfica se lee como 78.7766... ).
Utilización transporte (%): 87.5%.

Identificación del Cuello de Botella
El cuello de botella es el proceso con la mayor utilización, ya que está operando a su máxima capacidad y limitando el rendimiento de todo el sistema.
El proceso con la mayor utilización es
 Producción, con un 100.0% de utilización.
Según la metodología de análisis, si un proceso está
 cerca del 100%, ese es el cuello de botella.
Por lo tanto, en este escenario, el
proceso más crítico es Producción. Su utilización del
100% sugiere que la capacidad de producción (900 unidades diarias con 85% de eficiencia, resultando en 765 unidades producidas) es la que está limitando la capacidad de todo el flujo, especialmente cuando la demanda diaria media es de 800 unidades. El gráfico de
Producción vs Demanda (gráfico 1) probablemente confirmará esto, mostrando que en muchos días la producción no alcanza a cubrir la demanda fluctuante.

Interpretación de los Gráficos
Los gráficos comparativos ayudan a visualizar el impacto del cuello de botella:
Producción vs Demanda: Muestra si la capacidad de producción cubre los pedidos. Con una utilización del
 100% en Producción y una demanda media de 800 unidades, pero una capacidad de producción efectiva menor (aprox. 765 unidades), es probable que este gráfico muestre backlog (pedidos pendientes).
Inventario y Backlog: Este gráfico visualiza acumulaciones o faltantes. La presencia de backlog se confirmaría aquí, indicando pedidos no atendidos debido a la limitación de Producción.
Picking y Cola de Envío: La utilización de Picking es de 78.8%. Aunque esto indica una alta carga de trabajo, está por debajo de la limitación de Producción, por lo que
 no es el cuello de botella primario.
Enviado vs Entregado: Muestra la diferencia entre lo que sale del almacén y lo que llega al cliente (según el lead time de transporte). La utilización de Transporte es de
 87.5% , lo que sugiere que
 Tansporte no es el límite.
Resumen del Flujo de los Procesos Transversales
Los procesos están encadenados como
Producción → Inventarios → Almacenes → Transporte. El límite del sistema se encuentra en
Producción al estar al 100% de utilización. Esto significa que, incluso con una alta utilización en Picking y Transporte, estos procesos no pueden procesar más de lo que la Producción les está entregando, ya que su capacidad máxima ha sido alcanzada.
