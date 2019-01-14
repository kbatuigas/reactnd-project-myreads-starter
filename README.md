# MyReads Project

This app allows the user to track book reading from a particular library - books they've read, books they're currently reading, and books they want to read. Each of these groups of books are organized by shelves: Read, Currently Reading, and Want to Read. 

Each book can be moved from one shelf to another by using its dropdown menu. Books can also be removed entirely from a shelf ("None").

The app also has a search page, which allows the user to search the library. The page uses particular search terms - more details can be found [here](SEARCH_TERMS.md).

To run the app, follow these steps:

* download this repo locally to your machine
* install all project dependencies with `npm install`
* start the development server with `npm start`

## Repo files
```bash
├── README.md - This file.
├── SEARCH_TERMS.md # The whitelisted short collection of available search terms for you to use with your app.
├── package.json # npm package manager file. It's unlikely that you'll need to modify this.
├── public
│   ├── favicon.ico # React Icon, can be changed.
│   └── index.html # DO NOT MODIFY
└── src
    ├── App.css # App styles, can be customized as desired.
    ├── App.js # This is the root of the app. Contains static HTML.
    ├── App.test.js # Used for testing. Provided with Create React App. Testing is encouraged, but not required.
    ├── BooksAPI.js # A JavaScript API for the provided Udacity backend. Instructions for the methods are below.
    ├── icons # Helpful images for the app. Use at your discretion.
    │   ├── add.svg
    │   ├── arrow-back.svg
    │   └── arrow-drop-down.svg
    ├── index.css # Global styles. You probably won't need to change anything here.
    └── index.js # Used for DOM rendering only, shouldn't need to modify
```

## Backend Server for Development

To simplify the development process, a backend server for you to develop against has been provided. The file [`BooksAPI.js`](src/BooksAPI.js) contains the methods needed to perform necessary operations on the backend:

* [`getAll`](#getall)
* [`update`](#update)
* [`search`](#search)

### `getAll`

Method Signature:

```js
getAll()
```

* Returns a Promise which resolves to a JSON object containing a collection of book objects.
* This collection represents the books currently in the bookshelves in your app.

### `update`

Method Signature:

```js
update(book, shelf)
```

* book: `<Object>` containing at minimum an `id` attribute
* shelf: `<String>` contains one of ["wantToRead", "currentlyReading", "read"]  
* Returns a Promise which resolves to a JSON object containing the response data of the POST request

### `search`

Method Signature:

```js
search(query)
```

* query: `<String>`
* Returns a Promise which resolves to a JSON object containing a collection of a maximum of 20 book objects.
* These books do not know which shelf they are on. They are raw results only. You'll need to make sure that books have the correct state while on the search page.

## Important
The backend API uses a fixed set of cached search results and is limited to a particular set of search terms, which can be found in [SEARCH_TERMS.md](SEARCH_TERMS.md). That list of terms are the _only_ terms that will work with the backend, so don't be surprised if your searches for Basket Weaving or Bubble Wrap don't come back with any results.

## Create React App

This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app). You can find more information on how to perform common tasks [here](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md).

## Credits

* forked from Udacity starter template [here](https://github.com/udacity/reactnd-project-myreads-starter)
* Ryan Waite's [project walkthrough for FEND](https://youtu.be/acJHkd6K5kI)
