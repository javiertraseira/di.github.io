# UT4.1 Lenguajes de descripción basados en XML

## Lenguajes de marcado

El uso de la tecnología **XML** tiene un papel importante en la actualidad, ya que permite la compatibilidad entre sistemas para compartir información de manera fácil, segura y fiable. Compite en la actualidad con otros dos lenguajes como son **JSON** y **YAML**.

![](media/7fe9961d5b5db5ae41dee2d72600071e.jpeg)
![](media/eb580aa34ad2ca6abea192f9c64f4faf.png)
![](media/fa0e2328b672c6db1168f3034a532d00.png)

Cuando se trata de compartir datos **JSON** es la mejor herramienta debido a que los datos están almacenados en vectores y registros mientras que XML almacena los datos en árboles.

Con respecto a **YAML** (YAML Ain't Markup Language) su simplicidad también le otorga velocidad pero, a diferencia del JSON, no es usado para servicios web o Apis sino para archivos de configuración, depuración u otros fines en los que la facilidad de lectura juega un rol importante.

Ejemplo de un archivo **JSON**: 

    {
    "squadName": "Super herosquad",
    "homeTown": "Metro City",
    "formed": 2016,
    "members": [
    {
        "name": "MoleculeMan",
        "age": 29,
        "secretIdentity": "Dan Jukes",
        "powers": [
        "Radiationresistance",
        "Radiationblast"
        ]
    },
    {
        "name": "Madame Uppercut",
        "age": 39,
        "secretIdentity": "Jane Wilson",
        "powers": [
        "Milliontonnepunch",
        "Damageresistance",
        "Superhumanreflexes"
        ]
    },
    }


Ejemplo de un archivo **YAML**:

    network:
    version: 2
    renderer: networkd
    ethernets:
    enp3s0:
    addresses:
    -10.10.10.2/24
    nameservers:
    search: [mydomain, otherdomain]
    addresses: [10.10.10.1, 1.1.1.1]
    routes:
    -to: default
    via: 10.10.10.1


| **XML**                                                                                 | **JSON**                                                                                                     | **YAML**                                                                                                     |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| El lenguaje de marcado de información general más antiguo y extensible, pero engorroso. | Adecuados para el procesamiento de datos de un programa. Permite usar objetos.                               | No se usa para intercambio de datos. Información de texto. Proporciona facibilidad de lectura y legibilidad. |
|  Utilizado para interacción y transmisión de información en Internet.                   |  Usado en la comunicación de información entre la nube de aplicaciones móviles y el nodo no se puede anotar. |  Usado en archivos de configuración de varios sistemas.                                                      |

### Lenguaje XML

```note
💡 XML es un metalenguaje extensible de etiquetas, es decir que a partir de la definición de datos por medio de etiquetas y ciertas reglas sirve como base para definir otros lenguajes de marcas.
```

XML presenta diversos usos que ya conocemos, entre los que destacan:
-   Intercambio de información entre aplicaciones: al almacenar información mediante documentos de texto plano no se requiere software especial.
-   Computación distribuida: se trata de la posibilidad de utilizar XML para intercambiar información entre diferentes ordenadores a través de redes.
-   Información empresarial: este lenguaje tiene cada vez más importancia para generar interfaces empresariales gracias a la facilidad para estructurar los datos de la forma más apropiada para cada empresa.

Al ser XML un metalenguaje, puede ser empleado para definir otros lenguajes. Entre los más importantes actualmente se encuentran: XHTML, GML, MathML, XAML, RSS y SVG.

## Lenguajes de descripción de interfaces

Un archivo en XML no permite diseñar ni configurar una interfaz gráfica, sólo ofrecerá los datos necesarios para ser mostrados o manipulados.

Existen lenguajes basados en el estándar XML que permiten describir cómo debe ser tratada la información que contiene un documento XML para presentarla en un medio como puede ser una página web ( HTML ) o cualquier otro documento estructurado.

A continuación se llevará a cabo una descripción de algunos lenguajes de programación basados en XML:

-   XSLT (eXtensible Style Language Transformation)
-   XUL (eXtensible User interface Language)
-   XForms
-   XAML (Extensible Application Markup Language)
-   SVG (Scalable Vector Graphics)


### XSLT

XSLT (*XSL Transformations*) es un estándar de la organización *W3C* que presenta una forma de transformar documentos XML en otros tipos de documentos, incluso en formatos que no son XML.

![](media/f09dbf318afaac8b649429eddeff541b.jpeg)
![](media/f9926c775e195847ff07787706c5b397.png)

La unión de XML y XSLT ayudará al aumento de la productividad por permitir la separación de contenido y presentación gráfica.

![](media/511c83afabbae4764e4c5c06c951aeb5.jpeg)

Algunos elementos del lenguaje XSLT:

| **Elemento**     | **Significado**                                                                   |
|------------------|-----------------------------------------------------------------------------------|
| \<xsl:template\> | utilizado para asociar una plantilla con un elemento XML                          |
| \<xsl:sort\>     | utilizado para ordenar la salida                                                  |
| \<xsl:value-of\> | utilizado para extraer el valor de un nodo seleccionado                           |
| \<xsl:for-each\> | utilizado para seleccionar cada elemento XML de un conjunto de nodos especificado |
| \<xsl:if\>       | utilizado para establecer un condicional sobre un valor de un nodo o atributo     |


## XAML

**XAML** es un lenguaje de marcas empleado para la creación de interfaces en el modelo de programación *.NET Framework* de Microsoft. Las aplicaciones creadas podrán ejecutarse en entornos Windows.

XAML consta de una serie de elementos XML para representar los principales componentes gráficos, así como la distribución, paneles y manejadores de eventos. Puede hacerse programando directamente la interfaz mediante un editor de texto, o mediante el entorno de desarrollo gráfico incluido en la herramienta Expresión Blend. El código asociado a la interfaz es puramente declarativo, es decir, hace referencia tan solo al aspecto visual, pero no añade funcionalidad, salvo ciertas respuestas muy sencillas a interacciones con el usuario.

![](media/d88ceaa7ac176faa451214dbf4a2be18.jpeg)![](media/bd89f72741757520c2f4897ba47ce60a.jpeg)

## SVG

**SVG** (*Scalable Vector Graphics*) no es un lenguaje de descripción de interfaces en sí mismo, pero es un formato gráfico abierto basado en XML para crear archivos vectoriales, mediante un lenguaje de marcado por medio de etiquetas aprobado por el *W3C* y soportado por todos los navegadores actuales.

Entre sus posibilidades, podemos señalar la capacidad de usar tres tipos de objetos gráficos:

-   Formas de vectores gráficos (entre las que se incluyen líneas, polígonos, polilíneas, rectángulos, círculos o elipses, etc.).
-   Imágenes y texto.

Además, a los objetos gráficos les podemos aplicar transformaciones (traslaciones, escala, etc.), animaciones y efectos de filtro.

Un documento **SVG** sencillo consiste simplemente en un elemento raíz \<svg\> y varias formas básicas que conforman un gráfico. A partir de ahí, se puede hacer todo lo complejo que queramos.

![](media/45102ebc6c3e273b64f73bfb44a99c9b.jpeg)

-   Creación de un círculo:

        <svg><circle cx=»60″ cy=»60″ r=»60″ fill=»#FF7700″ stroke=»#333333″ stroke-width=»4″></svg>

    ![](media/d336c242a4f02af2f9f718f9a88e2362.png)


-   Creación de un rectángulo:

        <svg><rectx=»200″ y=»50″ width=»200″ height=»250″ fill=»#FF7700″ stroke=»#333333″ strokewidth=»10″ /></svg>

    ![](media/21960879fc1052354e2c02674d6172a3.png)


## Herramientas desarrollo de interfaces en XML

El principal objetivo de las herramientas es ocultar la sintaxis de los lenguajes de modelado y proporcionarles una interfaz que permita especificar adecuadamente el modelo de interfaz en los tres aspectos que hemos visto, a saber: La interfaz se almacena en un archivo de texto plano siguiendo las directrices del estándar **XML**.

Entre otras, podemos encontrar las siguientes aplicaciones de desarrollo de interfaces de **escritorio** y/o **móvil**:

-   Netbeans IDE
-   Eclipse IDE (pluggins)
-   IntelliJ IDEA
-   Scene Builder
-   Microsoft Visual Code Studio (pluggins)
-   Microsoft Blend
-   QT Designer
-   Glade
-   Android Studio

![](media/957cbfe64469f986c6a0ffa239da4e44.jpeg)