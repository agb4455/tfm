name: Feature request
about: Sugiere una mejora o nueva funcionalidad
title: ""
labels: ["enhancement"]
assignees: ""
body:
  - type: markdown
    attributes:
      value: |
        Gracias por sugerir una mejora.

  - type: textarea
    id: problem
    attributes:
      label: ¿Qué problema resuelve?
      description: Explica el caso de uso o la necesidad que se quiere cubrir.
    validations:
      required: true

  - type: textarea
    id: proposal
    attributes:
      label: Propuesta
      description: Describe la solución propuesta.
    validations:
      required: true

  - type: textarea
    id: impact
    attributes:
      label: Impacto esperado
      placeholder: Qué cambiaría en la experiencia, arquitectura o funcionamiento.
