---
description: >-
  To organize you project you need to use routes and here you can find how you
  can do this.
---

# Routes

To use routes in your application you need to use the lib react-router-dom, you can use executing this command **npm install react-router-dom**.

After the command executed you can create the routes file, I will introduce an example.

{% code title="Routes.js" %}
```jsx
import { BrowserRouter, Routes, Route } from 'react-router-dom';

import Home from './pages/Home';
import About from './pages/About';
import Contact from './pages/Contact';
import Product from './pages/Product';
import PageNotFound from './pages/PageNotFound';

import Header from './components/Header';

function Routes() {
    return(
      <BrowserRouter>
        <Header/>
        <Routes>
          <Route path="/" element={ <Home/> } />
          <Route path="/about" element={ <About/> } />
          <Route path="/contact" element={ <Contact/> } />
          <Route path="/product/:id" element={ <Product/> } />
  
          <Route path="*" element={ <PageNotFound/> } />
        </Routes>
      </BrowserRouter>
    )
}

export default Routes;
```
{% endcode %}

In the App file you need to add the Routes, as follows.

{% code title="App.js" %}
```jsx
import Routes from './routes';

function App() {
    return (
        <Routes/>
    );
}

export default App;
```
{% endcode %}

In the Product page, for example, you can do as follows.

{% code title="pages/Product/index.js" %}
```jsx
import { Link, useParams } from 'react-router-dom';

function Product(){
    const { id } = useParams();
    
    return (
        <h2>Product: {id}</h2>
        <br/>
        <Link to='/contact'>Contact</Link> // You can use link here.
    )
}

export default Product;
```
{% endcode %}

And finally, the Header component.

{% code title="components/Header/index.js" %}
```jsx
import { Link } from 'react-router-dom';

function Header(){
    return(
        <header>
            <h2>Menu</h2>
            
            <Link to='/'>Home</Link>
            <Link to='/about'>About</Link>
            <Link to='/contact'>Contato</Link>
        </header>
    )
}

export default Header;
```
{% endcode %}
