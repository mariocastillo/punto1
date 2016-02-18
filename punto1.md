# punto1
Point 1 

List, Set and Map are interfaces which implements collection interface. The difference between theme are these: 
Duplicity: -List allow to duplicate elements 
-Set doesn’t allow duplicates. 
-Map stored elements as key & value pair. Map doesn’t support duplicate keys but allows duplicate values.

Order: -List maintain the insertion order. 
-Set doesn’t maintain any order; still few classes like linkedhashset maintain the elements insertion order. 
-Map doesn’t maintain order; still few classes like linkedhashmap sorts the elements in the insertion order.

Ejemplos :
-Los maps se suelen utilizar cuando el programador sabe que tiene de un arreglo de datos muy grandes y tiene que estar sacando datos especificos todo el tiempo.  ejemplo:
en una compañia hay 10000000 de usuarios los cuales estan en un map el cual tiene el id del usuario como "key" y un array de valores como "value". Para buscar un usuario en map es muy facil ya que solo tiene que pedir el id del usuario para ingresar a la informacion, en cambio si fuera una lista o un set tendria que recorrer la lista hasta encontrar el id del usuario, lo cual es muy ineficiente en terminos de codigo.

- en la misma compañia se quiere sacar el promedio de edad de todos los usurios en la base de datos. para este ejemplo seria mejor utilizar una lista ya que tiene que recorrer uno a uno todos los elementos lo cual es mas eficiente para listas , este ejemplo tambien se podria utilizar para set.

-una empresa tiene un sistema de notificacion de fallos, pero estos fallos se suelen repetir antes de que el soporte tecnico llegue a repararlos. Para este ejemplo seria ideal utilizar set ya que no permite duplicados en las listas, por lo cual seria mas eficiente en terminos de memoria que si se utlizara List and Map.



////List Example 
//ejemplo de como se utiliza en java

import java.util.*;

public class CollectionsDemo {

   public static void main(String[] args) {
      List a1 = new ArrayList();
      a1.add("Zara");
      a1.add("Mahnaz");
      a1.add("Ayan");
      System.out.println(" ArrayList Elements");
      System.out.print("\t" + a1);

      List l1 = new LinkedList();
      l1.add("Zara");
      l1.add("Mahnaz");
      l1.add("Ayan");
      System.out.println();
      System.out.println(" LinkedList Elements");
      System.out.print("\t" + l1);
   }
}



//Set example
//ejemplo de como se utiliza en java

import java.util.*;

public class SetDemo {

  public static void main(String args[]) { 
     int count[] = {34, 22,10,60,30,22};
     Set<Integer> set = new HashSet<Integer>();
     try{
        for(int i = 0; i<5; i++){
           set.add(count[i]);
        }
        System.out.println(set);
  
        TreeSet sortedSet = new TreeSet<Integer>(set);
        System.out.println("The sorted list is:");
        System.out.println(sortedSet);

        System.out.println("The First element of the set is: "+
                          (Integer)sortedSet.first());
        System.out.println("The last element of the set is: "+
                        (Integer)sortedSet.last());
     }
     catch(Exception e){}
  }
} 

// Map example
//ejemplo de como se utiliza en java


import java.util.HashMap;
import java.util.Map;

public class HashMapExample {
	
	public static void main(String[] args) {
		Map vehicles = new HashMap();
		
		// Add some vehicles.
		vehicles.put("BMW", 5);
		vehicles.put("Mercedes", 3);
		vehicles.put("Audi", 4);
		vehicles.put("Ford", 10);
		
		System.out.println("Total vehicles: " + vehicles.size());
		
		// Iterate over all vehicles, using the keySet method.
		for(String key: vehicles.keySet())
			System.out.println(key + " - " + vehicles.get(key));
		System.out.println();
		
		String searchKey = "Audi";
		if(vehicles.containsKey(searchKey))
			System.out.println("Found total " + vehicles.get(searchKey) + " "
					+ searchKey + " cars!\n");
		
		// Clear all values.
		vehicles.clear();
		
		// Equals to zero.
		System.out.println("After clear operation, size: " + vehicles.size()); 
	}
}
