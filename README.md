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


# FRAMEWORK
### screen z kodu (css)
![Image alt](https://github.com/Elena19ar/APLIKACJA-TODO/blob/master/css.png)

### screen z kodu (przyklad uzycia klas)
![Image alt](https://github.com/Elena19ar/APLIKACJA-TODO/blob/master/1css.png)
 
 
 
  ### Wykorzystanie Bootstrapu:
  
 ```
 div class="btn-group">
      <button type="button" class="btn btn-danger dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Action
      </button>
      <div class="dropdown-menu">
        <a class="dropdown-item" href="http://localhost:3000/todoes">To do</a>
        <a class="dropdown-item" href="http://localhost:3000">home</a>       
        <div class="dropdown-divider"></div>
        <a class="dropdown-item" href="#">Search</a>
      </div>
    </div>


    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>


    <div class="row">
      <div class="col-sm-6">
        <div class="card">
          <div class="card-body">
            <div class="card" style="width: 18rem;">

              <div class="card-body">
                <h5 class="card-title">ToDo app</h5>
                <h6 class="card-subtitle mb-2 text-muted">Screen from repo</h6>
                <p class="card-text">Tworzenie zadań do wykonania: Mamy możliwość Stworzenia zadania: wprowadzania tekstu, przycisk do wprowadzania danych wejściowych. Mozna zmieniac zadanie. Wyswietlanie listy zadań TO DO. Jest funkcja oznaczania zadań do wykonania jako zakończone I można usunąc zadanie TO Do z listy zadań..</p>
                <a href="#" class="card-link">https://github.com/Elena19ar/APLIKACJA-TODO/blob/master/README.md</a>
                
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-sm-6">
        <div class="card">
          <div class="card-body">
            <div class="card-body">
              <h5 class="card-title">Maps SDK</h5>
              <h6 class="card-subtitle mb-2 text-muted">for Android Utility Library</h6>
              <p class="card-text">This open-source library contains utilities that are useful for a wide range of applications using the Google Maps Android API.   </p>

              <a href="https://github.com/Elena19ar/android-maps-utils" class="btn btn-primary btn-lg disabled" tabindex="-1" role="button" aria-disabled="true">Link na Repo</a>
              
              
          </div>
        </div>
      </div>
    </div>

 ```
 ### screen z kodu 
![Image alt](https://github.com/Elena19ar/APLIKACJA-TODO/blob/master/1b.png)
 
 ### Uzywanie css-ow
```
.searchbox__submit {
  position: absolute;
  top: 0;
  margin: 0;
  border: 0;
  border-radius: 16px 0 0 16px;
  background-color: rgba(69, 142, 225, 0);
  padding: 0;
  width: 32px;
  height: 100%;
  vertical-align: middle;
  text-align: center;
  font-size: inherit;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  right: inherit;
  left: 0;
}

.searchbox__submit::before {
  display: inline-block;
  margin-right: -4px;
  height: 100%;
  vertical-align: middle;
  content: '';
}

.searchbox__submit:hover,
.searchbox__submit:active {
  cursor: pointer;
}






## Wykonawca

#### Alena Arbuzava
#### Grupa S32-31
#### 3 rok 5 semestr
#### indeks 260934

