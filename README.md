using System;

namespace Tarea2_AreasYEdad
{
    class Program
    {
        // ---------- FUNCIONES (devuelven un resultado) ----------

        /// Área del triángulo: (base * altura) / 2
        static double AreaTriangulo(double baseT, double altura)
        {
            return (baseT * altura) / 2.0;
        }

        /// Área del cuadrado: lado * lado
        static double AreaCuadrado(double lado)
        {
            return lado * lado;
        }

        /// Área del círculo: pi * radio^2
        static double AreaCirculo(double radio)
        {
            return Math.PI * Math.Pow(radio, 2);
        }

        /// Retorna un mensaje según la edad recibida
        static string MensajeEdad(int edad)
        {
            if (edad < 0)
                return "Edad no válida.";
            if (edad >= 18)
                return $"Con {edad} años es MAYOR de edad.";
            else
                return $"Con {edad} años es MENOR de edad.";
        }

        // ---------- PROCEDIMIENTOS DE APOYO (usabilidad) ----------

        static void Linea()
        {
            Console.WriteLine(new string('=', 52));
        }

        static void Titulo(string texto)
        {
            Console.Clear();
            Linea();
            Console.WriteLine($"   {texto}");
            Linea();
            Console.WriteLine();
        }

        /// Lee un número positivo; repite hasta que el usuario escriba uno válido
        static double LeerPositivo(string etiqueta)
        {
            double valor;
            while (true)
            {
                Console.Write($"  {etiqueta}: ");
                string entrada = Console.ReadLine();
                if (double.TryParse(entrada, out valor) && valor > 0)
                    return valor;
                Console.WriteLine("  ⚠ Debe escribir un número mayor que 0. Intente de nuevo.");
            }
        }

        static void Pausa()
        {
            Console.WriteLine();
            Console.Write("  Presione ENTER para continuar...");
            Console.ReadLine();
        }

        // ---------- PROGRAMA PRINCIPAL ----------

        static void Main(string[] args)
        {
            // 1) Triángulo
            Titulo("CÁLCULO DE ÁREAS  ·  TRIÁNGULO");
            double b = LeerPositivo("Base");
            double h = LeerPositivo("Altura");
            double aTri = AreaTriangulo(b, h);
            Console.WriteLine();
            Console.WriteLine($"  Área del triángulo = {aTri:F2} unidades²");
            Pausa();

            // 2) Cuadrado
            Titulo("CÁLCULO DE ÁREAS  ·  CUADRADO");
            double lado = LeerPositivo("Lado");
            double aCua = AreaCuadrado(lado);
            Console.WriteLine();
            Console.WriteLine($"  Área del cuadrado = {aCua:F2} unidades²");
            Pausa();

            // 3) Círculo
            Titulo("CÁLCULO DE ÁREAS  ·  CÍRCULO");
            double radio = LeerPositivo("Radio");
            double aCir = AreaCirculo(radio);
            Console.WriteLine();
            Console.WriteLine($"  Área del círculo = {aCir:F2} unidades²");
            Pausa();

            // 4) Edad
            Titulo("VERIFICACIÓN DE EDAD");
            int edad;
            while (true)
            {
                Console.Write("  Edad: ");
                if (int.TryParse(Console.ReadLine(), out edad) && edad >= 0 && edad <= 120)
                    break;
                Console.WriteLine("  ⚠ Escriba una edad válida (0 a 120).");
            }
            Console.WriteLine();
            Console.WriteLine("  " + MensajeEdad(edad));
            Pausa();

            // Resumen final
            Titulo("RESUMEN DE RESULTADOS");
            Console.WriteLine($"  Triángulo ....... {aTri:F2} u²");
            Console.WriteLine($"  Cuadrado ........ {aCua:F2} u²");
            Console.WriteLine($"  Círculo ......... {aCir:F2} u²");
            Console.WriteLine($"  Edad ............ {MensajeEdad(edad)}");
            Console.WriteLine();
            Linea();
            Console.WriteLine("  Gracias por usar la calculadora. ¡Hasta pronto!");
            Linea();
            Console.ReadKey();
        }
    }
}