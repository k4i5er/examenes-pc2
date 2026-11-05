# Examen Práctico Parcial: Desarrollo de Layout Responsivo Híbrido en Python con Tkinter

**Curso:** Desarrollo de Interfaces Gráficas en Python con Tkinter  
**Cobertura:** Sesiones 01 a 08 (Módulo 1: Arquitectura de Ventanas, Administradores de Geometría y Padding)  
**Duración:** 100 minutos (1 sesión de clase)  

---

## I. Ficha Técnica e Instrucciones Generales

### Objetivos a Evaluar:

1. **Gestión de Ventana Principal.
2. **Estructuración Externa:** Organización del esqueleto general de la aplicación (Encabezado, Cuerpo Central y Barra de Estado) implementando alineación, estiramiento, expansión y padding externo e interno.
3. **Maquetación Tabular Responsiva:** Construcción del área de trabajo interna mediante celdas, fusión de filas/columnas, anclaje magnético, pesos dinámicos, dimensiones mínimas de celda y aislamiento jerárquico.
4. **Posicionamiento Relativo/Flotante:** Incorporación de una tarjeta de estado o insignias flotantes mediante coordenadas relativas, anclajes y gestión del orden de profundidad.
5. **Regla de Oro de Tkinter:** Aislamiento estricto de gestores de geometría sin colisión en el mismo contenedor padre directo.

---

## II. Enunciado del Proyecto: Dashboard de Monitoreo de Estación Meteorológica

Deberás desarrollar la interfaz gráfica responsiva para un **Dashboard de Monitoreo de Estación Meteorológica**, garantizando que la distribución visual se adapte suave y simétricamente cuando el usuario cambie el tamaño de la ventana o la maximice.

```
+-------------------------------------------------------------------------------------+
| ENCABEZADO                                                                          |
+---------------------------------------+---------------------------------------------+
| PANEL LATERAL                         | ÁREA PRINCIPAL                              |
| - Filtros / Menú de Opciones          | - Tarjetas de Sensores                      |
| - Ancho protegido                     | - Tabla de Registro                         |
|                                       |   +---------------------------------------+ |
|                                       |   | INSIGNIA ALERTA                       | |
|                                       |   +---------------------------------------+ |
+---------------------------------------+---------------------------------------------+
| BARRA DE ESTADO                                                                     |
+-------------------------------------------------------------------------------------+

```

### Especificaciones Técnicas del Proyecto:

1. **Ventana Principal (`tk.Tk`):**

  * Título: `"Sistema de Monitoreo Meteorológico v1.0"`.
  * Geometría inicial: `900x600` píxeles.
  * Tamaño mínimo permitido: `750x450` píxeles.
  * Color de fondo general neutro (ej. `#f4f6f9` o `#e9ecef`).
2. **Estructura Externa:**

  * **`frame_header`:** Ubicado en la parte superior con altura fija o padding con color de fondo contrastante (ej. `#1e293b`), conteniendo un título principal (`Label` en blanco/dorado).
  * **`frame_status`:** Ubicado en la parte inferior, funcionando como barra de estado con indicador de conexión y hora.
  * **`frame_main`:** Ocupando todo el área central restante.
3. **Área Central Responsiva:**

  * **Columna 0 (Panel Lateral de Controles - `frame_sidebar`):**  
    * Ancho protegido o fijo.
  * **Columna 1 (Panel Principal de Lecturas - `frame_content`):**  
    * Absorbe todo el espacio horizontal sobrante.
    * El contenedor `frame_content` debe estar configurado para crecer verticalmente.
    * Dentro de `frame_content`, maquetar una matriz de al menos **3 tarjetas meteorológicas** (para Temperatura, Humedad y Presión) que se expandan suavemente al estirar la ventana.
4. **Widget Especial Flotante:**

  * Dentro de una de las tarjetas (ej. Tarjeta de Temperatura), agregar una **Insignia de Alerta Flotante** (`Label` con fondo rojo/amarillo y texto `"ALERTA: Alta Temp"`).
  * La insignia debe posicionarse de forma relativa para mantenerse fija en la esquina superior derecha de esa tarjeta sin importar el tamaño que adopte.
  * Utilizar `.lift()` para asegurar que la insignia flote sobre los demás elementos visuales de la tarjeta.

---
