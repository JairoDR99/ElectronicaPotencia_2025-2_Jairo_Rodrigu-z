# Informe – Módulo 1: Diodos de Potencia y Rectificadores Monofásicos

## 1. Características de los Diodos de Potencia

Los diodos de potencia son dispositivos semiconductores diseñados para conducir corriente eléctrica en una sola dirección y soportar altos niveles de tensión y corriente. A diferencia de los diodos de señal, los de potencia están construidos con áreas de unión más grandes para manejar potencias mayores.

Algunas de sus principales características son:

- Alta capacidad de corriente (hasta cientos de amperios).
- Alta tensión inversa soportada (desde decenas hasta miles de voltios).
- Velocidades de conmutación adaptadas según el tipo.
- Alta eficiencia térmica.
- Uso en rectificadores, inversores y fuentes conmutadas.

## 2. Tipos de Diodos

### 2.1 Diodo de Propósito General

Este tipo de diodo se utiliza en aplicaciones donde no se requiere una rápida conmutación. Es ideal para frecuencias bajas (menos de 1 kHz), y su característica principal es su robustez. Un ejemplo típico es el **1N5408**.

**Aplicaciones:** fuentes de alimentación de baja frecuencia, equipos domésticos, rectificadores simples.

### 2.2 Diodo de Recuperación Rápida

Diseñados para operar en aplicaciones con conmutación de frecuencia media a alta. Tienen un tiempo de recuperación inversa mucho menor que los de propósito general, lo cual minimiza pérdidas de energía en la conmutación.

**Aplicaciones:** inversores, fuentes conmutadas, convertidores DC-DC.

### 2.3 Diodo Schottky

Este tipo de diodo utiliza una unión metal-semiconductor en lugar de una unión P-N. Tiene una caída de voltaje directa más baja (usualmente 0.2–0.4 V) y un tiempo de conmutación extremadamente rápido. No presenta recuperación inversa significativa.

**Aplicaciones:** rectificación en fuentes switching, protección contra inversión de polaridad, sistemas de alta frecuencia.

## 3. Diodo Freewheeling (Rueda Libre)

El diodo de rueda libre se coloca en paralelo con la carga inductiva para permitir el paso de la corriente cuando el interruptor principal se apaga. Su función es proteger el circuito contra los picos de voltaje generados por la energía almacenada en la inductancia.

**Aplicaciones típicas:**
- Motores DC
- Convertidores buck
- Relés y bobinas

## 4. Rectificadores con Diodos

### 4.1 Rectificador Monofásico de Media Onda

Este circuito permite el paso de la corriente solo durante el semiciclo positivo de la señal de entrada. Es el tipo más sencillo de rectificador, pero presenta un alto contenido armónico y una baja eficiencia.

**Ventajas:** simplicidad, bajo costo.  
**Desventajas:** alto rizado, baja eficiencia.

### 4.2 Rectificador Monofásico de Onda Completa

Puede implementarse usando:
- Transformador con derivación central y dos diodos, o
- Puente rectificador de cuatro diodos.

Convierte ambos semiciclos de la señal AC en corriente pulsante unidireccional, mejorando notablemente la eficiencia respecto a la media onda.

### 4.3 Rectificador Trifásico (opcional para adelantar)

Utiliza tres fases de entrada AC y típicamente seis diodos. Ofrece una señal de salida con menor rizado y mejor aprovechamiento de la fuente.

## 5. Parámetros de Desempeño

- **Eficiencia de conversión:** Relación entre la potencia de salida y la de entrada.
- **Tensión de rizado (ripple):** Variación de la señal DC a la salida del rectificador.
- **Caída de voltaje directa (Vf):** Tensión necesaria para que el diodo conduzca.
- **Tiempo de recuperación inversa (trr):** Tiempo que tarda el diodo en bloquear después de apagar la conducción.

## 6. Diseño de un Circuito Rectificador

Para diseñar un rectificador se deben considerar:
- Tipo de carga (resistiva, inductiva o capacitiva).
- Nivel de tensión de entrada AC.
- Frecuencia de operación.
- Requerimiento de tensión y corriente de salida.

El diseño incluye la selección del tipo de diodo, valores de los componentes pasivos, disipación térmica y condiciones de protección.

## 7. Simulaciones en LTspice

Se realizaron dos simulaciones principales:

### 7.1 Rectificador de Media Onda
**Archivo:** `rectificador_medio.asc`  
**Resultado:** Se observa conducción solo en los semiciclos positivos.  
**Imagen:** `onda_media_resultado.png`

### 7.2 Rectificador de Onda Completa
**Archivo:** `rectificador_completo.asc`  
**Resultado:** Salida unidireccional durante ambos semiciclos.  
**Imagen:** `onda_completa_resultado.png`

---

## Bibliografía

1. Rashid, M. H. *Electrónica de Potencia*. Pearson Educación, 4ª edición.
2. Mohan, N., Undeland, T., Robbins, W. *Power Electronics: Converters, Applications, and Design*. Wiley, 3rd Edition.
3. Erickson, R. W., Maksimovic, D. *Fundamentals of Power Electronics*. Springer, 2nd Edition.
