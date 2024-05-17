# patrones arquitectonicos
>[!NOTE]
> un 👽**patron  arquitectonico** es una  👻solucion general y
👾reutilizable a un problema comun en la arquitectura de software 
dentro de un contexto dado.los patrones arquitectonicos 
son la habilidad de organizacion de nivel de carpeta dentro del proyecto de software

PATRONES ARQUITECTONICOS MAS CONOCIDOS
1. PATRON DE CAPAS
2. PATRON CLIENTE-SERVIDOR
3. PATRON MAESTRO-ESCLAVO
4. PATRON FILTRO DE TUBERIA
5. PATRON DE INTERMEDIARIO
6. PATRON DE IGUAL A IGUAL
7. PATRON DE BUS EVENTO
8. MODELO-VISTA-CONTROLADOR
9. ARQUITECTURA LIMPIA
10. ARQUITECTURA HEXAGONAL


PATRON DE filtro DE TUBERIA


 El patrón de filtro de tubería, también conocido como patrón de filtro de tubería y filtro, es un patrón de diseño que se utiliza comúnmente en el desarrollo de software. Este patrón se utiliza para procesar datos secuenciales de manera eficiente y modular, dividiendo el proceso en etapas o filtros que se aplican secuencialmente a los datos.

La idea básica detrás del patrón de filtro de tubería es tener una serie de componentes llamados "filtros", cada uno de los cuales realiza una operación específica en los datos que pasan a través de él. Estos filtros están conectados entre sí formando una tubería, donde la salida de un filtro se convierte en la entrada del siguiente.

Los principales beneficios de este patrón incluyen:

Modularidad: Cada filtro es independiente y puede ser reutilizado o modificado sin afectar a otros componentes de la tubería.

Facilidad de mantenimiento: Los cambios en el proceso de filtrado se pueden realizar fácilmente añadiendo, eliminando o modificando filtros individuales.

Escalabilidad: Se pueden agregar nuevos filtros para ampliar la funcionalidad sin necesidad de reescribir el código existente.

Por ejemplo, en el procesamiento de imágenes, se podría implementar una tubería de filtro para realizar operaciones como ajuste de contraste, filtrado de ruido y detección de bordes, donde cada filtro realizaría una de estas tareas en la imagen.

La implementación del patrón de filtro de tubería puede variar según el lenguaje de programación y el contexto específico del problema a resolver, pero en general, implica la creación de clases o funciones para cada filtro y una forma de conectarlos entre sí para formar la tubería.



class FiltroBase:
    def __init__(self):
        pass
    
    def aplicar(self, datos):
        raise NotImplementedError()

class FiltroEliminarCaracteresEspeciales(FiltroBase):
    def aplicar(self, datos):
        return ''.join(c for c in datos if c.isalnum() or c.isspace())

class FiltroConvertirMinusculas(FiltroBase):
    def aplicar(self, datos):
        return datos.lower()

class FiltroEliminarPalabrasVacias(FiltroBase):
    def __init__(self, palabras_vacias):
        self.palabras_vacias = palabras_vacias
    
    def aplicar(self, datos):
        return ' '.join(word for word in datos.split() if word.lower() not in self.palabras_vacias)

def aplicar_filtro_tuberia(datos, filtros):
    resultado = datos
    for filtro in filtros:
        resultado = filtro.aplicar(resultado)
    return resultado

texto = "¡Hola, mundo! Este es un ejemplo de texto. Contiene palabras vacías como 'es' y 'un'."
filtros = [
    FiltroEliminarCaracteresEspeciales(),
    FiltroConvertirMinusculas(),
    FiltroEliminarPalabrasVacias(['es', 'un'])
]
resultado = aplicar_filtro_tuberia(texto, filtros)
print(resultado)




El patrón de filtro de tubería es un concepto de diseño de software más que una herramienta o tecnología específica, por lo que es utilizado por empresas en una variedad de sectores y contextos de desarrollo de software. Aquí hay algunas empresas y organizaciones que podrían estar utilizando este patrón:

1. Empresas tecnológicas: Gigantes como Google, Facebook y Amazon lo emplean para procesar grandes volúmenes de datos en tiempo real, como la personalización de contenido, análisis de datos de usuarios y procesamiento de transacciones.

2. Empresas financieras: Instituciones bancarias, empresas de gestión de inversiones y firmas de trading utilizan este patrón para analizar datos del mercado financiero, ejecutar algoritmos de trading y detectar fraudes en tiempo real.

3. Empresas de salud: Compañías farmacéuticas, hospitales y proveedores de atención médica emplean este patrón para procesar datos de pacientes, analizar resultados de pruebas médicas y monitorear la eficiencia operativa.

4. Empresas de comercio electrónico: Plataformas como eBay, Alibaba y Shopify lo utilizan para analizar datos de ventas, recomendar productos a los usuarios y optimizar la experiencia de compra en línea.

5. Empresas de logística y transporte: Compañías de transporte, como UPS y FedEx, utilizan este patrón para rastrear envíos, optimizar rutas de entrega y gestionar inventarios de manera eficiente.


