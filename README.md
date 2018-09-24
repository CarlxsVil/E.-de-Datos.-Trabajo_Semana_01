# E.-de-Datos.-Trabajo_Semana_01
package figura;

import java.io.*;
import java.util.Scanner;

/**
 *
 * @author Marco
 */
public class Figura implements FiguraInterface {

    /**
     * Cuando una clase implementa una interfaz esta obliga a cumplir todos los
     * contratos de la interfaz
     */
    public static void main(String[] args) {
        Scanner entrada = new Scanner(System.in);
        // TODO code application logic here
        double area = 0;
        // tipo de dato nombre_variable = palabra reservada(new) tipo de dato(alcance)

        // instancia de la clase figura
        Figura ofigura = new Figura();

        //  Instanciando la Clase Circulo
        System.out.println("Ingrese el radio del Circulo: ");
        int radio = entrada.nextInt();
        Circulo ocirculo = new Circulo();
        ocirculo.set_Radio(radio);

        area = ofigura.CalculoArea(ocirculo);

        System.out.println("\nEl Area del Circulo es : " + area);

        // Instancias la Clase Triangulo
        System.out.println("Ingrese el lado del triangulo: ");
        double lado = entrada.nextDouble();
        System.out.println("Ingrese la base del tiangulo: ");
        double base = entrada.nextDouble();
        Triangulo oTriangulo = new Triangulo(base, lado);

        area = ofigura.CalculoArea(oTriangulo);

        System.out.println("\nEl Area del Triangulo es : " + area);

        // Instanciando la Clase Rectangulo
        System.out.println("Ingrese la base del rectangulo: ");
        double base2 = entrada.nextDouble();
        System.out.println("Ingrese la altura del rectangulo: ");
        double altura = entrada.nextDouble();
        Rectangulo oRectangulo = new Rectangulo(base2, altura);

        area = ofigura.CalculoArea(oRectangulo);
        System.out.println("\nEl Area del Rectangulo es: " + area);
        
        //Instanciando la Clase Cuadrado
        System.out.println("Ingrese el lado del cuadrado");
        double lado3 = entrada.nextDouble();
        Cuadrado oCuadrado = new Cuadrado(lado3);
        
        area = ofigura.CalculoArea(oCuadrado);
        System.out.println("\nEl area del Cuadrado es: " + area);

        // Los Datos de Entrada que se ingresen desde teclado.
        // Completar para el area del rectangulo.
    }

    // 
    public double CalculoArea(Object obj) {
        double area = 0;

        //System.out.println(obj.getClass().getSimpleName());
        switch (obj.getClass().getSimpleName()) {
            case "Circulo":
                // convierte el objeto obj recibido por parametro 
                // en la clase instaciada circulo.
                Circulo oCirculo = (Circulo) obj;

                area = Circulo.PI * Math.pow(oCirculo.get_Radio(), 2);

                break;

            case "Triangulo":

                Triangulo oTriangulo = (Triangulo) obj;

                area = oTriangulo.GetBase() * oTriangulo.GetAltura() / 2;

                break;

            case "Rectangulo":

                Rectangulo oRectangulo = (Rectangulo) obj;

                area = oRectangulo.GetBase() * oRectangulo.GetAltura();
                break;

            case "Cuadrado":

                Cuadrado oCuadrado = (Cuadrado) obj;

                area = oCuadrado.GetLado() * oCuadrado.GetLado();

        }

        return area;
    }

}
