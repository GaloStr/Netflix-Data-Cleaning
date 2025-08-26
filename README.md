# 🚀 Proyecto de Limpieza de Datos

¡Hola! 👋 Este es un proyecto para mostrar cómo se hace un laburo de limpieza y preparación de datos, como lo haría un analista en la vida real. La idea es agarrar un archivo crudo (`netflix1.csv`) y dejarlo listo para cualquier análisis que se nos ocurra.

---

### **1. La Estrategia: ¿Cómo Arrancamos? 🗺️**

Acá la clave es ser metódicos. La estrategia que seguimos fue esta:

* **Mirar antes de actuar:** Primero que nada, hay que inspeccionar los datos a fondo. Ver qué info tienen, si les falta algo o si hay algún dato raro. 🔍
* **Manos a la obra:** Con el panorama claro, nos pusimos a limpiar lo que hacía falta y a transformar las columnas que no nos servían como estaban. 🧹
* **Hacer crecer los datos:** Después, le agregamos más columnas al DataFrame para que sea mucho más útil. ✨

---

### **2. ¿Qué Pasó en la Limpieza? 🤔**

Acá te cuento el paso a paso del proceso, con la lógica detrás de cada decisión:

#### **La Primera Inspección**

Al arrancar, descubrimos que, aunque no había nulos "normales" (`NaN`), sí teníamos un montón de valores que decían **"Not Given"** en las columnas de **`director`** y **`country`**. ¡Eso es lo mismo que un dato que falta!

#### **La Decisión Clave sobre los Datos Faltantes** 🧠

Acá viene la parte más importante. La gran pregunta era: **¿borramos las filas con "Not Given"?** La respuesta fue un rotundo **NO**.

Si hubiéramos borrado esas filas, habríamos tirado a la basura miles de registros que sí tenían información valiosa en las otras columnas (como el título, el año de estreno, etc.). Borrarla solo para deshacernos de un dato faltante hubiera sido un error garrafal que podría haber distorsionado cualquier análisis. Por eso, lo que hicimos fue reemplazar esos valores por nulos y dejamos las filas intactas.

#### **Arreglando las Columnas que no Servían** 🔧

Después de eso, nos centramos en las columnas que estaban en un formato incómodo:

* **`date_added`:** La pasamos a un formato de fecha real, lo que nos permite hacer análisis de tiempo.
* **`duration`:** La separamos en dos columnas: una con el número y otra con la unidad (min o Season), para poder hacer cálculos sin problema.

#### **Sumando Datos Extra** ➕

Al final, hicimos un poco de "ingeniería" para que la base de datos sea más completa. Agregamos columnas como:

* **`month_added`** y **`year_added`:** Para ver cuándo se sube más contenido a la plataforma.
* **`age`:** Para saber qué tan antiguo es el contenido.
* **`is_movie`** y **`is_tv_show`:** Columnas para filtrar fácilmente entre películas y series.

---

### **3. Conclusión: ¡Proyecto Listo! 🎉**

Después de estos pasos, el DataFrame está completamente limpio, ordenado y listo para cualquier análisis que necesites hacer. La clave fue ser cuidadosos con los datos faltantes y transformar las columnas para que sean realmente útiles. ¡Listo para exportar y mostrar! 💾
