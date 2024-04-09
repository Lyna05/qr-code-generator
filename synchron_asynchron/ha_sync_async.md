# HA Sync/Async

## Aufgabe 1

Beantworte die Fragen. 10 Punkte pro Frage.

1. **Welche Aussage über synchrone Operationen in JavaScript ist wahr?**
    - A) Sie können den Browser daran hindern, auf Benutzereingaben zu reagieren.
    - B) Sie erfordern die Verwendung des **`async`**Schlüsselwortes.
    - C) Sie laufen parallel zum Hauptthread.
    - D) Sie sind immer schneller als asynchrone Operationen.
2. **Was ist eine Callback-Funktion in JavaScript?**
    - A) Eine Funktion, die andere Funktionen als Parameter annimmt.
    - B) Eine Funktion, die automatisch aufgerufen wird, wenn ein Fehler auftritt.
    - C) Eine Funktion, die als Argument an eine andere Funktion übergeben und von dieser aufgerufen wird.
    - D) Eine Funktion, die wiederholt aufgerufen wird, bis eine Bedingung erfüllt ist.
3. **Wofür werden Callback-Funktionen in JavaScript typischerweise verwendet?**
    - A) Zum Erstellen von Schleifen
    - B) Zur Fehlerbehandlung in synchronem Code
    - C) Zum Warten auf das Ergebnis einer asynchronen Operation
    - D) Zum Direktaufruf innerhalb der Funktion, die sie definiert
4. **Wie übergibt man eine Callback-Funktion als Parameter?**
    - A) Durch Angabe des Funktionsnamens ohne Klammern
    - B) Durch direktes Einfügen des Funktionscodes als Argument
    - C) Durch Aufrufen der Funktion und Übergabe des Ergebnisses
    - D) Alle oben genannten Methoden sind korrekt
5. **Welches Feature ermöglicht es JavaScript, Callback-Funktionen effektiv zu nutzen?**
    - A) Typinferenz
    - B) Ereignisschleifen (Event Loop)
    - C) Statische Typisierung
    - D) Klassenbasierte Vererbung
6. **Was ist ein potenzielles Problem, das durch die Verwendung von zu vielen verschachtelten Callback-Funktionen entstehen kann?**
    - A) Callback-Hölle (Callback Hell)
    - B) Globale Variablenkonflikte
    - C) Unkontrollierte Typumwandlung
    - D) Übermäßiger Speicherverbrauch
7. **Wie kann die "Callback-Hölle" in JavaScript vermieden oder verbessert werden?**
    - A) Durch Verwendung globaler Variablen
    - B) Durch Nutzung von Promises und **`async`**/**`await`**
    - C) Durch vollständiges Vermeiden von Funktionen
    - D) Durch Schreiben aller Code in einer einzigen Funktion
8. **Was ist ein Promise in JavaScript?**
    - A) Eine Funktion, die sofort ausgeführt wird
    - B) Ein Objekt, das die Möglichkeit bietet, auf das Ergebnis einer asynchronen Operation zu warten
    - C) Ein Befehl, um JavaScript-Code anzuhalten
    - D) Ein Typ von JavaScript-Loop
9. **Welche Zustände kann ein Promise haben?**
    - A) running, waiting, completed
    - B) true, false, undefined
    - C) pending, fulfilled, rejected
    - D) open, closed, error
10. **Wie fängt man einen Fehler in einem Promise auf?**
    - A) `.error()`
    - B) `.fail()`
    - C) `.catch()`
    - D) `.reject()`
11. **Welches Schlüsselwort wird verwendet, um eine Funktion als asynchron zu deklarieren?**
    - A) `async`
    - B) `await`
    - C) `defer`
    - D) `promise`
12. **Wie wartet man auf das Ergebnis eines Promises?**
    - A) Durch Aufrufen der `.wait()` Methode des Promises
    - B) Durch Verwendung des `await` Schlüsselwortes vor dem Promise
    - C) Durch direktes Auswerten des Promise-Objekts in einer If-Bedingung
    - D) Durch Rückgabe des Promises aus einer Funktion
13. **Was passiert, wenn innerhalb einer `async` Funktion ein Fehler auftritt und dieser nicht mit `try`/`catch` abgefangen wird?**
    - A) Das Programm stürzt ab.
    - B) Der Fehler wird ignoriert.
    - C) Die Funktion gibt ein abgelehntes Promise zurück.
    - D) Die `async` Funktion wird erneut gestartet.
14. **Kann `await` außerhalb einer `async` Funktion verwendet werden?**
    - A) Ja, in jedem Fall
    - B) Nein, `await` kann nur innerhalb von `async` Funktionen verwendet werden
    - C) Ja, aber nur in synchronen Funktionen
    - D) Ja, aber nur innerhalb von Promises
15. **Was gibt eine `async` Funktion zurück?**
    - A) Einen Boolean-Wert
    - B) Ein Promise
    - C) Einen undefinierten Wert
    - D) Einen synchronen Wert

## Aufgabe 2

Für jedes Beispiel entscheide, ob der Code synchron oder asynchron ist, und gebe an, wie Asynchronität implementiert wird. 15 Punkte pro Beispiel:

### Beispiel 1

```jsx
function sum(a, b) {
  return a + b;
}

console.log(sum(2, 3));

```

**Frage:** Ist der Code synchron oder asynchron und wie ist Asynchronität implementiert?

### Beispiel 2

```jsx
setTimeout(() => {
  console.log('Nachricht nach 2 Sekunden');
}, 2000);

```

**Frage:** Ist der Code synchron oder asynchron und wie ist Asynchronität implementiert?

### Beispiel 3

```jsx
let promise = new Promise((resolve, reject) => {
  setTimeout(() => resolve("Erfolg"), 1000);
});

promise.then(result => console.log(result));

```

**Frage:** Ist der Code synchron oder asynchron und wie ist Asynchronität implementiert?

### Beispiel 4

```jsx
async function fetchUserData() {
  let response = await fetch('<https://api.example.com/user>');
  let data = await response.json();
  console.log(data);
}

fetchUserData();

```

**Frage:** Ist der Code synchron oder asynchron und wie ist Asynchronität implementiert?

### Beispiel 5

```jsx
console.log('Start');
setTimeout(() => {
  console.log('In der Mitte');
}, 0);
console.log('Ende');

```

**Frage:** Ist der Code synchron oder asynchron und wie ist Asynchronität implementiert?

### Beispiel 6

```jsx
function fetchData(callback) {
  setTimeout(() => {
    callback('Daten geladen');
  }, 1500);
}

fetchData(result => console.log(result));

```

**Frage:** Ist der Code synchron oder asynchron und wie ist Asynchronität implementiert?

## Aufgabe 3

Hier sind Code-Beispiele mit Lücken, die ausgefüllt werden sollen. 15 Punkte pro Beispiel.

### Beispiel 1: Erstellen eines Promises

```jsx
let promise = new Promise((resolve, ____) => {
  let completed = true;
  if (completed) {
    resolve('Aufgabe abgeschlossen');
  } else {
    ____('Aufgabe fehlgeschlagen');
  }
});

```

### Beispiel 2: Verwendung eines Promises

```jsx
promise.then((message) => {
  console.log(message);
}).____((error) => {
  console.error(error);
});

```

### Beispiel 3: Verkettung von Promises

```jsx
new Promise((resolve, reject) => {
  setTimeout(() => resolve(1), 1000);
}).then((result) => {
  console.log(result); // 1
  return result * 2;
}).____((result) => {
  console.log(result); // 2
  return result * 3;
}).then((result) => {
  console.log(result); // 6
});

```

### Beispiel 4: Einsatz von `async`/`await`

```jsx
async function fetchUserData() {
  let response = await fetch('<https://api.example.com/user>');
  let data = _____ response.json();
  console.log(data);
}

fetchUserData();

```

### Beispiel 5: Fehlerbehandlung mit `async`/`await`

```jsx
async function checkStatus() {
  try {
    let response = await fetch('<https://api.example.com/status>');
    if (!response.ok) {
      throw new Error('Netzwerkantwort war nicht ok');
    }
    let data = await response.json();
    console.log('Serverstatus:', data.status);
  } ____ (error) {
    console.error('Fehler gefangen:', error);
  }
}

checkStatus();

```