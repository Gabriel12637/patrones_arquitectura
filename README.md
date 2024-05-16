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


PATRON DE FLUJO DE TUBERIA


Un patrón de filtro de tubería se refiere a un diseño específico utilizado en la fabricación de filtros para tuberías. Estos filtros se utilizan para retener partículas sólidas, sedimentos u otros contaminantes presentes en fluidos que fluyen a través de tuberías.

El diseño del filtro de tubería puede variar según el propósito específico y las características del fluido que se está filtrando. Algunos factores a considerar en el diseño incluyen el tamaño de las partículas a filtrar, el flujo del fluido, la presión y la temperatura.

Algunos patrones comunes de filtro de tubería incluyen:

Filtro de malla: Utiliza una malla metálica o de plástico para atrapar partículas sólidas de un cierto tamaño mientras permite que el fluido pase a través de ella.

Filtro de cartucho: Consiste en un cartucho cilíndrico que contiene un medio filtrante, como papel, tela o carbono activado, que retiene las partículas a medida que el fluido pasa a través del cartucho.


Estos son solo algunos ejemplos generales, pero hay una amplia variedad de diseños de filtros de tubería disponibles para adaptarse a diferentes aplicaciones y condiciones de filtración. La selección del patrón de filtro adecuado depende de varios factores, incluidos el tamaño de las partículas a filtrar, la capacidad de flujo requerida y las características del fluido. 
  
  # Definición de funciones de filtro
def filtro_1(datos):
    for dato in datos:
        if dato % 2 == 0:
            yield dato

def filtro_2(datos):
    for dato in datos:
        if dato % 3 == 0:
            yield dato

# Datos de entrada
datos_entrada = range(1, 21)  # Números del 1 al 20

# Aplicar los filtros secuencialmente
datos_filtrados_1 = filtro_1(datos_entrada)
datos_filtrados_2 = filtro_2(datos_filtrados_1)

# Imprimir resultados
print("Datos filtrados por filtro 1:")
for dato in datos_filtrados_1:
    print(dato)

print("\nDatos filtrados por filtro 2:")
for dato in datos_filtrados_2:
    print(dato)

 El patrón de filtro de tubería en Python se utiliza para procesar datos de manera modular y eficiente, especialmente en situaciones que involucran grandes volúmenes de datos o flujos continuos de información. Puede aplicarse en casos como el procesamiento de datos en tiempo real, análisis de registros, procesamiento de secuencias de datos, transformación de datos en procesos ETL, y procesamiento de flujos de datos en redes de comunicación. Este patrón permite aplicar filtros y transformaciones de manera secuencial a los datos, facilitando la modularidad y la escalabilidad en el desarrollo de sistemas y aplicaciones.


1. Empresas tecnológicas: Gigantes como Google, Facebook y Amazon lo emplean para procesar grandes volúmenes de datos en tiempo real, como la personalización de contenido, análisis de datos de usuarios y procesamiento de transacciones.

2. Empresas financieras: Instituciones bancarias, empresas de gestión de inversiones y firmas de trading utilizan este patrón para analizar datos del mercado financiero, ejecutar algoritmos de trading y detectar fraudes en tiempo real.

3. Empresas de salud: Compañías farmacéuticas, hospitales y proveedores de atención médica emplean este patrón para procesar datos de pacientes, analizar resultados de pruebas médicas y monitorear la eficiencia operativa.

4. Empresas de comercio electrónico: Plataformas como eBay, Alibaba y Shopify lo utilizan para analizar datos de ventas, recomendar productos a los usuarios y optimizar la experiencia de compra en línea.

5. Empresas de logística y transporte: Compañías de transporte, como UPS y FedEx, utilizan este patrón para rastrear envíos, optimizar rutas de entrega y gestionar inventarios de manera eficiente.


