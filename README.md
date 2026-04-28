

**Caso 1: ¿Qué hace que un producto triunfe en e-commerce?**

**1\. Portada del equipo**

Integrantes:

Valeria Ayala   
Diandra Bañez  
Diego Alvarez  
Carlos Carrizales  
Natalia Ccusi

**Roles:**

 **Líder de proyecto:** Carlos Carrizales  
 **Analista de datos:** Valeria Ayala  
 **Ingeniero de datos:** Diego Alvarez   
 **Analista de negocio:** Diandra Bañez  
 **Especialista en visualización y reporting:** Natalia Ccusi

1. **Descripción del problema de negocio**

El problema de negocio se centra en identificar qué factores influyen en el éxito de un producto dentro de un marketplace de e-commerce, tomando como referencia plataformas similares a Olist en Brasil. En este tipo de empresas, los vendedores compiten dentro de una misma plataforma y dependen de variables como el precio, el costo de envío, la categoría del producto, el tiempo de entrega y la experiencia del cliente para lograr ventas sostenibles y buenas calificaciones.

Este problema es relevante porque la satisfacción del cliente impacta directamente en la reputación del vendedor, la recompra y la rentabilidad del marketplace. Una mala experiencia, como una entrega tardía, un costo de envío elevado o una baja calidad percibida, puede generar calificaciones negativas y reducir la confianza del consumidor. Por otro lado, entender qué factores generan mejores reseñas permite priorizar mejoras logísticas, comerciales y de atención al cliente.

En este contexto, analizar cómo variables como el precio, el tiempo de entrega, la categoría del producto y la calificación del cliente afectan el desempeño de los productos permite tomar mejores decisiones de negocio. Esto puede ayudar a los marketplaces y vendedores digitales a optimizar su oferta, mejorar la experiencia de compra y escalar sus ventas de forma más eficiente.

2.  **Descripción de los datos**

**Fuente principal:**

El dataset principal corresponde a Brazilian E-Commerce Public Dataset by Olist, disponible en Kaggle. Este conjunto de datos contiene información de pedidos realizados en Brasil, incluyendo datos de órdenes, productos, clientes, vendedores, pagos, envíos y reseñas.

**Fuentes de enriquecimiento:**

Para complementar el análisis, se incorporan datos externos como:

* Calendario comercial de Brasil, considerando fechas como Black Friday, Navidad y otras temporadas de alta demanda.  
* Días festivos nacionales en Brasil, para analizar posibles variaciones en volumen de pedidos y tiempos de entrega.  
* Información referencial del tipo de cambio BRL/PEN, para contextualizar precios desde una perspectiva regional.

**Número de registros:**

El dataset cuenta con más de 100,000 órdenes registradas, lo que permite realizar análisis robustos sobre comportamiento de compra, satisfacción del cliente, tiempos de entrega y desempeño por categoría.

**Variables Clave:**

* Fecha de compra: permite analizar patrones temporales y temporadas de mayor demanda.  
*  Precio del producto: variable clave para evaluar competitividad y percepción de valor.  
* Costo de envío: puede influir en la satisfacción y decisión de compra.  
* Categoría del producto: permite identificar qué tipos de productos tienen mejor desempeño.  
* Tiempo de entrega: diferencia entre la fecha de compra, fecha estimada y fecha real de entrega.  
*  Calificación del cliente: variable principal para medir satisfacción.  
* Estado del pedido: permite filtrar pedidos entregados, cancelados o con problemas  
* Ubicación del cliente y vendedor: ayuda a analizar distancia, tiempos logísticos y posibles retrasos.

**Limitaciones de los datos:**

* No existe una variable directa de recompra, por lo que se debe aproximar con comportamiento de clientes o reseñas.  
* Algunas categorías presentan valores nulos o nombres incompletos.  
* No todos los pedidos tienen la misma cantidad de información disponible en reseñas o pagos.  
* El dataset representa un periodo específico, por lo que los resultados no necesariamente reflejan el comportamiento actual del mercado.

3. **EDA Inicial**

**Visualización 1: Distribución de calificaciones de clientes**

![img](images/imagen1.png)

Esta visualización permite observar cómo se distribuyen las reseñas de los clientes en una escala de 1 a 5\. El objetivo es identificar si la mayoría de compradores tuvo una experiencia positiva o si existe una proporción significativa de clientes insatisfechos.

**Interpretación esperada:**  
Si las calificaciones de 4 y 5 estrellas predominan, se puede afirmar que la mayoría de pedidos generan satisfacción. Sin embargo, las calificaciones bajas deben analizarse con mayor detalle porque pueden estar asociadas a retrasos, costos de envío altos o problemas por categoría.

**Visualización 2: Top 10 categorías con mayor número de pedidos**

![img](images/imagen2.png)

Esta visualización muestra las categorías de productos con mayor volumen de ventas dentro del marketplace. Permite identificar qué categorías concentran mayor demanda y cuáles podrían tener mayor importancia estratégica para la empresa.

**Interpretación esperada:**  
Las categorías con mayor número de pedidos pueden representar oportunidades de optimización, ya que cualquier mejora en precio, envío o satisfacción dentro de ellas tendría un impacto importante en el negocio.

**Visualización 3: Relación entre tiempo de entrega y calificación del cliente**

![img](images/imagen3.png)

Esta visualización compara los días de entrega con la calificación otorgada por el cliente. El objetivo es analizar si los pedidos que demoran más reciben peores reseñas.

**Interpretación esperada:**  
Si se observa que las calificaciones disminuyen cuando el tiempo de entrega aumenta, se podría concluir que la logística tiene un impacto directo en la satisfacción del cliente.

**Visualización 4: Costo de envío promedio por categoría**

![img](images/imagen4.png)

Esta visualización permite comparar cuánto pagan los clientes por envío según la categoría del producto. Algunas categorías pueden tener costos más altos debido al peso, volumen o distancia logística.

**Interpretación esperada:**  
Si ciertas categorías tienen costos de envío elevados y calificaciones más bajas, el marketplace podría revisar estrategias de subsidio, promociones o mejora logística para reducir la fricción en la compra.

**Visualización 5: Pedidos entregados a tiempo vs. pedidos con retraso**

![img](images/imagen5.png)

Esta visualización clasifica los pedidos según si fueron entregados antes o después de la fecha estimada. Permite medir el nivel de cumplimiento logístico del marketplace.

**Interpretación esperada:**  
Un alto porcentaje de entregas tardías podría explicar parte de las calificaciones negativas. Además, esta métrica puede ser usada como indicador clave para proponer recomendaciones en la etapa final.

**4\. Hipótesis de negocio**

Para la Etapa 2 de este proyecto, el equipo se enfocará en validar las siguientes hipótesis de negocio mediante análisis estadístico y modelos básicos:

1\. ¿Los pedidos con mayor tiempo de entrega reciben calificaciones más bajas que los pedidos entregados dentro del plazo estimado, debido a que la demora afecta la experiencia de compra del cliente?

2\. ¿Los costos de envío elevados reducen la satisfacción del cliente, especialmente cuando representan una proporción importante del costo total de la compra?

3\. ¿Existen categorías de productos que obtienen mejores calificaciones que otras debido a diferencias en expectativas del cliente, características del producto y desempeño logístico?

4\. ¿El precio del producto influye en la calificación del cliente, considerando que precios más altos pueden generar mayores expectativas sobre la calidad y el servicio recibido?

**Variables a analizar**

Para validar estas hipótesis se utilizarán variables del dataset relacionadas con el proceso de compra y la experiencia del cliente:

*  Tiempo de entrega: diferencia entre la fecha estimada y la fecha real de entrega.  
*  Costo de envío: valor pagado por el transporte del pedido.  
* Precio del producto: precio registrado del artículo comprado.  
* Categoría del producto: clasificación del producto dentro del marketplace.  
* Calificación del cliente: puntaje de satisfacción otorgado en la reseña.

**Enfoque de análisis**

* Las hipótesis serán evaluadas mediante análisis exploratorio de datos, comparación de grupos, análisis de correlación y segmentación por categorías. Esto permitirá identificar qué variables tienen mayor relación con la satisfacción del cliente y cuáles podrían convertirse en oportunidades de mejora para el marketplace.

**5\. Plan de trabajo – Etapa 2 (Semanas 7–14)**

| Semana | Actividad | Responsable |
| :---: | :---: | :---: |
| 7 | Integración de datasets | Diandra |
| 8 | Análisis de variables clave | Valeria |
| 9 | Validación de hipótesis | Carlos |
| 10 | Modelado básico | Diego |
| 11 | Dashboard	 | Natalia |
| 12 | Insights y recomendaciones | Valeria |
| 13 | Presentación | Diandra |
| 14 | Entrega final | Todo el equipo |

**6\.  Apéndice**

Durante el desarrollo del presente trabajo, el equipo utilizó herramientas de inteligencia artificial generativa, específicamente ChatGPT, como apoyo en la elaboración del informe.

El uso de la IA se enfocó principalmente en:

- La mejora de la redacción y claridad del contenido.  
- La organización de la estructura del documento.  
- La formulación y ajuste de las hipótesis de negocio.  
-  La revisión de la coherencia entre el problema planteado, los datos utilizados y el análisis exploratorio realizado.

Es importante destacar que todas las sugerencias generadas por la herramienta fueron revisadas, contrastadas y validadas por los integrantes del equipo antes de ser incorporadas al documento final.

Asimismo, el análisis de datos, la interpretación de los resultados, las visualizaciones y las conclusiones presentadas corresponden al trabajo propio del equipo, basado en el dataset utilizado y en el desarrollo del notebook.

