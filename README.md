//Utilizamos el diseño de patrón Composite para crear un proyecto sobre una empresa. Para ello creamos una empresa con varios departamentos, que a su vez pueden contener varios subdepartamentos, y estos pueden contener varios empleados.

Esta es la interfaz que define las operaciones comunes para todos los componentes (Departamento, Subdepartamento y empleados)//

public interface ElementoEmpresa(){

    mostrarDetalles(): void ;
}

//Implementamos la interfaz para un Departamento//

public class Empresa implements ElementoEmpresa {
    private nombre: string;
    
    mostrarDetalles(): void {
        console.log('Departamento de $(this.nombre) y es el número: $(this.id) )
    }
}

//Implementamos la interfaz para un Subdepartamento//

public class Subdepartamento implements ElementoEmpresa {

    private componentes: ComponenteEmpresa[] = [];

    constructor(private nombre: string, private id: number) {}

    agregarComponente(componente: ComponenteEmpresa): void {
        this.componentes.push(componente);
    }
    mostrarDetalles(): void {
        console.log(`Subdepartamento: ${this.nombre}`);
        this.componentes.forEach(componente => {
            componente.mostrarDetalles();
        });
    }
}
// Implementación de la interfaz para un Empleado//
class Empleado implements ComponenteEmpresa {
    constructor(private nombre: string, private trabajo: string) {}

    mostrarDetalles(): void {
        console.log(`Empleado: ${this.nombre}, trabajo: ${this.trabajo}`);
    }
}

// Creamos  la estructura de la empresa//

const empresa = new Departamento("Empresa");
const departamentoTI = new Subdepartamento("Departamento de IT", 1);
const departamentoVentas = new Subdepartamento("Departamento de Ventas", 2);

const empleado1 = new Empleado("Nil", "Desarrollador");
const empleado2 = new Empleado("Joan", "Desarrolladora");
const empleado3 = new Empleado("Paula", "Comercial");

// Agregamos empleados a los subdepartamentos//
subdepartamentoDesarrollo.agregarComponente(empleado1);
subdepartamentoDesarrollo.agregarComponente(empleado2);
subdepartamentoSoporte.agregarComponente(empleado3);

// Agregamos subdepartamentos a los departamentos//
departamentoTI.agregarComponente(subdepartamentoDesarrollo);
departamentoTI.agregarComponente(subdepartamentoSoporte);

// Agregamos departamentos a la empresa//
empresa.agregarComponente(departamentoTI);
empresa.agregarComponente(departamentoVentas);

// Mostrar detalles de la empresa//
empresa.mostrarDetalles();





