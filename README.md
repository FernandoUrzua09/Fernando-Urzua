// Conversión de Fechas
import java.time.LocalDate;
import java.util.Scanner;

public class ConversionFechas {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Ingrese una fecha en formato YYYY-MM-DD: ");
        String fechaInput = scanner.nextLine();

        try {
            LocalDate fecha = LocalDate.parse(fechaInput);
            LocalDate unaSemanaDespues = fecha.plusWeeks(1);
            LocalDate unMesAntes = fecha.minusMonths(1);

            System.out.println("Fecha una semana después: " + unaSemanaDespues);
            System.out.println("Fecha un mes antes: " + unMesAntes);
        } catch (Exception e) {
            System.out.println("Formato de fecha inválido.");
        }
    }
}

// Comparación de Cadenas
import java.util.Scanner;

public class ComparacionCadenas {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingrese la primera cadena: ");
        String cadena1 = scanner.nextLine();
        System.out.print("Ingrese la segunda cadena: ");
        String cadena2 = scanner.nextLine();

        if (cadena1.length() == cadena2.length()) {
            System.out.println("Ambas cadenas tienen la misma longitud.");
        } else {
            System.out.println("Las cadenas tienen longitudes diferentes.");
        }

        if (cadena1.equals(cadena2)) {
            System.out.println("El contenido de ambas cadenas es igual.");
        } else {
            System.out.println("El contenido de las cadenas es diferente.");
        }
    }
}

// Manipulación de Texto
import java.util.Scanner;

public class ManipulacionTexto {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingrese un texto largo: ");
        String texto = scanner.nextLine();

        String palabra = "ingeniería";
        String textoMinusculas = texto.toLowerCase();
        int contador = 0;

        int index = textoMinusculas.indexOf(palabra);
        while (index != -1) {
            contador++;
            index = textoMinusculas.indexOf(palabra, index + 1);
        }

        System.out.println("La palabra 'ingeniería' aparece " + contador + " veces en el texto.");
    }
}

// Convertir Nombres
import java.util.Scanner;

public class ConvertirNombres {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.print("Ingrese un nombre completo en minúsculas (o escriba 'salir' para terminar): ");
            String input = scanner.nextLine();

            if (input.equalsIgnoreCase("salir")) {
                break;
            }

            String[] palabras = input.split(" ");
            StringBuilder nombreFormatoTitulo = new StringBuilder();

            for (String palabra : palabras) {
                if (!palabra.isEmpty()) {
                    nombreFormatoTitulo.append(Character.toUpperCase(palabra.charAt(0)))
                            .append(palabra.substring(1).toLowerCase())
                            .append(" ");
                }
            }

            System.out.println("Nombre en formato título: " + nombreFormatoTitulo.toString().trim());
        }
    }
}
