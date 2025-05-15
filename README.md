# Venezuela-JSON

**Una completa base de datos en formato JSON con la estructura político-territorial de Venezuela: estados, municipios, ciudades y parroquias.**

Basado en el trabajo de [CodersVenezuela/Venezuela-JSON](https://github.com/CodersVenezuela/Venezuela-JSON)

[![GitHub Stars](https://img.shields.io/github/stars/CodersVenezuela/Venezuela-JSON.svg?style=social&label=Stars)](https://github.com/CodersVenezuela/Venezuela-JSON)
[![GitHub Forks](https://img.shields.io/github/forks/CodersVenezuela/Venezuela-JSON.svg?style=social&label=Forks)](https://github.com/CodersVenezuela/Venezuela-JSON)
[![GitHub Issues](https://img.shields.io/github/issues/CodersVenezuela/Venezuela-JSON.svg)](https://github.com/CodersVenezuela/Venezuela-JSON/issues)

LoboGuardian/Venezuela-JSON

[![GitHub Stars](https://img.shields.io/github/stars/LoboGuardian/Venezuela-JSON.svg?style=social&label=Stars)](https://github.com/CodersVenezuela/Venezuela-JSON)
[![GitHub Forks](https://img.shields.io/github/forks/LoboGuardian/Venezuela-JSON.svg?style=social&label=Forks)](https://github.com/CodersVenezuela/Venezuela-JSON)
[![GitHub Issues](https://img.shields.io/github/issues/LoboGuardian/Venezuela-JSON.svg)](https://github.com/CodersVenezuela/Venezuela-JSON/issues)
[![License](https://img.shields.io/github/license/LoboGuardian/Venezuela-JSON)](https://github.com/LoboGuardian/Venezuela-JSON/LICENSE)

## ¿Qué contiene?

Este repositorio proporciona archivos JSON estructurados que contienen información detallada sobre la división político-territorial de Venezuela, incluyendo:

* **Estados:** La máxima división administrativa del país.
* **Municipios:** Subdivisiones de los estados.
* **Ciudades:** Asentamientos urbanos dentro de los municipios.
* **Parroquias:** Subdivisiones de los municipios, especialmente relevantes para fines administrativos y electorales.

Cada archivo JSON está organizado de manera lógica para facilitar su uso en diversas aplicaciones y proyectos.

## Estructura de los archivos

Los datos se encuentran organizados en los siguientes archivos:

* `venezuela.json`: Contiene un objeto JSON con una clave principal "estados", cuyo valor es un array de objetos. Cada objeto representa un estado y contiene sus municipios, los cuales a su vez contienen sus ciudades y parroquias.
* `estados.json`: Contiene una lista de todos los estados de Venezuela, con información como su código y nombre.
* `municipios.json`: Contiene una lista de todos los municipios, incluyendo su código, nombre y el código del estado al que pertenecen.
* `ciudades.json`: Contiene una lista de las principales ciudades, incluyendo su código, nombre, y el código del municipio al que pertenecen.
* `parroquias.json`: Contiene una lista de todas las parroquias, incluyendo su código, nombre y el código del municipio al que pertenecen.

**Ejemplo de estructura (simplificado):**

```json
// venezuela.json
{
  "estados": [
    {
      "codigo": "VE-A",
      "nombre": "Amazonas",
      "municipios": [
        {
          "codigo": "VE-A-01",
          "nombre": "Alto Orinoco",
          "ciudades": [
            {
              "codigo": "VE-A-01-001",
              "nombre": "La Esmeralda"
            }
            // ... más ciudades de Alto Orinoco
          ],
          "parroquias": [
            {
              "codigo": "VE-A-01-01",
              "nombre": "Alto Orinoco"
            }
            // ... más parroquias de Alto Orinoco
          ]
        }
        // ... más municipios de Amazonas
      ]
    }
    // ... más estados
  ]
}
```

```json
// estados.json
[
  {
    "codigo": "VE-A",
    "nombre": "Amazonas"
  },
  // ... más estados
]

// municipios.json
[
  {
    "codigo": "VE-A-01",
    "nombre": "Alto Orinoco",
    "estado_codigo": "VE-A"
  },
  // ... más municipios
]

// ciudades.json
[
  {
    "codigo": "VE-A-01-001",
    "nombre": "La Esmeralda",
    "municipio_codigo": "VE-A-01"
  },
  // ... más ciudades
]

// parroquias.json
[
  {
    "codigo": "VE-A-01-01",
    "nombre": "Alto Orinoco",
    "municipio_codigo": "VE-A-01"
  },
  // ... más parroquias
]
```

---
## ¿Cómo utilizarlo?

Estos archivos JSON pueden ser fácilmente consumidos por una variedad de lenguajes de programación y aplicaciones. Aquí tienes algunos ejemplos de cómo podrías utilizarlos:

- **Desarrollo web**: Para poblar selectores de ubicación en formularios, mostrar mapas interactivos, etc.
- **Aplicaciones móviles**: Para ofrecer funcionalidades basadas en la ubicación.
- **Análisis de datos**: Para realizar estudios geográficos y demográficos.
- **Sistemas de información geográfica (SIG)**: Como base de datos para visualizar y analizar la división territorial.

---

### Ejemplo en Python:

```Python

import json

with open('estados.json', 'r') as f:
    estados = json.load(f)

for estado in estados:
    print(f"Código: {estado['codigo']}, Nombre: {estado['nombre']}")

```

---

## Contribuciones

¡Las contribuciones son bienvenidas! Si encuentras algún error, tienes datos más actualizados o quieres mejorar la estructura, no dudes en abrir un issue o enviar un pull request. Por favor, sigue las siguientes pautas:

1. Asegúrate de que los datos estén en formato JSON válido.
2. Mantén la estructura de los archivos consistente.
3. Describe claramente los cambios propuestos en tu pull request.

## Licencia

Este proyecto está bajo la licencia [AGPL-3.0](LICENSE) - consulta el archivo LICENSE para más detalles.

## Agradecimientos
Si utilizas este repositorio en tu proyecto, agradecería que incluyeras una mención o un enlace a este repositorio, basado en [CodersVenezuela/Venezuela-JSON](https://github.com/CodersVenezuela/Venezuela-JSON)

¡Esperamos que esta base de datos te sea de gran utilidad!
