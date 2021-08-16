# Infrastructure as Code (IaC)
> **Enfoque para la automatización y aprovisionamiento de infraestructura basada en practicas de desarrollo de software**

## Principios y Practicas Generales IaC
Dado que los sistemas cambian constantemente IaC tiene algunos principios:
* La infraestrucutra de ser facilmente reproducibles,desechables, consistente (no hay intervencion humana) y repetible.

Algunas buenas practicas son:
* usar archivos de definición, procesos autodocuemntados (multiples persinas usaran el código), versionar y realizar cambios pequeños para impactar en lo mas minimo la disponibilidad del servicio

Beneficios al usar IaC:
* Creación rapido on-demand
* Automatización, CI (Despliegue automatico al entregar cambios)
* Visibilidad y trazabilidad (Registro cambios a través del versionamiento)
* Recrear ambientes homogéneos y parametrizables
* Facil de testear

## terraform
[Desarrollada en Go por Hashicorp](https://www.terraform.io/) iteractua directamente con APIs del [proveedor](https://www.terraform.io/docs/language/providers/index.html) de infraestructura.