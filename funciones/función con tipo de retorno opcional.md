## Función con tipo de retorno opcional

En este ejercicio se va a crear una función con parametro option  
Posteriormente se presentan 3 formas diferentes de llamar a una función con parametro option (getOrElse, pattern matching y map)   
Por último se mejora la función del ejercicio anterior con la nueva función para buscar si existe un cupón.

Indice:  
- [función que devuelve un option String](#función-que-devuelve-un-option-String)  
- [llamada a función con option usando getOrElse](#llamada-a-función-con-option-usando-getOrElse)  
- [llamada a función con option usando pattern matching](#llamada-a-función-con-option-usando-pattern-matching)  
- [llamada a función con option usando map](#llamada-a-función-con-option-usando-map)  
- [revisión función ejercicio anterior](#revisión-función-ejercicio-anterior)  

### función que devuelve un option String
//esta función devolverá el cupón asignado a ese cliente filtrando los demás valores vacios.  

```scala
def dailyCouponCode(): Option[String] = {
  // look up in database if we will provide our customers with a coupon today
  val couponFromDb = "COUPON_1234"
  Option(couponFromDb).filter(_.nonEmpty)
}
```
### llamada a función con option usando getOrElse  
```scala
val todayCoupon: Option[String] = dailyCouponCode()
println(s"Today's coupon code = ${todayCoupon.getOrElse("No Coupon's Today")}")
```

### llamada a función con option usando pattern matching

```scala
dailyCouponCode() match {
  case Some(couponCode) => println(s"Today's coupon code = $couponCode")
  case None => println(s"Sorry there is no coupon code today!")
}
```

### llamada a función con option usando map
```scala
dailyCouponCode().map(couponCode => println(s"Today's coupon code = $couponCode"))
```

### revisión función ejercicio anterior
// función ejercicio anterior
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

//ahora ya se puede utilizar la función dailyCouponCode para evaluar si existen cupones
```scala
println(s"""Total cost with daily coupon code = ${calculateDonutCost("Glazed Donut", 5, dailyCouponCode())}""")
```
