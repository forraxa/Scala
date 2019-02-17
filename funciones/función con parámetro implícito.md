## Función con parámetro implícito
Las funciones con parámetro implicito no necesitan especificar 
los atributos implicitos al momento de llamar a la función.  
Los parámetros implicitos se han de declarar antes de llamar a la función.  

Indice:
- [declarar función con parámetro implicito](#declarar-función-con-parámetro-implicito)  
- [declarar valor implícito](#declarar-valor-implícito)
- [como llamar a una funcin con parámetro implícito](#como-llamar-a-una-funcin-con-parámetro-implícito)
- [como definir una funcin con varios parametros implícitos](#como-definir-una-funcin-con-varios-parametros-implícitos)  
- [cómo pasar manualmente los parámetros implícitos](#cómo-pasar-manualmente-los-parámetros-implícitos)




### declarar función con parámetro implicito
```scala
def totalCost(donutType: String, quantity: Int)(implicit discount: Double): Double = {
  println(s"Calculating the price for $quantity $donutType")
  val totalCost = 2.50 * quantity * (1 - discount)
  totalCost
}
```

### declarar valor implícito
```scala
mplicit val discount: Double = 0.1
println(s"All customer will receive a ${discount * 100}% discount")
```


### como llamar a una funcin con parámetro implícito  
Se omite la llamada al parámetro
```scala
println(s"""Total cost with discount of 5 Glazed Donuts = ${totalCost("Glazed Donut", 5)}""")
```

### como definir una funcin con varios parametros implícitos  
Simplemente se separan por comas.
```scala
def totalCost2(donutType: String, quantity: Int)(implicit discount: Double, storeName: String):Double = {
  println(s"[$storeName] Calculating the price for $quantity $donutType")
  val totalCost = 2.50 * quantity * (1 - discount)
  totalCost
}
```

### cómo pasar manualmente los parámetros implícitos
```scala
println(s"""Total cost with discount of 5 Glazed Donuts, manually passed-through = 
         ${totalCost2("Glazed Donut", 5)(0.1, "Scala Donut Store")}""")
```
