# 99 Little Bugs In the Code & Poke-Express

Here, we will build 3 small projects in one to keep learning express.

## Getting Started

- Fork this repo
- `git clone` the forked repository
- `cd` to the directory where you cloned it
- `npm install` to install dependencies that are already included in the `package.json`
- `npm test` to run the tests
- `npm install express dotenv` to install new dependencies express and dotenv
- `touch app.js server.js .env`
- go into `package.json` and put `server.js` as the value for the key `main`

**.env**

```
PORT=8888
```

> _Note_: Remember to `git add`, `git commit` and `git push` regularly

## Submission Guidelines

- When finished, commit and push your work.
- Make a pull request on GitHub.

## Poke-Express

In The Darkest Timeline: The [Pokeapi](https://pokeapi.co) has gone from free to \$1 per API call!

You decide to take it upon yourself to create a new Pokemon API for all to share for free.

You have happened upon a strange `pokemon.json` file. Rumor has it that a mysterious person who goes by PyritePikachu scraped this data off the internet. It doesn't have anywhere near as much info as Pokeapi and it seems a bit outdated, but that's ok! It's a start!

### Getting Started

Confirm you are able to bring in the data from the `pokemon.json` file

**app.js**

```js
const pokemon = require('./pokemon.json')
console.log(pokemon[0])
```

`node app.js` - to confirm you see an object with Bulbasaur's info.

- make a route `/pokemon` that will show a list of all the pokemon
- make a route `/pokemon/:indexOfArray` that returns 1 pokemon at that array position
  - if the array position is invalid or there is no pokemon at that position, instead send `sorry, no pokemon found at /pokemon[indexOfArray]` - where `[indexOfArray]` is the value from the URL that the user has entered
- make a route /pokemon/search - where a user can add a query parameter
  such as http://localhost:8888/pokemon/search?name=oddish

  which will respond with

  ```
  {
  name: 'Oddish',
  img: 'http://img.pokemondb.net/artwork/oddish.jpg',
  type: [ 'Grass', 'Poison' ],
  stats: {
    hp: '45',
    attack: '50',
    defense: '55',
    spattack: '75',
    spdefense: '65',
    speed: '30'
  },
  damages: {
    normal: '1',
    fire: '2',
    water: '0.5',
    electric: '0.5',
    grass: '0.25',
    ice: '2',
    fight: '0.5',
    poison: '1',
    ground: '1',
    flying: '2',
    psychic: '2',
    bug: '1',
    rock: '1',
    ghost: '1',
    dragon: '1',
    dark: '1',
    steel: '1'
  },
  misc: {
    classification: 'weed pokemon',
    height: '1’08”',
    weight: '11.9',
    happiness: '70'
  }
  }

  ```

## Bonus

- Instead of just sending JSON, create new routes at `/pokemon-pretty/` send some HTML
- for all the pokemon, send an unordered list of anchor tags that link to the array position of the pokemon
- in each individual view `/pokemon-pretty/:indexOfArray` of a pokemon, instead of JSON, display the name, image and any other info

HRRMMM, adding all this HTML as a string inside the routes is getting unweildly... is there a better way?

## Bonus Bonus

- Add search ability for other keys in the pokemon data.

- Use `<style></style>` and put some CSS in there to style the page

- Use create-react-app and figure out how to connect it to this backend (we'll teach you later on in the course how to do this)