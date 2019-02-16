## Funciones con parámetros

Indice:  
- [Como definir una función con parámetros](#Como-definir-una-función-con-parámetros)  
- [Como llamar a una función con parámetros](#Como-llamar-a-una-función-con-parámetros)  
- [Como agregar valores por defecto a los parámetros](#Como-agregar-valores-por-defecto-a-los-parámetros)    
- [Como llamar a una función con parámetros por defecto](#Como-llamar-a-una-función-con-parámetros-por-defecto)  


### Como definir una función con parámetros
```scala
def calculateDonutCost(donutName: String, quantity: Int): Double = {
  println(s"Calculating cost for $donutName, quantity = $quantity")

  // make some calculations ...
  2.50 * quantity
}
```

### Como llamar a una función con parámetros
```scala
val totalCost = calculateDonutCost("Glazed Donut", 5)
println(s"Total cost of donuts = $totalCost")
```

### Como agregar valores por defecto a los parámetros
```scala
def calculateDonutCost2(donutName: String, quantity: Int, couponCode: String = "NO CODE"): Double = {
  println(s"Calculating cost for $donutName, quantity = $quantity, couponCode = $couponCode")
}
```

### Como llamar a una función con parámetros por defecto
```scala
val totalCostWithDiscount = calculateDonutCost2("Glazed Donut", 4, "COUPON_12345")
val totalCostWithoutDiscount = calculateDonutCost2("Glazed Donut", 4)
```
