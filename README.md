
# Práctica 3: Liberación controlada de fármacos por hidrogeles

## Información del estudiante

**Alberto Villalobos** \[22212277]; l22212277@tectijuana.edu.mx

Gemelos Digitales

Ingeniería Biomédica

## Docente

Dr. Paul Antonio Valle Trujillo; paul.valle@tectijuana.edu.mx

Departamento de Ingeniería Eléctrica y Electrónica, Tecnológico Nacional de México/IT Tijuana, Blvd. Alberto Limón Padilla s/n, Tijuana, C.P. 22454, B.C., México.

## Descripción de la asignatura

La asignatura de Gemelos Digitales forma parte del plan de estudios de la carrera en Ingeniería Biomédica con la siguiente competencia general del curso: Formula el gemelo digital a través de datos experimentales para el desarrollo estrategias de control mediante teorías de sistemas dinámicos no lineales y la experimentación in silico. Esta asignatura pretende aportar al perfil del Ingeniero Biomédico la capacidad de realizar investigación científica en el área de Biología de Sistemas con la finalidad de dirigir y participar en equipos de trabajo interdisciplinarios en contextos nacionales e internacionales, así como de proporcionar soluciones informáticas para resolver problemas en el campo de la Ingeniería Biomédica con ética profesional.

En el contexto de sistemas dinámicos que describen sistemas biológicos o fisiológicos, el modelizado in silico es una extensión lógica de la experimentación in vitro controlada, es el resultado natural del gran aumento de la potencia computacional disponible a un costo que disminuye continuamente, combinando las ventajas de la experimentación in vivo e in vitro, sin someterse a las consideraciones éticas y la falta de control asociadas con los experimentos in vivo. A diferencia de los experimentos in vitro, que existen de forma aislada, los modelos in silico permiten incluir un conjunto prácticamente ilimitado de variables y parámetros, lo que hace que los resultados sean más aplicables en problemas del mundo real. La experimentación in silico ha dado lugar al paradigma denominado como "gemelos digitales" (en inglés digital twins); en esencia, los gemelos digitales son una réplica o representación digital de un proceso o sistema del mundo real, donde por replica se refiere a un modelo computacional desarrollado con base en datos experimentales y características especiales que le permiten conectar lo físico con lo virtual con el propósito de mejorar el rendimiento de un sistema, detectar y prevenir fallas, y realizar predicciones sobre su respuesta ante diferentes estímulos o escenarios de operación; una definición más formal establece que: un gemelo digital es un conjunto de modelos adaptativos que emulan el comportamiento de un sistema físico en un sistema virtual obteniendo datos en tiempo real para actualizarse a lo largo de su ciclo de vida; replica al sistema físico para predecir fallas y oportunidades de cambio, prescribir acciones en tiempo real para optimizar y/o mitigar eventos inesperados observando y evaluando el perfil operativo del sistema. En el campo particular de la Biología de Sistemas, un gemelo digital se presenta como un algoritmo o conjunto de algoritmos computacionales desarrollados con base en modelos mecanicistas de un organismo vivo, esto con el objetivo de emular su fisiología para ilustrar su dinámica en el corto y en el largo plazo, así como predecir su respuesta a diferentes estímulos endógenos y exógenos.

## Objetivo y descripción del sistema

El objetivo de esta práctica es determinar la tasa de liberación de fármacos (5-fluorouracilo) desde nanohidrogeles de PNVCL-PEGMA, utilizando datos experimentales y modelos matemáticos de regresión no lineal para caracterizar su comportamiento dinámico.

Se analizan cuatro formulaciones de hidrogeles (N45\_2MBA12, N35\_VP15, N32 y N36\_2MBA3) mediante el ajuste de cuatro modelos distintos:

1.  **Ecuación de Peppas:** Modela mecanismos de liberación por difusión y relajación de cadenas poliméricas: $X(t) = k  t^n$.
2.  **Farmacocinética de primer orden:** Describe la liberación proporcional a la cantidad de fármaco remanente: $X(t) = \beta  (1 - e^{-kt})$.
3.  **Modelo Eureqa (Función del tiempo):** Un modelo empírico basado en la raíz cuadrada del tiempo: $X(t) = \rho_1  \sqrt{t} - \rho_2  t$.
4.  **Modelo Eureqa Diferencial:** Representa la dinámica mediante una ecuación diferencial ordinaria (EDO) de primer orden:
    $$\dot{x} = \rho_1 - \rho_2x$$

Este enfoque permite identificar qué modelo describe con mayor precisión la liberación acumulada del fármaco, utilizando indicadores bioestadísticos como la R-cuadrada ordinaria y el Criterio de Información de Akaike (AICc).

**Palabras clave:** Liberación de fármacos; Hidrogeles; Regresión no lineal; Bioestadística; Experimentación in silico; EDOs.

## Actividades a realizar

1.  **Procesamiento de datos:** Carga y normalización de los datos experimentales obtenidos de la literatura para cada una de las 4 muestras de hidrogel.
2.  **Modelado matemático:** Implementación de funciones de ajuste no lineal (`fitnlm`) para los modelos de Peppas, farmacocinética y modelos empíricos.
3.  **Simulación numérica:** Integración numérica de la EDO (Modelo Eureqa Diferencial) utilizando el algoritmo `ode45`.
4.  **Análisis bioestadístico:** Evaluación de la calidad del ajuste mediante el cálculo de errores estándar (SE), intervalos de confianza (CI), valores p y criterios de información.
5.  **Visualización y comparación:** Generación de gráficos comparativos entre los puntos experimentales y las trayectorias de los modelos ajustados.

## Lista de archivos incluidos en el repositorio

1.  **Cuaderno computacional de MATLAB [.mlx]:** Código fuente con el análisis completo.
2.  **Archivo de datos [DATA.csv]:** Valores experimentales de liberación vs tiempo.
3.  **Resultados visuales [.pdf]:** Gráficas de los ajustes (Peppas\_Result, Farmaco\_Result, Eureqa\_Result, EureqaDif\_Result).
4.  **Resumen bioestadístico:** Tablas generadas en la consola de MATLAB con los parámetros óptimos.

## Referencias

\[1] P. A. Valle, Syllabus para Gemelos Digitales, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Tijuana, B.C., México, 2025. Permalink: [https://biomath.xyz/course/](https://biomath.xyz/course/)

\[2] M. A. González‐Ayón, J.A. Sañudo‐Barajas, L.A. Picos‐Corrales, & A. Licea‐Claverie, "PNVCL‐PEGMA nanohydrogels with tailored transition temperature for controlled delivery of 5‐fluorouracil", Journal of Polymer Science Part A: Polymer Chemistry, vol. 53, issue 22, pp. 2662-2672, Aug 2015. DOI: [https://doi.org/10.1002/pola.27766](https://doi.org/10.1002/pola.27766)
