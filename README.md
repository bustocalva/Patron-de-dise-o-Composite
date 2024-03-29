El patrón Composite se utiliza para modelar la estructura jerárquica de una empresa, permitiendo tratar tanto a los objetos individuales (empleados) como a las composiciones de objetos (departamentos y subdepartamentos) de la misma manera. Esto proporciona flexibilidad y facilita la manipulación de la estructura de la empresa en su conjunto.


La Interfaz 'ElementoEmpresa' define el método 'mostrarDetalles()', el cual se implementará en todas las clases (Departamentos, subdepartamentos y empleados).

La clase 'Departamento' representa el departamento de una empresa, en el que recibe el nombre del departamento en el constructor. Con el método mostrarDetalles(), imprime el nombre de dicho departamento.

La clase 'Subdepartamento' representa un Subdepartamento de una empresa en el que recibe el nombre del departamento y el número identificador del mismo en el constructor. Con el método mostrarDetalles(), imprime el nombre y el número identificador. Además tiene un array 'componentes' para almacenar elementos que puede contener. Incluimos los métodos 'agregarComponentes()' y 'mostrarDetalles()', que el nombre ya indica para qué sirven.

La clase 'Empleado' tiene un constructor el cuál indica el nombre del trabajador y su puesto de trabajo. Tambíen incluye 'mostrarDetalles()' e imprime el nombre y el puesto de trabajo.

Para crear la estructura de la empresa se instancian las clases (Departamento, Subdepartamento y Empleado), donde se agregan empleados a los subdepartamentos y los subdepartamentos a los departamentos.

