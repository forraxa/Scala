## Función implícita

Permite proporcionar métodos o funciones a las clases o cualquier tipo.  

Indice:  
- [](#)

### como crear una clase de tipo String y un metodo llamado isFavoriteDonut()

```scala
class DonutString(s: String) {
  def isFavoriteDonut: Boolean = s == "Glazed Donut"
}
```

### como crear una función implícita encapsulada en un objeto para convertir un String en un objeto de una clase.  

```scala
object DonutConverstions {
  implicit def stringToDonutString(s: String) = new DonutString(s)
}
```
