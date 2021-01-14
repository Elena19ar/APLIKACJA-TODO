# TO DO APPLICATION (React, Node JS ExpressJS, MongoDB )

Tworzenie zadań do wykonania:
Mamy możliwość Stworzenia zadania: wprowadzania tekstu, przycisk do wprowadzania danych wejściowych.
Mozna zmieniac zadanie.
Wyswietlanie listy zadań TO DO.
Jest funkcja oznaczania zadań do wykonania jako zakończone
I można usunąc zadanie TO Do z listy zadań.

### Jezeli nie ma zadań to wypisuje: No todos yet :(
![Image alt](https://github.com/Elena19ar/APLIKACJA-TODO/blob/master/111.png)
### Podczas wpisania okienko swieci się na niebiesko
![Image alt](https://github.com/Elena19ar/APLIKACJA-TODO/blob/master/Безымянный.png)
### Można wykreślic zadanie (zrobiono)
![Image alt](https://github.com/Elena19ar/APLIKACJA-TODO/blob/master/1.png)
## REACT frontend:
Zostały uzylane pakiety Axios (wyswietlanie żądań http),
Cors (wysyła żądania do API)
Project został bootstrappowany za pomocą Create React App.
## Api Backend (GET, POST, UPDATE, DELETE)


### Połączenie z bazą danych
#### Połączenie z bazą danych w index.js
```
const mongoose = require("mongoose")
mongoose.connect("mongodb://localhost/todo-app", {
 
  keepAlive: true,
  useNewUrlParser: true,
  useUnifiedTopology: true,
})
mongoose.set("debug", true) 
mongoose.Promise = Promise
```

###  DELETE 
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
###  PUT
```
app.put("/todos/:id", async (req, res, next) => {
  try {
    const todo = await db.Todo.findByIdAndUpdate(req.params.id, req.body, {
      new: true,
    })
    return success(res, todo)
  } catch (err) {
    next({ status: 400, message: "failed to update todo" })
  }
})
```
###  POST
```
app.post("/todos", async (req, res, next) => {
  try {
    const todo = await db.Todo.create(req.body)
    return success(res, todo)
  } catch (err) {
    next({ status: 400, message: "failed to create todos" })
  }
})
```

###  GET
```
app.get("/todos", async (req, res, next) => {
  try {
    const todos = await db.Todo.find({})
    return success(res, todos)
  } catch (err) {
    next({ status: 400, message: "failed to get todos" })
  }
})
```


W projekcie również została użyta obsługa błędów:
```

app.use((err, req, res, next) => {
  return res.status(err.status || 400).json({
    status: err.status || 400,
    message: err.message || "there was an error processing request",
  })
})
```


## Wykonawca

#### Alena Arbuzava
#### Grupa S32-31
#### 3 rok 5 semestr
#### indeks 260934

