# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Application router.js is where you link all the routes for the entire
    application. This includes organizing how routes are nested,
    linking to the handlebars template, and telling the app what path to reach
    that template in the url.

    Ember route is the equivalent to a model. you can put data you wish to render
    on the page in the ember route.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    #link-to 'campus.boston'
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first is a nested route, nested under the parent route of 'products'.
    The second looks nested, but it's just given a path that has 'products'
    in the url.

    You would probably access the first while you are already
    on the /products view but you could access the second from any view and
    it would just through /products/ before the product id in the url.


    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    The model in your route would take an input of params, and at the end you
    set up the array so that it returns the index of the id passed in as the params.
    It seems like this would only work for our sample data since our indicies
    started at 1 and incremented by 1 each time. If we were to do this with a real database, we shouldnt use the index to find a specific ID rather we'd have to use a findById, or a .where(id == the id parameter passed in)
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    model.attribute or model.key

    for example if you have an attribute of 'name' in the data you could
    reference it in the template as model.name
    ```
