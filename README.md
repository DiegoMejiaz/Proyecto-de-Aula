import java.util.Scanner;

class Usuario {
    private int identificacion;
    private String name;
    private String email;
    private int edad;
    private int grado;
    String cuentaEliminar;

    public Usuario(int identificacion, String name, int edad, String email, int grado) {
        this.identificacion = identificacion;
        this.name = name;
        this.email = email;
        this.edad = edad;
        this.grado = grado;
    }

    public int getidentificacion() {
        return identificacion;
    }

    public void setidentificacion(int identificacion) {
        this.identificacion = identificacion;
    }

    public String getname() {
        return name;
    }

    public void setname(String name) {
        this.name = name;
    }

    public String getemail() {
        return email;
    }

    public void setemail(String email) {
        this.email = email;
    }

    public int getedad() {
        return edad;
    }

    public void setedad(int edad) {
        this.edad = edad;
    }

    public int getgrado() {
        return grado;
    }

    public void setgrado(int grado) {
        this.grado = grado;
    }

    public String getcuentaEliminar() {
        return cuentaEliminar;
    }

    public void setcuentaEliminar(String cuentaEliminar) {
        this.cuentaEliminar = cuentaEliminar;
    }
}

class categoria {
    private int codigoJuego;
    private String name;
    private String descripcionJuego;
    private double precio;

    public categoria(int codigoJuego, String name, String descripcionJuego, double precio) {
        this.codigoJuego = codigoJuego;
        this.name = name;
        this.descripcionJuego = descripcionJuego;
        this.precio = precio;
        
    }

    public int getcodigoJuego() {
        return codigoJuego;
    }

    public void setcodigoJuego(int codigoJuego) {
        this.codigoJuego = codigoJuego;
    }

    public String getname() {
        return name;
    }

    public void setname(String name) {
        this.name = name;
    }

    public String getdescripcionJuego() {
        return descripcionJuego;
    }

    public void setdescripcionJuego(String descrpcionJuego) {
        this.descripcionJuego = descrpcionJuego;
    }

    public double getprecio() {
        return precio;
    }

    public void setprecio(int precio) {
        this.precio = precio;
    }
}

class inscripcion {
    int id;

}

public class hola2 {

    static Scanner entrada = new Scanner(System.in);

    public static void main(String[] args) {
        Usuario[] usuarios = new Usuario[100];
        int contadorDeMiArreglo = 0;

        int opcion;
        prueba.limpiarPantalla();
        do {
            System.out.println("------INICIO------");
            System.out.println("1. Inscribirse ");
            System.out.println("2. Ver juegos: ");
            System.out.println("3. personas Inscritas");
            System.out.println("4. listar usuarios ");
            System.out.print("Seleciona la opcion: ");
            opcion = entrada.nextInt();
            limpiarPantalla();
            switch (opcion) {
                case 1:
                inscripcionJuegos(usuarios,contadorDeMiArreglo,entrada);
                    break;

                case 2:
                gestionarUsuarios(usuarios, contadorDeMiArreglo, entrada);
                    break;

                case 3:
                listarUsuarios(usuarios,contadorDeMiArreglo);
                    break;
                
                case 4:
                listarUsuarios(usuarios,contadorDeMiArreglo);
            }

        } while (true);
    }

    // Método guardar
    public static void inscripcionJuegos(Usuario[] usuarios, int contadorDeMiArreglo, Scanner entrada) {
        do{
            System.out.println("¿Desea inscribirse?");
            System.out.println("1.(SI) 2.(NO) ");
            int codigoJuego = entrada.nextInt();
            limpiarPantalla();
               switch (codigoJuego) {
                case 1:
                System.out.print("Digite su nombre completo: ");
                String name = entrada.next();
       
                System.out.print("Digite su edad: ");
                int edad = entrada.nextInt();
        
                String email;
                System.out.print("Digite el email: ");
                do {
                   email = entrada.next();
                   if (!email.contains("@")) {
                       System.out.println("Digite un email valido: ");
                   }
                } while (!email.contains("@"));
       
                System.out.print("Digite el grado que está cursando: ");
                int grado = entrada.nextInt();
       
                usuarios[contadorDeMiArreglo] = new Usuario(codigoJuego, name, edad, email, grado);
                System.out.println("Inscripcion exitosa!");
            
                break;
                case 2:
                System.out.println("Opcion no valida");
                   break;
               } 
               
            }while (true);
    }

    public static void gestionarUsuarios(Usuario[] usuarios, int contadorDeMiArreglo, Scanner entrada) {
        do {
            System.out.println("Selecciona el juego al que quieres entrar: ");
            System.out.println("1. Juego uno");
            System.out.println("2. Juego dos");
            System.out.println("3. Juego tres");
            int opcionGestion = entrada.nextInt();
            limpiarPantalla();
            switch (opcionGestion) {
                case 1:
                    if (contadorDeMiArreglo < usuarios.length) {
                       
                    }
                    break;
                case 2:
                       
                    break;

                case 3:
                      
                    break;

                case 4:
                    eliminarcuentaUsuario(usuarios, contadorDeMiArreglo, entrada);
                    break;

                default:
                System.out.println("Opcion no valida. Seleccione una opcion valida");
                    break;
            }

        } while (true);
    }



    public static void listarUsuarios(Usuario[] usuarios, int contadorDeMiArreglo) {
        System.out.println("LISTA DE USUARIO");

        for (int i = 0; i < contadorDeMiArreglo; i++) {
            System.out.println("codigoJuego: " + usuarios[i].getidentificacion());
            System.out.println("Nombre: " + usuarios[i].getname());
            System.out.println("Email: " + usuarios[i].getemail());
            System.out.println("Edad: " + usuarios[i].getedad());
            System.out.println("Grado: " + usuarios[i].getgrado());
        }
    }

    public static void modificarUsuarios(Usuario[] usuarios, int contadorDeMiArreglo, Scanner entrada) {
        System.out.println("Digite el numero de identificacion a modificar: ");
        int identificacionAmodificar = entrada.nextInt();

        for (int i = 0; i < contadorDeMiArreglo; i++) {
            if (usuarios[i].getidentificacion() == identificacionAmodificar) {
                System.out.print("Ingrese el numero de identificacion: ");
                int identificacionModificada = entrada.nextInt();

                do {
                    if (usuarios[i].getidentificacion() == identificacionModificada) {
                        System.out.println("Ingresaste la misma identificacion, ingresa una diferente: ");
                        identificacionModificada = entrada.nextInt();
                    }
                } while (usuarios[i].getidentificacion() == identificacionModificada);

                System.out.print("Ingrese el nombre: ");
                String nombreModificado = entrada.next();

                System.out.print("Ingrese el email: ");
                String emailModificado = entrada.next();

                System.out.print("Ingrese la edad: ");
                int nuevaEdad = entrada.nextInt();

                System.out.print("Ingrese el grado: ");
                int nuevoGrado = entrada.nextInt();

                System.out.println("Modificacion exitosa");

                usuarios[i].setidentificacion(identificacionModificada);
                usuarios[i].setname(nombreModificado);
                usuarios[i].setemail(emailModificado);
                usuarios[i].setedad(nuevaEdad);
                usuarios[i].setgrado(nuevoGrado);

            } else {
                System.out.println("La identificacion no se encuentra registrada");
            }
        }
    }

    public static void eliminarcuentaUsuario(Usuario[] usuarios, int contadorDeMiArreglo, Scanner entrada) {
        System.out.println("Digite la identificacion de la cuenta a eliminar: ");
        int cuentaEliminar = entrada.nextInt();
        for (int i = 0; i < contadorDeMiArreglo; i++) {
            if (usuarios[i].getidentificacion() == cuentaEliminar) {
                for (int j = i; j < contadorDeMiArreglo - 1; j++) {
                    usuarios[j] = usuarios[j + 1];
                }
                usuarios[contadorDeMiArreglo - 1] = null;
                contadorDeMiArreglo--;
                System.out.println("Cuenta eliminada");
                pausa();
            }

        }
    }

    public static void limpiarPantalla() {
        try {
            ProcessBuilder pb = new ProcessBuilder("cmd", "/c", "cls");
            Process starProcess = pb.inheritIO().start();
            starProcess.waitFor();
        } catch (Exception e) {
            System.out.println(e);
        }
    }

    // Metodo pausa
    public static void pausa() {
        entrada.nextLine();
        System.out.println("\t\nPresione enter para continuar...");
        entrada.nextLine();
    }

}

