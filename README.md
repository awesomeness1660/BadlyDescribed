# Badly Described

> Famous movies and TV shows, described as unhelpfully as possible.

**"A big boat has a bad night."** Can you name the movie?

Badly Described is a browser guessing game. Each round gives you a vague plot
description of a famous movie or TV show, and you have to name the title.

## Features

- **Three difficulty levels**: Easy, Medium and Hard. Harder levels have vaguer descriptions and are worth more points.
- **Hints**: unlock the year, genre, a giveaway clue, and the letter pattern of the title. Each hint costs 20% of the round's points.
- **Category filter**: play with movies, TV shows, or both.
- **Forgiving answers**: small typos and alternate titles count.
- **10 rounds per game**, with a score, a streak counter and an end-of-game recap.
- **No install or sign-up**. It's a single HTML file that runs in any browser.

## Difficulty levels

| Level  | Description style | How you answer      | Hints | Points |
|--------|-------------------|---------------------|-------|--------|
| Easy   | Clear             | Pick from 4 options | 4     | 100    |
| Medium | Vague             | Type the title      | 3     | 200    |
| Hard   | Painfully basic   | Type the title      | 2     | 300    |

On Medium and Hard you get 3 guesses per round.

## How to run it

Download `index.html` and open it in your browser. That's it.

## Hosting it online

The game is one static file, so any free static host works:

- **Netlify Drop**: drag a folder containing `index.html` onto app.netlify.com/drop.
- **GitHub Pages**: push `index.html` to a repo, then turn on Pages under **Settings → Pages**.
- **itch.io**: zip `index.html` and upload it as an HTML project.

## Adding titles

Open `index.html` and find the `TITLES` list near the top of the `<script>` section.
Copy an existing entry and edit it:

```js
{ t: "Titanic", type: "movie", year: 1997, genre: "Romance / disaster", alias: [],
  hard: "A big boat has a bad night.",
  medium: "Two people from very different floors of a ship fall for each other, then the ship has an ice problem.",
  easy: "A rich young woman and a poor artist fall in love on a famous ocean liner's first and last voyage.",
  clue: "There is a long argument online about whether a floating door had room for two." },
```

| Field    | What it's for |
|----------|---------------|
| `t`      | The correct title |
| `type`   | `"movie"` or `"tv"` |
| `year`   | Release year, shown in the first hint |
| `genre`  | Shown in the second hint |
| `alias`  | Other accepted answers, such as `["spiderman", "spider man"]` |
| `hard`   | The vaguest description |
| `medium` | A vague but fairer description |
| `easy`   | A clear description |
| `clue`   | The third hint, which should be a near-giveaway |

Tip: a good `hard` description is technically true but could describe a dozen other things.

## Changing the rules

These settings are near the `TITLES` list:

- `ROUND_SIZE`: rounds per game (default `10`)
- `MAX_GUESSES`: typed guesses per round (default `3`)
- `LEVELS`: points, hint count and multiple-choice setting for each difficulty

## Built with

Plain HTML, CSS and JavaScript, with no frameworks or build step.
Fonts are Anton, Karla and Courier Prime from Google Fonts.
