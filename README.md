# SIMULACRO III DE CONSULTAS SOL - BASES DE DATOS


1. Muestra todas las piezas que sean de color rojo.

Select * from piezas where color = "rojo";

2. Muestra todos los proveedores que estén ubicados en la ciudad de 'Madrid'.

Select  * from proveedores where ciudad_proveedor= "Madrid";

3. Muestra el nombre de la pieza más pesada.

Select max(Peso), nombre_proveedor from piezas;

4. Muestra el nombre del proveedor que suministra la mayor cantidad de piezas diferentes.

Select nombre_proveedor from proveedores inner joinpiezas on proveedor.id_proveedor = piezas.id_proveedor having count(id_pieza) > (Select Distint count(id_pieza) from piezas group by id_proveedor) group by id_proveedor LIMIT 1;

5. Saca todos los proveedores que suministren al menos una pieza de color azul.

Select * from proveedores inner join piezas on preovedores.id_proveedor = piezas.id_proveedor where color= "azul";

6. Visualiza el nombre de la pieza más ligera que es suministrada por el proveedor
'Proveedor A'.

Select * from piezas inner join proveedores on piezas.id_proveedor = proveedores.id_proveedor  where peso = min(peso) and nombre_proveedor = "Proveeddor A";

7. Saca el nombre del proveedor que suministra la pieza más pesada.

Select nombre_proveedor from proveedores inner joinpiezas on proveedor.id_proveedor = piezas.id_proveedor where peso => (Select peso from piezasr) LIMIT 1;

8. Muestra todas las piezas que sean suministradas por proveedores de la ciudad de
Barcelona'.

Select * from piezas inner join proveedores on piezas.id_proveedor = proveedores.id_proveedor  where  where ciudad_proveedor= "Barcelona";


9. Muestra el nombre del proveedor que suministra la mayor cantidad de piezas de color verde.

Selectnombre_proveedor from proveedores  where color = "verde" and having count(id_pieza)> (Select count(id_pieza) from piezas where color = "verde" group by id_proveedor) group byu id_proveedor;

10. Muestra el nombre de la pieza más pesada que es suministrada por un proveedor de la ciudad de Valencia.

Select nombre_pieza from piezas inner join proveedores on piezas.id_proveedor = proveedores.id_proveedor  where  where ciudad_proveedor= "valeencia" and peso = max(peso);
