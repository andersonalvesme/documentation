# Quick start

### What is React?

React is a Javascript library for building user interfaces.

React is used to build single-page applications.

React allows us to create reusable UI components.

### How does React Work?

> React creates a VIRTUAL DOM in memory.

Instead of manipulating the browser's DOM directly, React creates a virtual DOM in memory, where it does all the necessary manipulating, before making the changes in the browser DOM.

> React only changes what needs to be changed!

React finds out what changes have been made, and changes only what needs to be changed.

#### What is DOM?

The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.

### React.JS History

Current version of React.JS is V18.0.0 (April 2022).

Initial Release to the Public(V0.3.0) was in July 2013.

React.JS was first used in 2011 for Facebook's Newsfeed feature.

Facebook Software Enginner, Jordan Walke, created it.

Current version of `create-react-app` is v5.0.1 (April 2022)

`create-react-app` includes built tools such as webpack, Babel and ESLint.

### How to create a React App?

First you need to set up a React Environment on your computer. You can use create-react-app, this tool is an officially supported way to create React applications.

> Node.js is required.

Open your terminal and run this command: npx create-react-app my-react-app

> Note: If you've previously installed **create-react-app** globally, it is recommended that you uninstall the package to ensure npx always uses the latest version of create-react-app. To uninstall, run this command: **npm uninstall -g create-react-app**.
