# Fitness Tracker

## Description

Track your workouts with Fitness Tracker. The app will keep track of every exercise in your workout. The app dashboard will display weekly summary graphs of all workouts done in a week.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
  - [Screenshots](#screenshots)
  - [Snippets](#snippets)
- [Credits](#credits)
- [License](#license)

## Installation

1. Clone repository.
2. Check in routes/api-routes and comment in block of code if you want the database to be prepopulated with dummy values
3. npm install
4. node server.js

Running seeders/seed.js is optional to have a prepopulated database.

<p align="center">
    <a href="https://fitnesstracker96.herokuapp.com"><img src="https://img.shields.io/badge/-👉 See Live Site-success?style=for-the-badge"  alt="Live Site" /></a>
</p>

## Usage

### Screeshots

1. Homepage displaying last workout

![Site](public/assets/homepage.png)

2. Last Week's Summary

![Site](public/assets/dash.png)

### Snippets

1. Adding to an array type

```javascript
// add exercise
app.put("/api/workouts/:id", (req, res) => {
  db.Workout.findOneAndUpdate(
    { _id: req.params.id },
    {
      $inc: { totalDuration: req.body.duration },
      $push: { exercises: req.body },
    },
    { new: true }
  )
    .then((dbWorkout) => {
      res.json(dbWorkout);
    })
    .catch((err) => {
      res.json(err);
    });
});
```

- This function will add an exercise to the array of exercises that belong to the workout with the given id. Here we will locate the workout with the given ID and update its fields. We will increase the total duration of the workout by the duration of the exercise being inserted. We will push the exercise to the array of exercises.

## Credits

### Author

- 💼 Japkirat Singh: [portfolio](https://japkirat96.github.io/Protfolio.me/)
- :octocat: Github: [Japkirat96](https://github.com/JAPKIRAT96/fitnessTracker)

### Built With

</br>
<p align="center">
    <a href="https://developer.mozilla.org/en-US/docs/Web/HTML"><img src="https://img.shields.io/badge/-HTML-orange?style=for-the-badge"  alt="HMTL" /></a>
    <a href="https://developer.mozilla.org/en-US/docs/Web/CSS"><img src="https://img.shields.io/badge/-CSS-blue?style=for-the-badge" alt="CSS" /></a>
    <a href="https://www.javascript.com/"><img src="https://img.shields.io/badge/-Javascript-yellow?style=for-the-badge" alt="Javascript" /></a>
    <a href="https://getbootstrap.com/"><img src="https://img.shields.io/badge/-Bootstrap-blueviolet?style=for-the-badge" alt="Bootstrap" /></a>
    <a href="https://nodejs.org/en/"><img src="https://img.shields.io/badge/-Node-orange?style=for-the-badge" alt="Node" /></a>
    <a href="https://www.npmjs.com/package/express"><img src="https://img.shields.io/badge/-Express-blue?style=for-the-badge" alt="Express" /></a>
    <a href="https://www.mongodb.com/"><img src="https://img.shields.io/badge/-MongoDB-blue?style=for-the-badge" alt="MongoDB" /></a>
</p>

## License

#### MIT
