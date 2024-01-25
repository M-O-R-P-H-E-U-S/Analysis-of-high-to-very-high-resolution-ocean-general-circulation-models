# Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models


## Introducción

El presente informe de Practicas Preprofesionales corresponde a la pasantía de investigación realizada entre los meses de Febrero y Mayo del 2023 en el laboratorio de Earth and Atmospheric Sciences en la Universidad de Alberta, en la provincia de Alberta en Canadá.

![uoa](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/uoa.jpeg)

![eas](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/eas.jpeg)

En el laboratorio de Earth and Atmospheric Sciences se dedican a simular fenómenos oceanográficos en base a datos recopilados del Mar Labrador, Zona oeste de Groenlandia, Cabo Farewell y Estrecho de Davis. Está localizada en Edmonton, Canadá.

En el laboratorio se trabajan con múltiples configuraciones sobre las que estan realizando investigaciones: ANHA4, eORCA025, ANHA12, SPG12, LAB60, ARC60 y ANHA2.

En el presente trabajo se utilizo la configuración ANHA, que corresponde a la configuración Ártica y Atlántica del Hemisferio Norte en el modelo NEMO, abarca extensivamente el Océano Ártico, el Atlántico Norte y una parte del Atlántico Sur. Sus límites se extienden desde el Estrecho de Bering en el Ártico hasta los 20 grados de latitud sur en el Océano Atlántico Sur. ANHA se concibió como una versión más enfocada de la red global ORCA, permitiéndonos realizar investigaciones y desarrollos con una utilización más eficiente de recursos informáticos, incluyendo RAM y tiempo de CPU.

La configuración ANHA posee una resolución de 1/4 de grado, denominada ANHA4. Esta resolución específica es crucial para nuestras investigaciones, ya que nos permite alcanzar nuestros objetivos con mayor precisión y utilizando menos recursos computacionales. La elección de esta resolución específica está respaldada por la necesidad de equilibrar la representación detallada de fenómenos oceanográficos cruciales con la eficiencia en el procesamiento de datos.


![grid](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/grid.jpeg)
Regiones sobre el espacio de ANHA4, SPG12 and LS60.

ANHA4 es una configuración regional de baja resolución que desempeña un papel crucial al proporcionarnos simulaciones eficientes y de bajo costo computacional que se centran en modelar remolinos o giros oceánicos. La baja resolución se refiere a la desratización de la cuadrícula espacial, donde la información se agrupa en regiones más grandes, lo que resulta en un menor consumo de recursos computacionales.

Esta configuración se destaca especialmente en estudios de sensibilidad, ya que nos permite llevar a cabo simulaciones que abarcan varias décadas en un período relativamente corto, aproximadamente un mes. Este enfoque nos brinda la capacidad de explorar y entender de manera eficiente cómo diferentes variables y factores afectan el comportamiento oceánico a lo largo del tiempo.

ANHA4 ha demostrado ser extremadamente productivo en nuestro contexto de investigación y desarrollo. Su rapidez en las simulaciones nos facilita realizar pruebas exhaustivas de nuevos modelos o ajustes de parámetros, así como evaluar sistemas acoplados. Este nivel de eficiencia impulsa significativamente nuestra capacidad para avanzar en la comprensión de fenómenos oceanográficos complejos y desarrollar modelos más precisos. 

## Antecedentes

En las últimas décadas, la capa de hielo de Groenlandia ha experimentado un fenómeno alarmante de pérdida de masa, como se evidencia en el estudio científico referenciado \parencite{10.1038/nature12854}. Este proceso, impulsado principalmente por el aumento del derretimiento superficial y la descarga acelerada de glaciares, ha generado un flujo creciente de agua dulce hacia el océano Atlántico subartico.

La magnitud de esta pérdida de masa tiene un papel crucial en la alteración del balance de agua dulce en la región. A medida que aumenta el flujo de agua dulce desde Groenlandia hacia el océano, se presenta una serie de impactos significativos. Este flujo continuo de agua dulce puede afectar de manera directa la salinidad del océano Atlántico subartico, con posibles consecuencias para la circulación oceánica regional.

La entrada de grandes cantidades de agua dulce en la región del Mar Labrador puede modificar las propiedades térmicas y de salinidad del agua, alterando así los patrones de convección impactando en la fauna y flora marina. Esta convección profunda es esencial para la circulación oceánica global, y su perturbación podría tener repercusiones en la circulación de vuelco meridional del Atlántico, un componente crucial del sistema climático global.

El efecto de los aumentados flujos de agua dulce indica que la entrada de agua procedente del deshielo en la plataforma occidental de Groenlandia está dando lugar a una tendencia gradual de enfriamiento en la superficie del mar de Labrador. Aunque, en la actualidad, este enfriamiento es de magnitud inferior en comparación con la variabilidad asociada a eventos esporádicos de "grandes anomalías de salinidad", se prevé que la acumulación continua de agua de deshielo posee el potencial de reducir de manera progresiva la convección invernal profunda.

A pesar de estos cambios, se concluye que la anomalía de agua dulce aún no ha tenido un impacto significativo en la circulación de vuelco meridional del Atlántico.

La interacción entre la capa de hielo de Groenlandia (GrIS) y el océano Atlántico Norte subartico, así como los impactos de la pérdida de masa de la GrIS en el nivel del mar, dan lugar a trayectorias y destinos del agua dulce proveniente del deshielo de Groenlandia, destacándose diferencias notables entre las áreas occidental y oriental de la isla. Se observa que el agua dulce del GrIS occidental tiende a acumularse en la bahía de Baffin antes de dirigirse al sur por la plataforma de Labrador, mientras que el agua dulce del GrIS oriental principalmente contribuye a la convección profunda en el mar de Labrador.

La interacción entre los glaciares que desembocan en el mar de Groenlandia y el océano. Se revela que tanto las aguas polares como atlánticas influyen cerca de todos los glaciares, señalando la participación del Ártico y del Atlántico en este entorno. La entrada de agua atlántica y la descarga subglacial son evidentes en los resultados, sugiriendo la influencia de estos factores en el derretimiento de los glaciares submarinos.

La contribución significativa de la Capa de Hielo de Groenlandia (GrIS) al aumento del nivel del mar es un fenómeno que ha experimentado un preocupante incremento en las últimas dos décadas. Este aumento se atribuye en parte al fenómeno de derretimiento submarino, que ha provocado la retirada acelerada de los glaciares de salida.

Diversos factores están en juego para explicar este deterioro acelerado de la Capa de Hielo de Groenlandia (GrIS). La entrada de aguas subtropicales en la región juega un papel crucial al introducir temperaturas más cálidas, contribuyendo directamente al derretimiento del hielo. Además, cambios en las condiciones atmosféricas, como patrones de viento y temperatura, también están vinculados a este fenómeno, creando un entorno propicio para el aumento del derretimiento superficial.

La variabilidad oceánica es otra variable clave en este proceso. Cambios en las corrientes oceánicas y en la distribución del calor en el Atlántico Norte subpolar han generado condiciones propicias para el derretimiento y la retirada de los glaciares de la GrIS. El aumento del contenido de calor en estas regiones contribuye a debilitar la estabilidad de la capa de hielo, acelerando así su pérdida de masa.


![intro_1](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/intro_1.jpeg)
Ilustración del espacio de ANHA4.

### Objetivos

\begin{enumerate}
    \item Estudiar los experimentos preliminares ANHA4-ELGISF003 y ANHA4-ELG019 en la configuracion ANHA4. 
    
    \item Entender los procesos oceanográficos en las regiones de Groenlandia, Mar Labrado y el Estrecho de Davis.

    \item Analizar la dinámica de la circulación oceánica en latitudes altas, con las variables de presión, temperatura y salinidad. Estudiar el impacto de las corrientes marinas en latitudes altas.
\end{enumerate}

## Fundamento teórico

La oceanografía consiste en el estudio detallado de las propiedades geológicas, biológicas, físicas y químicas de los océanos. Cuyo propósito es estudiar los procesos que tienen lugar en los mares y océanos, además de comprender la interacción de estos con el entorno circundante, como la atmósfera, la corteza terrestre, tanto por encima como por debajo del nivel del mar.

### Propiedades físicas del agua

El agua cuenta con propiedades físicas como la salinidad (s), temperatura (T) y presión (p), sus efectos sobre el comportamiento físico del agua han sido ampliamente estudiados. Sin embargo, para una mejor descripción del comportamiento físico del agua de mar, es esencial tener en cuenta otros factores, como burbujas de aire, partículas orgánicas e inorgánicas, cuyo impacto en las propiedades físicas del agua resulta difícil de cuantificar con exactitud.

### Salinidad

La salinidad, medida en gramos por kilogramo de agua de mar, indica la cantidad total de material disuelto representa la concentración global de sales disueltas, integrando la contribución combinada de iones en el agua de mar.\\

En términos simples, la salinidad se define como la masa total de material disuelto en una unidad de masa de agua de mar.

\begin{equation*}
    V_{ad} = \dfrac{S_{ref} - S}{S_{ref}} V
\end{equation*}

 donde $S_{ref} = 34.8$
 
![densidad](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/densidad.jpeg)
Calculo del volumen de agua dulce en base a la salinidad.

### Temperatura

La temperatura de un cuerpo es la medida de su estado térmico, vinculado a la energía cinética de sus moléculas constituyentes. Esta energía cinética, es la temperatura del cuerpo, que también se denomina calor. Así, la temperatura no solo señala el nivel térmico, sino que también actúa como un indicador preciso de la cantidad de energía en forma de calor que el cuerpo alberga.\\

La temperatura, representada por T, se presenta como una variable termodinámica de suma importancia en la investigación del agua de mar, siendo objeto de mediciones a lo largo de varios siglos. Incluso en el siglo XVIII, los científicos suministraban a los capitanes de barcos termómetros especializados para medir con precisión las temperaturas del subsuelo. En la actualidad, es una práctica común en oceanografía expresar la temperatura en función de la diferencia entre la temperatura absoluta y 273,15 K, que corresponde al punto de congelación del agua. Esta representación termodinámica de la temperatura se conoce como temperatura Celsius, con el símbolo $^{\circ}C$.

### Presión

La presión, es la fuerza aplicada por unidad de área, se cuantifica en el Sistema Internacional de Unidades (SI) en Pascals (Pa), equivalente a Newton por metro cuadrado (N/$m^{2}$). En el contexto del agua de mar, la presión marina se erige como una variable termodinámica fundamental. Se refiere a la fuerza neta ejercida por un gradiente de presión sobre una porción de agua. En oceanografía, la medida de presión más comúnmente empleada es la presión del mar, simbolizada como P, que representa la presión real descontando una atmósfera estándar (aproximadamente 101,325 Pa).

\begin{equation}
    \dfrac{\partial P}{\partial z} = - \rho g
\end{equation}

### Densidad

El término densidad (representado por $\rho$) se ha seleccionado para describir la cantidad de masa por unidad de volumen. En el contexto del agua de mar, los gradientes meridionales de densidad son considerados impulsores del Transporte Termohalino (THC). El aumento de la densidad en la superficie del mar, derivado de la pérdida de calor a la atmósfera o la evaporación, puede provocar una estratificación estática inestable, con el agua más densa en la parte superior.

### Circulación general oceánica

La circulación general en oceanografía se refiere al movimiento constante y global del agua en los océanos de la Tierra. Esta circulación es impulsada principalmente por fuerzas como el viento, la temperatura y la salinidad. Se pueden identificar dos componentes fundamentales en la circulación general oceánica: la circulación superficial y la circulación profunda.

\begin{itemize}
    \item \textbf{Circulación Superficial:}
        \begin{itemize}
            \item \textbf{Corrientes de Viento:} La formación de estas corrientes se debe a la fricción entre el viento y la superficie del océano. La energía transferida desde el viento hacia el agua provoca el movimiento de las capas superficiales del océano, generando corrientes oceánicas.
            
            \item \textbf{Corrientes Ecuatoriales:} 
            En la región ecuatorial, los vientos alisios impulsan el agua cálida hacia el oeste, dando origen a las corrientes ecuatoriales del este y del oeste.
        
            \item \textbf{Corrientes Costeras:} La forma de la costa y la topografía del lecho marino tienen un impacto significativo en la dirección y la velocidad de las corrientes oceánicas en estas áreas.
    
        \end{itemize}

    \item \textbf{Circulación Profunda:}
        \begin{itemize}
            \item \textbf{Corrientes Termohalinas:} La tendencia es que el agua fría y más densa tienda a descender, mientras que el agua más cálida y menos densa tiende a ascender. Este proceso conduce a la formación de corrientes termohalinas que operan a profundidades considerables y pueden extenderse a lo largo de todo el océano.
            
            \item \textbf{Cinturones de Corriente Profunda:} Estas corrientes profundas, también denominadas cinturones de transporte termohalino, establecen conexiones entre los océanos y desempeñan un papel fundamental en la redistribución global del calor y los nutrientes.
    
        \end{itemize}
    
\end{itemize}

La circulación general oceánica juega un papel clave en la regulación del clima global al transportar calor por todo el planeta y afecta la vida marina al influir en la distribución de nutrientes y la mezcla del agua. 

### Escorrentía

La escorrentía es el movimiento del agua sobre la superficie del suelo. Este proceso ocurre cuando la cantidad de agua que alcanza cierta área supera la capacidad de absorción del suelo, ya sea debido a la saturación provocada por fuertes lluvias, la fusión de nieve u otras fuentes de agua.

### Mapamundi con longitud y latitud

Las líneas de latitud y longitud son representaciones imaginarias utilizadas para indicar las coordenadas geográficas en un mapa.\\

Las líneas de latitud, también conocidas como paralelas, son líneas horizontales imaginarias que circundan la Tierra. Se miden en grados, con el Ecuador ubicado a $0^{\circ}$ de latitud y los Polos Norte y Sur a $90^{\circ}$ de latitud. Estas líneas corren paralelas entre sí.\\

Por otro lado, las líneas de longitud, también denominadas meridianos, son líneas verticales imaginarias que atraviesan la Tierra desde el Polo Norte hasta el Polo Sur. Estos meridianos van del Polo Norte al Polo Sur.\\

Utilizar un mapa del mundo con líneas de latitud y longitud es beneficioso para aprender a interpretar las coordenadas geográficas de la Tierra y calcular la distancia entre dos puntos específicos. Ver figura: \ref{mapa_mundi}



![mapa_log](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/mapa_log.jpeg)

Latitudes y longitudes sobre un mapa mundi.

### Corrientes marinas

Las corrientes oceánicas, también conocidas como corrientes marinas, constituyen el movimiento de las aguas en los océanos y, en menor medida, en mares más extensos. Su origen se atribuye a diversas causas, destacando el efecto del movimiento de rotación terrestre, que incide de manera distinta en el fondo oceánico y en la superficie.\\

En términos generales, el concepto de corrientes marinas se aplica al movimiento superficial de las aguas en los océanos y mares, como se representa en los mapas de corrientes. Contrariamente, las corrientes submarinas se consideran movimientos de compensación de las corrientes superficiales. Este fenómeno implica que, mientras en la superficie las aguas pueden desplazarse de este a oeste en la zona intertropical debido a la inercia ocasionada por el movimiento de rotación terrestre, en el fondo del océano, las aguas seguirán ese movimiento de rotación de oeste a este.\\

La compensación no solo ocurre entre la superficie y el fondo submarino, sino también en la propia superficie. Ver figura: \ref{corrientes_marinas}

![corrientes](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/corrientes.jpeg)

Corrientes marinas en el mundo.

### Series de Tiempo

Las series temporales se refieren a conjuntos de datos organizados en vectores y recopilados a lo largo del tiempo, generalmente en intervalos regulares. A diferencia de los datos muestreados de manera aleatoria, que son fundamentales en muchos otros análisis de datos, las series temporales representan la evolución en el tiempo de una población o un proceso dinámico. La disposición lineal y secuencial de estos datos les confiere una posición distintiva en el análisis de datos, y su estudio implica la aplicación de un conjunto especializado de técnicas.

### Mar de Labrador

El Mar de Labrador, ubicado en el océano Atlántico Norte, se sitúa entre la península canadiense de Labrador y la isla danesa de Groenlandia. Con una profundidad de aproximadamente 3 kilómetros, se encuentra completamente rodeado por masas continentales en todos sus límites. Su conexión hacia el norte se establece a través del estrecho de Davis, vinculándolo con las aguas de la bahía de Baffin.

### Cabo Farewell

El Cabo Farewell se erige majestuosamente en la costa sur de la isla de Egger, en Groenlandia, marcando el punto más meridional de esta impresionante isla. Se proyecta con determinación hacia el mar en la confluencia entre el océano Atlántico Norte y el mar del Labrador. Su posición geográfica coincide con la misma latitud que ciudades tan notables como Estocolmo y las islas Orcadas. Egger, junto con sus islas menores adyacentes, da forma a lo que se conoce como el archipiélago Farewell.

### Groenlandia

Groenlandia, ubicada en la zona nororiental de América del Norte, es una isla extensa entre el océano Atlántico y el océano Glacial Ártico. Políticamente constituida como una nación constituyente del Reino de Dinamarca, ha mantenido vínculos políticos y culturales con Europa Septentrional durante más de un milenio. Con una extensión de 2,175,600 $km^{2}$, se la considera la isla más grande del mundo, excluyendo la definición de Australia como masa continental.

### Estrecho de Davis

El estrecho de Davis se presenta como una impresionante vía marítima, extendiéndose entre la pintoresca costa occidental de Groenlandia y la majestuosa costa oriental de la isla de Baffin, la más grande del archipiélago ártico canadiense.


![mar_labrador](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/mar_labrador.jpeg)

![cabo_farewell](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/cabo_farewell.jpeg)

(a)Ubicación del Mar Labrador referente a Groenlandia. (b) Ubicación del Cabo Farewell referente a Groenlandia.



![groenlandia](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/groenlandia.jpeg)

![davis_strait](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/davis_strait.jpeg)

(a)Ubicación de Groenlandia. (b) Estrecho de Davis referente a Groenlandia.

La corriente marina fría del Labrador se desplaza con gracia a través del Estrecho hacia el sur, bordeando la escarpada costa de la isla de Baffin y llevando consigo fragmentos de hielo durante la mayor parte del año. En un fascinante contraste, una corriente cálida derivada de la corriente del Golfo se desplaza hacia el norte a lo largo de la majestuosa costa de Groenlandia, dominando la región que engloba las travesías marítimas clave del Estrecho.














## Experimentos y resultados

### NEMO

El "Núcleo para la modelización europea del océano" (NEMO) representa un avanzado marco de modelización que se emplea en diversas actividades de investigación y servicios de predicción en los campos de ciencias oceánicas y climáticas. Este sistema innovador es fruto de la colaboración de un consorcio europeo, cuyo propósito es asegurar la confiabilidad y sostenibilidad a largo plazo de NEMO. Su desarrollo se centra en proporcionar herramientas precisas y eficientes para entender y prever los fenómenos oceánicos y climáticos, contribuyendo así al avance del conocimiento científico.

![nemo](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/nemo.jpeg)
Núcleo para la modelización europea del océano.

Para cada uno de los trabajos se tuvo en cuenta los experimentos ANHA4-ELGISF003 y ANHA4-ELG019. Cuyos datos fueron recogidos desde el servidor SSH de wessex.


\begin{itemize}
    \item I: Un experimento de control con derretimiento de Groenlandia agregado en la superficie.\\
    /mnt/storage6/myers/NEMO/ANHA4-ELG019
    \item II: Un experimento con un porcentaje de la escorrentía de Groenlandia añadido en profundidad.\\
    /mnt/storage6/myers/NEMO/ANHA4-ELGISF003
\end{itemize}



### Experimentos
### Primer Trabajo

Trazar los campos de salinidad y temperatura para el experimento ANHA-ELGISF003, para: verano (junio - septiembre) de cada año (2002 - 2017), para el Mar de Labrador en la parte occidental. Donde las ejecuciones fueron en los niveles: 0 - 50 m.\\

Se resuelve la malla $"ANHA4 \_ mesh \_ mask \_ L75.nc"$ para los valores de longitud = $[-70, -20]$ y latitud = $[45, 70]$, siendo la parte occidental del Mar Labrador. Se extraen los valores de temperatura y salinidad de los archivos de extension NC, $[dataF\_1,CEXP\_1,'\_',timeTag,'\_gridT.nc']$ con variables $'votemper'$ y $'vosaline'$. Posteriormente se promedia el valor de cada capa entre 0 y 50m para el periodo de verano desde 2002 a 2017. Vease el codigo en  \ref{Anexo_1}.

### Segundo Trabajo

Trazar las secciones transversales de salinidad y temperatura a lo largo de la corriente de Groenlandia occidental, que se extiende hasta el mar de Labrador, para cada uno de los experimentos, para: verano (junio-septiembre) de cada año(2002 - 2017). Donde la ejecución se realizó en el nivel 0 - 6000m.\\

Se resuelve la malla $"ANHA4 \_ mesh \_ mask \_ L75.nc"$ con dominio vertical = $[0 \hspace{0.3cm} 75], [0 \hspace{0.3cm} 1]$, calculándose el valor temperatura y salinidad de cada capa entre 0 - 6000m para el periodo de verano desde 2002 a 2017. Vease el codigo en  \ref{Anexo_2}.

![level_pre](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/level_pre.jpeg)
Niveles de profundidad en ANHA4.

### Tercer Trabajo

Realizar una serie temporal de la temperatura y la salinidad integradas para la parte oeste de Groenlandia, entre el cabo Farewell y el estrecho de Davis, y cerca de la costa a 300 m de profundidad, para cada una de las dos ejecuciones: para cada mes del año (2002 - 2017).\\ 

Se resuelve la malla $"ANHA4 \_ mesh \_ mask \_ L75.nc"$ en la regionStr=$'TRC05'$ con una profundidad de 300 m extrayéndose los valores de temperatura y salinidad para cada mes desde el año 2002 al 2017. Vease el codigo en  \ref{Anexo_3}.\\

### Resultados

### Primer Trabajo

![S6](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/S6.png)
Salinidad promedio del mes de Junio en el intervalo de tiempo 2002 - 2017, a una profundidad de 0 - 50m.

![T6](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/T6.png)
Temperatura promedio del mes de Junio en el intervalo de tiempo 2002 - 2017, a una profundidad de 0 - 50m.

![S7](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/S7.png)
Salinidad promedio del mes de Julio en el intervalo de tiempo 2002 - 2017, a una profundidad de 0 - 50m.

![T7](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/T7.png)
Temperatura promedio del mes de Julio en el intervalo de tiempo 2002 - 2017, a una profundidad de 0 - 50m.

![S8](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/S8.png)
Salinidad promedio del mes de Agosto en el intervalo de tiempo 2002 - 2017, a una profundidad de 0 - 50m.

![T8](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/T8.png)
Temperatura promedio del mes de Agosto en el intervalo de tiempo 2002 - 2017, a una profundidad de 0 - 50m.

![S9](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/S9.png)
Salinidad promedio del mes de Septiembre en el intervalo de tiempo 2002 - 2017, a una profundidad de 0 - 50m.

![T9](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/T9.png)
Temperatura promedio del mes de Septiembre en el intervalo de tiempo 2002 - 2017, a una profundidad de 0 - 50m.

### Segundo y Tercer Trabajo

![deepth_S_03](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/deepth_S_03.png)
Gráfica de profundidad vs Salinidad en el experimento ANHA4-ELGISF003 para el periodo de verano entre los años 2002 - 2017.

![deepth_T_03](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/deepth_T_03.png)
Gráfica de profundidad vs Temperatura en el experimento ANHA4-ELGISF003 para el periodo de verano entre los años 2002 - 2017.

![deepth_S_03](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/deepth_S_19.png)
Gráfica de profundidad vs Salinidad en el experimento ANHA4-ELG019 para el periodo de verano entre los años 2002 - 2017.

![deepth_T_03](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/deepth_T_19.png)
Gráfica de profundidad vs Temperatura en el experimento ANHA4-ELG019 para el periodo de verano entre los años 2002 - 2017.

### Tercer Trabajo

![ST_Salinity](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/ST_Salinity.png)
Gráfica de Series de Tiempo para la Salinidad de  todos los meses del año para el periodo 2002 - 2017.

![ST_Temperature](https://github.com/M-O-R-P-H-E-U-S/Analysis-of-high-to-very-high-resolution-ocean-general-circulation-models/blob/main/ST_Temperature.png)
Gráfica de Series de Tiempo para la Temperatura de  todos los meses del año para el periodo 2002 - 2017.



\chapter{Conclusiones}


\begin{itemize}
    \item Para el experimento ANHA4-ELGISF003, las temperaturas mas bajas (-1.6$^{\circ} C$ a 0.2$^{\circ} C$) se tienen en la costa de Groenlandia y en la Bahía de Baffin debido a las corrientes del Labrador y Groenlandia. Ver graficas: \ref{T6}, \ref{T7}, \ref{T8}, \ref{T9}.  Además de mantener las zonas de menor nivel de salinidad(33S a 33.5S). Ver graficas: \ref{S6}, \ref{S7}, \ref{S8}, \ref{S9}.

    \item Para el experimento ANHA4-ELGISF003, las temperaturas mas altas se tienen en el Atlántico Norte debido a la corriente del Atlántico Norte(10.5$^{\circ} C$ a 14$^{\circ} C$). Ver graficas: \ref{T6}, \ref{T7}, \ref{T8}, \ref{T9}. Ademas de mantener las zonas de mayor nivel de salinidad(34.8S a 35.5S). Ver graficas: \ref{S6}, \ref{S7}, \ref{S8}, \ref{S9}.
    
    \item Para el experimento ANHA4-ELGISF003, se tiene el mayor nivel de salinidad(15S) se tiene a 2245m de profundidad. A la profundidad de 1106m de profundidad se tiene el mayor nivel de temperatura 1.223$^{\circ} C$. Ver graficas: \ref{deepth_S_03}, \ref{deepth_T_03}.

    \item Para el experimento ANHA4-ELG019, se tiene el mayor nivel de salinidad(15S) se tiene a 2241m de profundidad. A la profundidad de 1066m de profundidad se tiene el mayor nivel de temperatura 1.230$^{\circ} C$. Ver graficas: \ref{deepth_S_19}, \ref{deepth_T_19}

    \item En el periodo (2002-2017) se muestran los máximos y mínimos de la salinidad y temperatura, estos picos se deben a las estaciones de verano e invierno. Dichas gráficas presentan un comportamiento oscilatorio debido a la periodicidad del clima durante el año. Ver graficas: \ref{ST_Salinity}, \ref{ST_Temperature}.

\end{itemize}

