# 🛠️ Prueba de Carga - Servicio de Autenticación (Login)

Este repositorio contiene los artefactos oficiales y la solución técnica para el **Ejercicio 1** correspondiente a la evaluación de desempeño y automatización de pruebas de carga sobre el servicio de login de `FakeStoreAPI`.

---

## 1. Requisitos y Versiones de Tecnologías

Para reproducir y ejecutar este plan de pruebas de manera idéntica, asegúrese de contar con el siguiente entorno configurado:
* **Sistema Operativo:** Windows 10 / 11 (compatible con Linux y macOS)
* **Java Runtime Environment (JRE):** Java 11 o superior (Recomendado Java 17)
* **Herramienta de Pruebas:** Apache JMeter `5.6.3`

---

## 2. Estructura de Archivos en el Repositorio

El proyecto se encuentra organizado con la siguiente estructura de componentes básicos:

* 📄 `"Plan de Pruebas - Fakestore Service Load Test.jmx"`: Script principal optimizado en Apache JMeter que contiene la lógica de hilos, temporizadores y aserciones.
* 📄 `usuarios.csv`: Archivo de datos externo parametrizado que almacena las credenciales de prueba (`user`, `passwd`).
* 📄 `resultados_evaluacion.jtl`: Archivo de bitácora o log de resultados en bruto generado automáticamente tras la ejecución.
* 📁 `reporte-html/`: Carpeta autogenerada que aloja el Dashboard interactivo y las gráficas web del comportamiento del sistema (Abrir `index.html`).
* 📄 `conclusiones.txt`: Informe ejecutivo con el análisis técnico de los Acuerdos de Nivel de Servicio (SLAs).
* 📄 `README.md`: Este manual explicativo de instrucciones paso a paso.

---

## 3. Instrucciones Paso a Paso para la Ejecución

### Paso 1: Clonar el repositorio
Abra una terminal en su máquina local y clone el proyecto utilizando Git:
```bash
git clone <URL_DE_TU_REPOSITORIO_GITHUB>
cd <NOMBRE_DEL_REPOSITORIO>
```

##Paso 2:Validación del archivo de datos

Verifique que el archivo usuarios.csv permanezca ubicado exactamente en la misma carpeta que el archivo .jmx. El elemento Configuración del CSV Data Set dentro de JMeter utiliza una ruta relativa para garantizar la portabilidad del script en cualquier entorno.


##Paso 3: Ejecución en Modo CLI (Línea de Comandos)

Por buenas prácticas de performance testing, la inyección de carga debe realizarse estrictamente sin interfaz gráfica (No-GUI) para evitar el consumo innecesario de recursos (CPU/RAM) en la máquina local.

Ejecute el siguiente comando exacto en su consola de Windows (cmd), asegurándose de apuntar a la ruta correcta de su ejecutable de JMeter:
```bash
"C:\Users\pablo\Downloads\apache-jmeter-5.6.3\apache-jmeter-5.6.3\bin\jmeter" -n -t "Plan de Pruebas - Fakestore Service Load Test.jmx" -l resultados_evaluacion.jtl -e -o reporte-html
```

📌 Desglose de las Banderas del Comando:

-n : Activa el modo No-GUI (CLI) de JMeter.

-t : Ruta absoluta o relativa del script de pruebas a ejecutar (.jmx).

-l : Nombre del archivo de salida para almacenar las métricas de respuesta en bruto (.jtl).

-e : Indica a JMeter que procese y compile un reporte gráfico HTML al finalizar la prueba.

-o : Define la carpeta de destino donde se estructurará el Dashboard (reporte-html).

##Paso 4: Visualización de Resultados

Una vez finalizada la ejecución en la consola (marcando el mensaje ... end of run), ingrese al directorio reporte-html/ de este repositorio y abra el archivo index.html para desplegar el panel interactivo en su navegador web.
```bash
reporte-html/
└── index.html  <-- Abrir en el navegador
```bash
