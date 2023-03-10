- # What is Routing
    - Duh - how we are able to navigate from one view to another in an app
    - React Router on the other hand, is used to create various routes in a single-page application. It is the standard routing package used in react to change views and move between pages.
- # What is the React Router Dom?
    - The React Router DOM is the node module that is specific to routing in web applications as opposed to mobile.
    - It allows engineers to create routes for a React single page application.
- # BrowserRouter, Route, Switch, and Link
    - 3 categories
        - 1. <BrowserRouter>BrowerRouter is a router implementation that has the ability to incorporate routing in react. It uses the [HTML5 History API](https://reactrouter.com/web/api/BrowserRouter) which include pushState, replaceState and the popState event to keep our UI in sync with the URL. It is the parent component that is used to store all other components and it uses regular URL paths.
        - 2. <Route>: Route is the conditional component that renders a component based on the URL defined or the URL it is pointing to. In other words, it is a component that renders some UI when its path matches the current URL.
            - <Link>: Link component is used to create links to different routes and implements navigation around the application. Links accepts the to prop, which signifies where we want the link to navigate our user to.
        - 3. <Switch>: The switch component is used to render only the first route that matches the location rather than rendering all matching routes.
- # Useful Hooks
    - ## useHistory
        - According to the react router doc, the useHistory hook gives you access to the history instance that you may use to navigate. Through the history object, we can access and manipulate the current state of the browser history.
    - ## useParam
        - The useParam hook returns an object of key/value pairs of URL parameters where the key is the parameter’s name and the value is the parameter’s current value. In other words, it provides access to search parameters in the URL.
    - ## useLocation
        - The useLocation hook is equivalent to the useState but it returns a new location whenever the URL changes. In simple terms, the useLocation hook returns the location object that represents the current URL.
