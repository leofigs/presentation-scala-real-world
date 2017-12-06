
## Scala no mundo real

---
@title[Perfil: Leonardo]

### Quem é o Leonardo

- 99ner
- Programador Scala há 1 ano +-
- Antes disso Python, Java, .Net ...
- dog person

@fa[github] leofigs   |   @fa[twitter] @leonardofigs   |   @fa[envelope-o] leofigs no gmail

---
@title[Scala]

![scala](assets/scala-logo-white.png)

- Multi paradigma ( Funcional + OO ) |
- Bitecode Java / JVM |
- Lightbend |


---
@title[99 scala evolution]
### Repositórios Scala na 99

<img src="assets/repos-progression.png" alt="repos-progression" style="height: 430px;"/>


---
@title[99 scala repos]
### Repositórios Scala ativos em 2017

<img src="assets/repos-active.png" alt="99_Scala" style="height: 430px;"/>

Note:
- Ativos = criados ou modificados em 2017
- Empresa poliglota
- Scala é uma das linguagens principais
- Scala é utilizada desde 2013

---
@title[99 scala languages]

### Outras linguagens na 99

<img src="assets/repos-word-cloud.png" alt="99_Scala" style="height: 430px;"/>

---
@title[Funcional]


## Scala é Funcional

![funcional](assets/dog-agility.gif)


---
@title[Functional Concepts]

## Paradigma funcional


<img src="assets/functional-cloud.png" alt="funcional" style="height: 430px;"/>


---
@title[Funcional - Imutabilidade]

### Imutabilidade

![imutabilidade](assets/dog-isolation.gif)

- Menos side effects (e bugs) |
- Mais facil para paralelizar |
- Melhoria na concorrência |
- Mais fácil para cachear / serializar |

---
@title[Funcional - Imutabilidade]

### O default em Scala é sempre imutável

```
println(List(1,2,3).getClass)
//class scala.collection.immutable.$colon$colon
```
---
@title[Funcional - Var]


### E o var?

![nope](assets/dog-nope.gif)


---
@title[Funcional - Monads]

### Monads
<img src="assets/dog-with-balls.gif" alt="dog-balls" style="height: 130px;"/>

Em duas palavras: Encapsula computação.
( existem mais regras para monads...)

Future é uma monad:
```scala
val f = Future {
	println("o futuro é agora")
}
```

---
@title[Functional - Code example]
### Código menor e mais sucinto

Java:
```java
public static Optional<Long> s2SourceFromLatLng(
	Double lat, Double lng, int estimativeCellLevel) {
  try {
    return Optional.of(S2CellId.fromLatLng(
      S2LatLng.fromDegrees(lat, lng)).parent(
        estimativeCellLevel).id());
  } catch (Exception e) {
    return Optional.empty();
  }
}
```

Scala:
```scala
def getCell(lat: Double, lng: Double,
	estimativeCellLevel: Integer = 18) =
    Try(S2CellId.fromLatLng(S2LatLng.fromDegrees(lat, lng))
      .parent(estimativeCellLevel).id).toEither
```


---
@title[Functional - Libraries]

### Bibliotecas Funcionais

Scala não define classes básicas para estruturas funcionais.


Bibliotecas:

 Scalaz

<img src="assets/cats-logo.png" alt="cats" style="height: 80px;"/>




---
@title[WWW]


### Scala para a Web

![web](assets/dog-on-turtle.gif)


---
@title[ScalaJS]

<img src="assets/scala-js-logo.png" alt="scalajs" style="height: 230px;"/>

- Tipagem estática
- Compila o código para Javascript (+ performance)
- Interoperavel com React, AngularJS
- Typescript++

---
@title[ScalaJS - Example]

```javascript
class Person(val firstName: String, val lastName: String) {
  def fullName(): String =
    s"$firstName $lastName"
}
```


```javascript
val names = persons.map(_.firstName)
```
---
@title[WWW - Play]

<img src="assets/play_logo.png" alt="playframework" style="height: 230px;"/>

- Akka no motor
- Stateless
- RESTful
- Big players ( Linkedin, Samsung, Walmart, theguardian)

---
@title[WWW - Play - Example]

### Endpoint Play

```scala
def findAllReceiptsByRefund(refundId: Long,
  limit: Int, offset: Int) = Action.async { request =>
    val res = for {
      recs  <- receipts.findByRefund(Some(refundId), limit: Int, offset: Int)
      count <- receipts.countFindByRefund(Some(refundId))
      jsonResult = Json.obj("receipts" -> recs, "size" -> count)
    } yield jsonResult
    res map (Ok(_))
  }
```

---
@title[WWW - Akka HTTP]

<img src="assets/akka_logo.png" alt="akka" style="height: 130px;"/>

AKKA-HTTP não é um framework web.

![dog-wat](assets/dog-wat.gif)

---
@title[WWW - Akka HTTP]

É um "toolkit" server e client http contruída sob o akka-actor e akka-stream

<img src="assets/dog-hard.gif" alt="dog-hard" style="height: 330px;"/>


---
@title[WWW - Akka HTTP]

### Comofas


```scala
object GeocoderResource extends BaseResource {
  val routes = pathPrefix("geocode" / "city") {
    pathEndOrSingleSlash {
      get {
        parameters('lat.as[Double], 'long.as[Double]){ (lat, long) =>
            getCityByLatLong(lat, long)
        }
      }
    }
  }

  def getCityByLatLong(lat: Double, long: Double) = complete(OK)
}
```


---
@title[Reactive title]

### Scala é Reativo

![reactive-dog](assets/dog-active.gif)

---
@title[Reactive]

![lightbend](assets/lightbend-logo.png)

Plataforma Reativa

![lrp](assets/lightbend_reactive_platform.png)

---
@title[Data]

### Data em Scala

![data](assets/dog-bag.gif)

---
@title[Data - BigData]

### BigData

![spark](assets/spark-logo.png)

---
@title[Market]

### Mercado de trabalho

![dogmoney](assets/dog-money.gif)


---
@title[Market - Stackoverflow dev survey]

![stackoverflow](assets/stackoverflow-logo.png)

StackOverflow Developer Survey

- Linguagem mais bem paga nos EUA em 2016 e 2017 |
- Top 10 mais bem pagas no mundo |
- Top 10 média salarial |

---
@title[Market - Brazil]

### Mercado no Brasil



---
@title[Market - World]

### Mercado no mundo



---
@title[The End]

## Obrigado.

## Estamos contratando

<img src="assets/logo99_big.png" class="no-border" alt="99_Logo" style="height: 400px;"/>

**The End**
---
