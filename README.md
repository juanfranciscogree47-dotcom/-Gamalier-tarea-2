# Tarea 2 - Áreas y mayoría de edad

**Nombre:** Juan Francisco Green Basora
**Matrícula:** 26-ESON-2-008
**Asignatura:** Programación
**Lenguaje:** C# (.NET)

## Descripción

El programa pide al usuario los datos necesarios y calcula el área de un triángulo,
de un cuadrado y de un círculo, además de indicar si una persona es mayor o menor
de edad. Cada cálculo está hecho dentro de su propia función y al final se muestra
un resumen con todos los resultados.

## Funciones

- **AreaTriangulo(base, altura):** calcula el área del triángulo con la fórmula base × altura / 2.
- **AreaCuadrado(lado):** calcula el área del cuadrado multiplicando el lado por sí mismo.
- **AreaCirculo(radio):** calcula el área del círculo usando 3.14 × radio × radio.
- **MensajeEdad(edad):** devuelve un mensaje indicando si la persona es mayor de edad (18 años o más) o menor de edad.

## Ejemplos de ejecución

| Cálculo | Datos de entrada | Resultado |
| --- | --- | --- |
| Área del triángulo | base 10, altura 5 | 25 |
| Área del cuadrado | lado 4 | 16 |
| Área del círculo | radio 3 | 28.26 |
| Mayoría de edad | edad 20 | La persona es mayor de edad |
| Mayoría de edad | edad 15 | La persona es menor de edad |

## Cómo ejecutar

1. Abrir la carpeta del proyecto en Visual Studio.
2. Ejecutar el programa con F5.
3. Digitar los datos que pide la consola.