# Proyecto: Limpieza y Preparación de Datos

¡Hola! Este es un proyecto simple para mostrar cómo se hace un trabajo de limpieza y preparación de datos, como lo haría un analista de verdad. El objetivo es tomar una base de datos en crudo (el archivo `netflix1.csv`) y dejarla impecable, lista para cualquier análisis.

---

### **1. La Estrategia: ¿Cómo Arrancamos?**

Acá la clave es ir con un plan claro. Lo que hicimos fue:

* **Mirar antes de actuar:** Primero que nada, hay que inspeccionar los datos a fondo. Ver qué tienen, si les falta algo o si hay algún dato raro que no nos sirva.
* **Arreglar el lío:** Con el panorama claro, nos pusimos a limpiar lo que hacía falta y a transformar las columnas que no estaban en el formato correcto.
* **Sumar valor:** Después de la limpieza, le agregamos más columnas a los datos para que sean mucho más útiles.

---

### **2. Lo que Pasó en la Limpieza: Paso a Paso**

Acá te cuento lo más importante que hicimos, con la lógica detrás de cada decisión:

#### **Paso 1: La Primera Inspección**

Cargamos el archivo y le pasamos el `info()` y `describe()` de Pandas para entender todo. Ahí nos dimos cuenta de algo clave: aunque no había nulos "normales" (`NaN`), sí teníamos un montón de valores que decían **"Not Given"** en las columnas de **`director`** y **`country`**. ¡Eso es lo mismo que un dato que falta!

#### **Paso 2: La Decisión de Oro sobre los Datos Faltantes**

Esta fue la parte más importante. La gran pregunta era: **¿borramos las filas con "Not Given"?** La respuesta fue un rotundo **NO**.

Si hubiéramos borrado esas filas, habríamos perdido una cantidad ENORME de información. Por ejemplo, aunque el nombre del director o el país no estaban, el resto de la información (el título, el año de estreno, etc.) en esas filas sigue siendo valiosísima. Borrarla solo para deshacernos de un `NaN` habría sido un error garrafal que podría haber arruinado cualquier análisis. Por eso, lo que hicimos fue reemplazar esos valores por `np.nan` y dejamos las filas intactas.

#### **Paso 3: Arreglando las Columnas**

Después de eso, nos centramos en las columnas que estaban en un formato incómodo:

* **`date_added`:** La pasamos al formato de fecha real (`datetime`), lo que nos permite hacer análisis sobre el tiempo.
* **`duration`:** La separamos en dos columnas: una con el número (`duration_value`) y otra con la unidad (min o Season), para poder hacer cálculos.

#### **Paso 4: Sumando Datos Extra**

Al final, hicimos un poco de "ingeniería" para que la base de datos sea más completa. Agregamos columnas como:

* **`month_added`** y **`year_added`:** Para ver cuándo se sube más contenido a la plataforma.
* **`age`:** Para saber qué tan antiguo es el contenido.
* **`is_movie`** y **`is_tv_show`:** Columnas para filtrar fácilmente si un título es una película o una serie.

---

### **3. Conclusión**

Después de estos pasos, el DataFrame `df1` está completamente limpio y listo para cualquier análisis. La clave fue ser cuidadosos con los datos faltantes y transformar las columnas para que sean realmente útiles. ¡Proyecto listo para mostrar!
