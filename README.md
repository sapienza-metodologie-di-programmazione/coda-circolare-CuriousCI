# Coda Circolare

Uno dei modi con cui si può implementare una `Queue` è tramite un buffer circolare. Un **buffer** non è altro che un `array` di lunghezza fissa, il fatto che sia circolare indica che l'ultimo elemento è seguito dal primo. 

## Esempio

```java
queue -> [ null | null | null ]
queue.enqueue(10) -> [ 10 | null | null ] 
queue.enqueue(20) -> [ 10 | 20 | null ] 
queue.enqueue(12) -> [ 10 | 20 | 12 ] 
queue.dequeue() -> [ null | 20 | 12 ] 
queue.dequeue() -> [ null | null | 12 ] 
queue.enqueue(15) -> [ 15 | null | 12 ] 
queue.enqueue(22) -> [ 15 | 22 | 12 ] 
queue.enqueue(8) -> Coda piena! 
```

## Richieste

Nel package `metodologie.struct` implementare una `Queue` basata su coda circolare. 

Quando viene creata un'istanza della `Queue` è necessario specificare la dimensione massima del buffer.

La `Queue` deve poter funzionare con tipi generici.


Implementare

- `enqueue(T item)`
    - aggiunge un `item` in fondo alla coda
    - **è fondamentale decidere** come gestire il caso in cui la coda è **piena**
- `dequeue()`
    - ritorna l'`item` in testa alla coda
    - **è fondamentale decidere** come gestire il caso in cui la coda è **vuota**
- `Iterable`
    - permettere di iterare la `Queue` in maniera comoda con un `for`
    - non rimuove elementi dalla `Queue`, permette soltanto di iterarli

> In questo caso `Iterable` vi permette di implementare la logica per iterare gli elementi di un buffer circolare una volta sola, e riusarla in maniera facile.
> Non è banale iterare un buffer circolare, per questo è comodo usare `Iterable` 
