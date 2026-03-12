# INESData Deployment - Fork de Integración para PIONERA

Este repositorio es un fork del entorno oficial de despliegue de INESData utilizado en el proyecto PIONERA.

El propósito de este fork es dar soporte al framework Validation-Environment, que proporciona entornos experimentales reproducibles para validar componentes de espacios de datos desarrollados en PIONERA.

Este fork incluye adaptaciones necesarias para:

- automatizar flujos de despliegue
- dar soporte a entornos de validación experimental
- integrar componentes externos desarrollados dentro del ecosistema PIONERA
- habilitar experimentos reproducibles de benchmarking y validación

## Cambios respecto al repositorio base

Esta variante introduce algunas adaptaciones sobre el repositorio original de despliegue de INESData para facilitar su uso en escenarios de validación y experimentación dentro del proyecto PIONERA.

Entre los principales cambios se incluyen:

- Reorganización de la estructura del despliegue del dataspace, sustituyendo `dataspace/step-1` y `dataspace/step-2` por `dataspace/registration-service` y `dataspace/public-portal`, utilizando una nomenclatura más explícita.
- Adaptación de la generación de ficheros de configuración para dataspaces y conectores, utilizando el formato `values-<nombre>.yaml` en lugar del esquema anterior `values.yaml.<nombre>`.
- Ajustes en `deployer.py` para alinearlo con los entornos utilizados por el framework de validación, incluyendo cambios en dominios, hostnames, nombres internos y formato de salida.
- Actualización de plantillas, charts y otros ficheros versionados para reflejar la nueva organización del despliegue y su integración con el flujo experimental.

Estas modificaciones mantienen la compatibilidad con el enfoque de despliegue original de INESData, pero lo adaptan a un uso reproducible dentro del framework Validation-Environment y de los experimentos de integración desarrollados en el proyecto PIONERA.

## Financiación

This work has received funding from the **PIONERA project** (Enhancing interoperability in data spaces through artificial intelligence), a project funded in the context of the call for Technological Products and Services for Data Spaces of the Ministry for Digital Transformation and Public Administration within the framework of the PRTR funded by the European Union (NextGenerationEU).

<div align="center">
  <img src="https://raw.githubusercontent.com/ProyectoPIONERA/Validation-Environment/refs/heads/refactor/new-framework/funding_label.png" alt="Logos financiación" width="900" />
</div>

## Autores y contacto

- **Mantenedor:** Adrian Vargas
- **Contacto:** adrian.vargas@upm.es

## Licencia

Este repositorio es un fork del repositorio de despliegue de INESData.

El código original pertenece a sus respectivos autores. En el momento de crear este fork, el repositorio upstream no declara explícitamente una licencia.

Las modificaciones introducidas en este fork en el contexto del proyecto PIONERA se distribuyen bajo la Apache License 2.0. Estas modificaciones incluyen adaptaciones para la integración con el framework Validation-Environment, así como cambios orientados a escenarios de validación y experimentación en espacios de datos.

---

## Documentación original de INESData

Las secciones siguientes corresponden a la documentación del repositorio original de despliegue de INESData.

This repository contains the code for the automated deployment of elements of the Dataspaceunit platform.

It is based in Kubernetes and Helm charts.

The deployment of a working platform is divided in 3 different steps:

- Deploying the common services (Postgres Database, Minio Object Storage, Keycloak Identity Provider), which will be common
to all the platform, and will be shared by all the different deployments.
- Deploying a dataspace, which in its core is nothing more than a set of configurations for the platform and common services, 
and a public website. This deployment will be launched for every dataspace desired in the platform. 
- Deploying a connector, which is the main element that an organization will use to connect their data to the dataspace.
A complete connector is composed by the main backend service and a frontend SPA web interface.

## Requirements

- A Kubernetes cluster.
- kubectl and helm installed locally. 

## Deploying a dataspace

The dataspace wil deployed using the Helm chart in the `dataspace` folder.
Steps:
- Creating a new namespace for the dataspace.
- Create a Keycloak Realm for the dataspace.
- Deploy the public web portal.

Follow the steps provided in the file deployment-guide.txt

## Deploying a connector

The connector will be deployed using the Helm chart in the `connector` folder.

Follow the steps provided in the file deployment-guide.txt


## Disclaimer

Este trabajo ha recibido financiación del proyecto INESData (Infraestructura para la INvestigación de ESpacios de DAtos distribuidos en UPM), un proyecto financiado en el contexto de la convocatoria UNICO I+D CLOUD del Ministerio para la Transformación Digital y de la Función Pública en el marco del PRTR financiado por Unión Europea (NextGenerationEU)

