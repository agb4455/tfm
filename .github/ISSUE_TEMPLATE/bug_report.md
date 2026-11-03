name: Bug report
about: Reporta un problema en el proyecto
title: ""
labels: ["bug"]
assignees: ""
body:
  - type: markdown
    attributes:
      value: |
        Gracias por reportar este problema.

  - type: textarea
    id: description
    attributes:
      label: Descripción del problema
      description: Explica el problema con el máximo detalle posible.
      placeholder: Qué está fallando, cuándo ocurre y qué esperabas.
    validations:
      required: true

  - type: textarea
    id: steps
    attributes:
      label: Pasos para reproducirlo
      placeholder: |
        1. Arranco el entorno
        2. Hago ...
        3. Aparece ...
    validations:
      required: true

  - type: textarea
    id: environment
    attributes:
      label: Entorno
      placeholder: |
        Sistema operativo:
        Versión de Docker:
        Rama / commit:
        Repos afectados:
    validations:
      required: true

  - type: textarea
    id: logs
    attributes:
      label: Logs / evidencia
      description: Añade mensajes relevantes, capturas o trazas.
