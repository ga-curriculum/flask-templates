<h1>
  <span class="headline">Flask Templates</span>
  <span class="subhead">Programming Logic in Templates</span>
</h1>

**Learning objective:** By the end of this lesson, learners will be able to integrate Python programming logic, such as loops and conditional statements, within Flask templates to dynamically control the content and structure of web pages.

| Lesson                         | Duration |
| ------------------------------ | -------- |
| Programming Logic in Templates | 15 min   |

## Python in HTML

One of the powerful features of Jinja templates is the ability to integrate Python logic, such as conditionals and loops, directly within your HTML. This allows you to create dynamic web pages that can change content based on certain conditions or iterate over data structures like lists.

### Looping in HTML with Jinja

You can easily loop through a list or any iterable in your HTML using the for statement. The syntax is straightforward:

```html
{% for number in [1, 2, 3] %}
  <p>{{ number }}</p>
{% endfor %}
```

In this example, the loop will iterate over the list `[1, 2, 3]`, and for each `number`, a new `<p>` tag will be created with the value of number inside it.

### Conditional Statements in HTML with Jinja

Jinja also supports conditional logic using `if`, `elif`, and `else` statements. This allows you to render different HTML depending on the value of a variable or the outcome of an expression.

Here’s an example of using `if/elif/else` in a Jinja template:

```html
{% if temperature >= 32 %}
  <p>It's really hot outside!</p>
{% elif temperature >= 21 %}
  <p>The weather is warm.</p>
{% elif temperature >= 10 %}
  <p>It's a bit chilly today.</p>
{% else %}
  <p>It's cold outside, bundle up!</p>
{% endif %}
```

<br>

<div class="activity solo-exercise">
  <h2 class="title">Create an Index Route</h2>
  <span class="minutes">10 min</span>
</div>

Now that we know the syntax for creating a loop within templates, let's fill in an index route that displays all the book reviews, including titles and text, in the template.

Create your `index` route in the server and complete the code needed to loop through reviews in the `index.html` template file.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Index Page</title>
  </head>
  <body>
    <!-- Loop through the reviews and provide details here -->
  </body>
</html>
```
