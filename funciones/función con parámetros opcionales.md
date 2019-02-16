## Funciones con parámetros opcionales

Indice:  
- [Cómo definir una opción como parámetro](#Cómo-definir-una-opción-como-parámetro)  
- [Cómo llamar a una función con un parámetro opción](#Cómo-llamar-a-una-función-con-un-parámetro-opción)   
- [Cómo asignar un valor predeterminado a un parámetro opción](#Cómo-asignar-un-valor-predeterminado-a-un-parámetro-opción)   

### Cómo definir una opción como parámetro
//ejm. para manejar cupones de descuento, no todos los clientes tienen cupones.

```scala
def calculateDonutCost(donutName: String, quantity: Int, couponCode: Option[String]): Double = {
  println(s"Calculating cost for $donutName, quantity = $quantity")

  couponCode match {
    case Some(coupon) =>
    val discount = 0.1 // Let's simulate a 10% discount
    val totalCost = 2.50 * quantity * (1 - discount)
    totalCost

    case None => 2.50 * quantity
  }
}
```
### Cómo llamar a una función con un parámetro opción
//couponCode puede asumir el valor **None** o declarar el valor con **Some**, **Some("descuentazo")**

```scala
val precioFinal = calculateDonutCost("Glazed Donut", 5, None)
val precioFinal = calculateDonutCost("Glazed Donut", 5, Some("Descuentazo"))
```

### Cómo asignar un valor predeterminado a un parámetro opción

```scala
def calculateDonutCostWithDefaultOptionValue(donutName: String, quantity: Int, 
                                             couponCode: Option[String] = None): Double = {
  println(s"Calculating cost for $donutName, quantity = $quantity")

  couponCode match{
    case Some(coupon) =>
      val discount = 0.1 // Let's simulate a 10% discount
      val totalCost = 2.50 * quantity * (1 - discount)
      totalCost

    case _ => 2.50 * quantity
  }
}
```
