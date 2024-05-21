# Despliegue de la Aplicación Pokedex en la Nube

Este documento proporciona una guía paso a paso para desplegar la aplicación Pokedex en la nube utilizando Microsoft Azure, directamente desde el portal de Azure.

## Prerrequisitos

Antes de comenzar, asegúrate de tener los siguientes elementos:

1. Una cuenta en [Microsoft Azure para Estudiantes](https://azure.microsoft.com/en-us/free/students).
2. La aplicación Pokedex lista para ser desplegada en un archivo comprimido (zip).
3. Azure CLI instalado. Puedes descargarlo desde [aquí](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli).

## Paso 1: Crear una Cuenta en Azure para Estudiantes

1. Abre tu navegador web y dirígete a [Azure para Estudiantes](https://azure.microsoft.com/en-us/free/students).
2. Haz clic en **"Activate"** para iniciar el proceso de registro.
3. Inicia sesión con tu cuenta de estudiante (usualmente una cuenta de correo electrónico proporcionada por tu institución educativa).
4. Sigue las instrucciones en pantalla para completar el registro. Esto puede incluir la verificación de tu identidad mediante un código enviado a tu correo electrónico.

## Paso 2: Iniciar Sesión en el Portal de Azure

1. Una vez que tu cuenta esté activada, inicia sesión en el [Portal de Azure](https://portal.azure.com/).

## Paso 3: Crear un Grupo de Recursos

1. En el portal de Azure, selecciona **"Resource groups"** en el menú de la izquierda.
2. Haz clic en **"Add"** para crear un nuevo grupo de recursos.
3. Ingresa un nombre para tu grupo de recursos, como `PokedexResourceGroup`.
4. Selecciona tu región preferida, por ejemplo, `East US`.
5. Haz clic en **"Review + Create"** y luego en **"Create"**.

## Paso 4: Crear un Plan de Servicio de App

1. En el portal de Azure, selecciona **"App Services"** en el menú de la izquierda.
2. Haz clic en **"Create"**.
3. Selecciona **"Web App"**.
4. Completa los detalles de la aplicación:
    - **Subscription**: Selecciona tu suscripción de Azure para Estudiantes.
    - **Resource Group**: Selecciona `PokedexResourceGroup`.
    - **Name**: Ingresa un nombre único para tu aplicación, como `NombreDeTuAppPokedex`.
    - **Publish**: Selecciona `Code`.
    - **Runtime Stack**: Selecciona `Python 3.8`.
    - **Region**: Selecciona `East US` u otra región preferida.
5. Haz clic en **"Review + Create"** y luego en **"Create"**.

## Paso 5: Subir la Aplicación a Azure

1. Una vez que la aplicación se haya creado, ve a la página de tu aplicación en el portal de Azure.
2. En el menú de la izquierda, selecciona **"Advanced Tools"** y luego haz clic en **"Go"**.
3. Esto abrirá la herramienta Kudu en una nueva pestaña. En Kudu, selecciona la pestaña **"Debug console"** y luego **"CMD"**.
4. Navega hasta el directorio `site/wwwroot`.
5. Sube tu archivo zip que contiene la aplicación Pokedex utilizando la opción de subir archivo en la parte superior.
6. Una vez subido, extrae el contenido del archivo zip directamente en `site/wwwroot`.

## Paso 6: Configurar las Variables de Entorno

1. En la página de tu aplicación en el portal de Azure, selecciona **"Configuration"** en el menú de la izquierda.
2. En la pestaña **"Application settings"**, haz clic en **"New application setting"**.
3. Agrega las variables de entorno necesarias para tu aplicación Pokedex.
4. Haz clic en **"Save"** para guardar los cambios.

## Paso 7: Verificar el Despliegue

1. Después de que Azure complete el despliegue, puedes verificar que tu aplicación esté funcionando correctamente accediendo a la URL
