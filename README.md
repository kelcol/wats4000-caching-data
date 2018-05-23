# Caching Data

> A project to practice caching data in the browser.

This project is designed to practice with caching data in `localStorage` using
the `vue-ls` module to help us. The project builds on [the previous refactoring
project](https://shawnr.gitbooks.io/practical-javascript-2-building-applications/content/application-architecture/project-application-architecture.html) where we enhanced the organization of a weather application. We will
work with a weather application that could have come out of that prior refactoring
experience.

The weather application has three major views: `CitySearch`, `CurrentWeather`,
and `Forecast`. These three views use several child components to display all of
their information. When we first open the repository, we can notice that there is
no way to save any data, and the site is making many requests to the weather API.

In order to improve the performance and user experience in our weather app, we
will add the ability for users to save favorite cities for easy viewing when
they return to the application. We will also cache our API queries so we do not
risk running into a rate limit, and so our users do not have to wait for
information to load as often.

These changes will dramatically enhance the utility and speed of our application.
To accomplish these changes, we will cache data into `localStorage` using the
`vue-ls` module. This module helps us manage our stored information more
efficiently and makes it a snap to provide expiration times on information.

In order to complete this project, we will edit several files in the repository.
Look for the `TODO` notes for guidance and indications of how we can accomplish
our goals.

**Note:** Additional information about completing this project can be found in
the [Practical JavaScript 2: Building Applications](https://shawnr.gitbooks.io/practical-javascript-2-building-applications/content/caching-data/project-caching-data.html) book.

**NOTE:** This project requires an API key from [OpenWeatherMap.org](https://openweathermap.org).

## Basic Requirements
In order to successfully complete this project, we must fulfill the following requirements.

- [X] Sign up to [OpenWeatherMap.org](https://openweathermap.org/) and generate an API Key.
- [X] Paste your API Key (which will be used as the `APPID` parameter) into the appropriate location in the `/src/common/api.js` file.

**`main.js`**
- [X] Add the base configuration for `vue-ls`.

**`CitySearch.vue`**
- [X] Add the `FavoriteCities` component as a child to the `CitySearch` component (using proper imports, etc.).
- [X] Add logic to the `created` function to initialize `this.favorites` to the value of the `favoriteCities` object in `localStorage`.
- [X] Add logic to the `saveCity` function to update the `favoriteCities` cache in `localStorage`.
- [X] Add logic to properly cache the API request in the `getCities` method (with proper label and expiry time).

**`FavoriteCities.vue`**
- [X] Add logic in the `removeCity` method to remove the city from the `this.favoriteCities` array.
- [X] Add logic to the `removeCity` method to remove the city from `localStorage`.

**`CurrentWeather.vue`**
- [X] Add logic to properly cache the API request in the `created` function (with proper label and expiry time).

**`Forecast.vue`**
- [X] Add logic to properly cache the API request in the `created` function (with proper label and expiry time).

## Stretch Goals
If we crave more challenge, we can attempt these additional goals.

- [ ] Add more preferences to the system, such as the ability to load a single "favorite" city when the page is first loaded (with no clicks or search required).
- [ ] Add the ability for users to specify their own label for the favorite cities (e.g. "home", "Aunt Barb's House", etc.).
- [ ] Add a query to another API service, such as flickr, to augment this information. Build the proper caching to make efficient use of that query, too.
- [ ] Add animated transitions to the information in this project.


## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
