```js

const gameEvents = new Map([

  [17, '⚽️ GOAL'],

  [36, '🔁 Substitution'],

  [47, '⚽️ GOAL'],

  [61, '🔁 Substitution'],

  [64, '🔶 Yellow card'],

  [69, '🔴 Red card'],

  [70, '🔁 Substitution'],

  [72, '🔁 Substitution'],

  [76, '⚽️ GOAL'],

  [80, '⚽️ GOAL'],

  [92, '🔶 Yellow card'],

]);

```

  

<u>Task1 Code:</u>

  

```js
const events = [...new Set(gameEvents.values())];
console.log(events);
```

  

<u>Task2 Code:</u>

```js
const update_GameEvents = gameEvents.delete(64);
console.log(gameEvents);
```

  

<u>Task3 Code:</u>

```js
const average = 90/(events.length);
console.log(`An event happened, on average, every ${average} minutes`);
```

  
  

<u>Task4 Code:</u>

```js
for(const [min,event] of gameEvents){

    //My code
    if(min <= 45){
    
    console.log(`[FIRST HALF] ${min} : ${event}`);

    } else{

     console.log(`[SECOND HALF] ${min} : ${event}`);
    }

  

    //Jonas code
    const half = min <= 45 ? 'FIRST' : 'SECOND';

    console.log(`[${half} HALF] ${min} : ${event}`);

}
```

  
  

<u>Bonus</u>

  

```js
const eventsValues = [...gameEvents.keys()];

console.log(eventsValues[eventValues.length-1]);
```