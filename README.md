# TO DO APPLICATION (React, Node JS ExpressJS, MongoDB )

Tworzenie zadań do wykonania:
Mamy możliwość Stworzenia zadania: wprowadzania tekstu, przycisk do wprowadzania danych wejściowych.
Mozna zmieniac zadanie.
Wyswietlanie listy zadań TO DO.
Jest funkcja oznaczania zadań do wykonania jako zakończone
I można usunąc zadanie TO Do

## REACT frontend:
Zostały uzylane pakiety Axios (wyswietlanie żądań http), Cors (wysyła żądania do API)
     



## Api Backend (GET, POST, UPDATE, DELETE)


###  DELETE 

###  PUT 

###  POST

###  GET
```
pp.delete("/todos/:id", async (req, res, next) => {
  try {
    await db.Todo.findByIdAndRemove(req.params.id)
    return success(res, "todo deleted!")
  } catch (err) {
    next({ status: 400, message: "failed to delete todo" })
  }
})
```
