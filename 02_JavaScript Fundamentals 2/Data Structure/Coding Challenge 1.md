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

}

```

  

<u>Task1 Code</u>:

```js

const [players1,players2] = game.players;

console.log(players1,players2);

```


<u>Task2 Code : </u>

```js

const [gk,...fieldPlayers] = players1

console.log(gk,fieldPlayers);

```


<u>Task3 Code:</u>

```js

const allPlayers = [...players1,...players2];

console.log(allPlayers);

```

  
<u>Task4 Code:</u>

```js

 const players1Final = [...players1,'Thiago','Coutinho','Perisic'];

 console.log(players1Final);

```

  
<u>Task5 Code:</u>

```js

//My code

const{team1,team2,x:draw} = game.odds;

console.log(team1,team2,draw);

  

//Jonas Sir Code

const{odds:{team1,team2,x:draw}} = game

```

  
<u>Task6 Code:</u>

```js

function printGoals(...PlayersName){

   console.log(`${PlayersName.length} goals scored`);
   
    PlayersName.forEach((player)=>{

    console.log(player,PlayersName.length);

  })
}


printGoals('Davies','Muller','Lewandowski','Kimmich')
printGoals(...game.scored);
```

<u>Task7 Code:</u>

```js
 team1 < team2 && console.log('Team1 is more likely to win');
 team2 < team1 && console.log('Team2 is more likely to win');
```



	