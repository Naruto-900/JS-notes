```js

const game = {

  team1: 'Bayern Munich',

  team2: 'Borrusia Dortmund',

  players:[

   [

    'Neuer',

    'Pavard',

    'Martinez',

    'Alaba',

    'Davies',

    'Kimmich',

    'Goretzka',

    'Coman',

    'Muller',

    'Gnarby',

    'Lewandowski'

   ],

   [

    'Burki',

    'Schutz',

    'Hummels',

    'Akanj',

    'Hakimi',

    'Weigl',

    'Witsel',

    'Hazard',

    'Brandt',

    'Sancho',

    'Gotze'

   ]

  ],

  

  score:'4:0',

  scored: ['Lewandowski','Gnarby','Lewandowski','Hummels'],

  date: 'Nov 9th, 2037',

  odds: {

   team1: 1.33,

   x: 3.25,

   team2:6.5,

  },

};
```


<u>Task1 Code:</u>

```js
//My code

   let goal = 0;

 for(const player of game.scored){

    console.log(`Goal ${++goal}: ${player}`);

 }

  

 //Jonas Sir code

 for(const [i,player] of game.scored.entries())

  console.log(`Goal ${i+1}: ${player}`);

```

>[!NOTE]
>Here in jonas sir code what sir has done is he has used array.entries() method that will return an array of array where each element will be an array where the first element will be the index of that element and second element will be the value



  
<u>Task2 Code:</u>

```js

const odds = Object.values(game.odds);

const average = 0;

  

for(const odd of odds){

    average += odd;

}

  

average /= odds.length;

console.log(average);

  

```

  

<u>Task3 Code:</u>

```js

const player1 = game.team1 , player2 = game.team2

  

const {team1,team2,x:draw} = game.odds

  

console.log(`Odd of victory ${player1}: ${team1}`);

console.log(`Odd of draw: ${draw}`);

console.log(`Odd of victory ${player2}: ${team2}`);

  

//Jonas Code

for(const [team,odd] of Object.entries(game.odds)){

    const str = team === 'x' ? 'draw' : `victory ${game[team]}`;

    console.log(`Odd of ${str} ${odd}`);

}

```


<u>Bonus Code:</u>

```js
 const [players1,players2] = game.players

  

 const p1 = players1[players1.length-2];
 const p2 =  players2[2];
 const p3 = game.scored[0];

  

// const ans = {

//   players1[players1.length-2] : 1,

//   players2[2] : 1,

//   game.scored[0] : 2,

// };

  

const ans = {

    [p1]:1,

    [p2]:1,

    [p3]:2,

}

console.log(ans)
```