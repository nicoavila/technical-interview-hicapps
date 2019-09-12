# Technical Interview HICAPS
> Este repositorio contiene la descripción del ejercicio para evaluar a los candidatos al puesto de **Desarrollador** en HICAPPS

![Logo](https://hicapps.cl/web/wp-content/uploads/2018/01/minlogo2x-2.jpg)

## Ejercicio:

### Objetivos:
* Evaluar la capacidad de resolución eficiente de un problema.
* Evaluar la capacidad de uso de `class`.
* Evaluar la capacidad de uso de `Promise.all()`
* Evaluar la capacidad de uso de `fetch()`
* Evaluar la capacidad de interacción con el DOM
* Evaluar la capacidad de uso de `map()` y `filter()`.

### Enunciado
Dados los siguientes endpoints:

1. https://jsonplaceholder.typicode.com/users
2. https://jsonplaceholder.typicode.com/todos

Que retornan el siguiente payload

+ Users (Array de Objetos)
```
{
    [
        {
            "id": 1,
            "name": "Leanne Graham",
            "username": "Bret",
            "email": "Sincere@april.biz",
            "address": {
                "street": "Kulas Light",
                "suite": "Apt. 556",
                "city": "Gwenborough",
                "zipcode": "92998-3874",
                "geo": {
                    "lat": "-37.3159",
                    "lng": "81.1496"
                }
            },
            "phone": "1-770-736-8031 x56442",
            "website": "hildegard.org",
            "company": {
                "name": "Romaguera-Crona",
                "catchPhrase": "Multi-layered client-server neural-net",
                "bs": "harness real-time e-markets"
            }
        }
    ]
}
```

+ Todos (Array de Objetos)
```
{
    [
        {
            "userId": 1,
            "id": 1,
            "title": "delectus aut autem",
            "completed": false
        }
    ]
}
```

Crea una pequeña aplicación en [Codepen](https://codepen.io) que muestre todos los **TODOS** de un **USER** en particular al hacer click en un botón.
Se adjunta una imagen del funcionamiento esperado:

<img src="https://github.com/nicoavila/technical-interview-hicapps/blob/master/expected.gif">

### Requerimientos
* Implementa una clase `Fetcher`. Debe aceptar en su constructor una `string` correspondiente al endpoint que quiero consultar. La clase debe implementar un método `callUrl()` que permita realizar una llamada a una API externa usando `fetch()`. Este método debe devolver una promesa.
* Utiliza dos instancias de `Fetcher` para realizar las llamadas a las API.
* Implementa una clase `DOMWritter` que acepte un resultado de una selección al DOM utilizando `querySelector()`. La clase debe implementar un método `createUserTodo()` que acepte como argumentos un `string` correspondiente al ID del usuario y un `Array` de objetos (cada uno de esos objetos corresponde a la lista de **TODOS** del **USER** en particular). Este método debe crear los elementos necesarios para mostrar los **TODOS** del **USER**.
* Utiliza una instancia de `DOMWritter` para realizar las operaciones de escritura en el DOM.
* Implementa un `eventListener` al evento `click` del botón. Utilizando `Promise.all()` debes esperar la llamada de ambos endpoints, de lo contrario muestra un mensaje con `console.error`. Cuando ambas promesas se resuelvan, debes identificar todos los **TODOS** de un **USER** utilizando `map()` y `filter()`. Cuando hayas terminado de identificar todos los **TODOS** de un **USER** utiliza el método `createUserTodo()` para mostrar esa información en el DOM.

### Criterios de evaluación
1. Se evaluará que el postulante pueda resolver el problema en forma eficiente.
2. Se evaluará que el postulante respete los requerimientos planteados en el ejercicio.

### Entrega
1. Se debe entregar por email un vínculo al _Pen_.

**MUCHO ÉXITO :tada:**