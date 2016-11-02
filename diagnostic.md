# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Application Router - This holds the default template where the main HTML
    will be displayed. This template also holds the {{outlet}} which is needed
    in order for the child templates to render in a specific view.

    Ember Route - this lets the app know what URL a specific View corresponds to.
    We have to create routes for any additional views except the default view '/'
    which is built into Ember.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
      ember g route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}Boston{{/link-to}}{{/link-to}}
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
    The first definition is a nested route. When the user goes to /products and
    clicks on one product, the path will change to products/:product_id. In this
    definition the route /product is not available to the user.

    In the second definition, the /product route is available to the user so
    when that url is passed in, the path will update to products/:product_id

    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    params.movie_id
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    You can reference by using model.data or if using an each statement ..

    {{#each model as |data|}} to rename 'model'
    ```
