# Ionic Angular InfoApp

App to search for info from an API and display it using the [Ionic 4 framework](https://ionicframework.com/docs).
Currently using a movie database API to develop the app.

## Table of contents

* [General info](#general-info)
* [Screenshots](#screenshots)
* [Technologies](#technologies)
* [Setup](#setup)
* [Features](#features)
* [Status](#status)
* [Inspiration](#inspiration)
* [Contact](#contact)

## General info

An active search bar enables the user to search for movies, with a list of matches appearing below. Each returned movie card can be clicked on to see more details. The API searches the [The Open Movie Database](http://www.omdbapi.com/) for search matches.

## Screenshots

![Home Page](./img/info-search.png)

## Technologies

* Ionic/angular - version 4.0.0
* Ionic DevApp, to allow app to run on an iOS or Android device.

## Setup

* To start the server on _localhost://8100_ type: 'ionic serve'
* The Ionic DevApp was installed on an Android device from the Google Play app store.

## Code Examples

* functions to search for info and retrieve more detailed info.

```typescript
  // Get data from the Omdb Api
  // map the result to return only the results that we need
  // @param {string} title Search Term
  // @param {SearchType} type movie, series, episode or empty
  // @returns Observable with the search results
  searchData(title: string, type: SearchType): Observable<any> {
    return this.http.get(`${this.url}?s=${encodeURI(title)}&type=${type}&apikey=${this.apiKey}`).pipe(
      map(results => results['Search'])
      );
  }
  // Get detailed information using the "id" parameter
  // @param {string} id imdbID to retrieve information
  // @returns Observable with detailed information
  getDetails(id) {
    return this.http.get(`${this.url}?i=${id}&plot=full&apikey=${this.apiKey}`);
  }
```

## Features

* Example 1

## Status & To-do list

* Status: Working info search, returns move info - see screen-print.

* To-do: add code so detailed info is returned.

## Inspiration

Project inspired by [Simon Grimms's 'How to Build Your First Ionic 4 App with API Calls'](https://medium.freecodecamp.org/how-to-build-your-first-ionic-4-app-with-api-calls-f6ea747dc17a).

## Contact

Created by [ABateman](https://www.andrewbateman.org) - feel free to contact me!