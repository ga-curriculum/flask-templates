<h1>
  <span class="headline">Flask Templates</span>
  <span class="subhead">Sending and Receiving Data</span>
</h1>

**Learning objective:** By the end of this lesson, learners will be able to send and receive data in a Flask application, using the request object to handle form data from POST requests and simulate basic create operations.

| Lesson                     | Duration |
| -------------------------- | -------- |
| Sending and Receiving Data | 15 min   |

## Reading Complex Request Data

So far, we've handled simple GET requests that retrieve and display information. However, in most applications, we need more complex functionality to create, update, and delete resources. This is where Flask's [request](https://flask.palletsprojects.com/en/3.0.x/reqcontext/) object comes into play.

The `request` object in Flask provides access to data sent from the client to the server. For instance, if we were sending data from an HTML form in a browser, we could access that data using the `request.form` object.

### Accessing Form Data

When a user submits a form in a web application, the data from the form fields is sent to the server. You can access this data in Flask using the `request.form` object, which behaves like a dictionary containing the form fields and their corresponding values.

```python
import request from Flask # include request with your other imports

@app.route("/accept_data", methods=["POST"])
def handle_data_submission():
    # Accessing form data sent via POST request
    data = request.form["address"]  # you can replace "address" with the name attribute of any form input
    return f"Received data: {data}"
```

If a form with an input field named `address` is submitted, `request.form["address"]` retrieves the value from that input field.

### Practicing sending data

Since we aren't working with a real database in this exercise, we can't fully implement true `CREATE`, `UPDATE`, and `DELETE` operations. However, we can simulate these actions by sending mock `POST` requests with data to our server. This data could represent the kind of information you might normally receive from an HTML form in a browser.

We can use this mock data to add logic to our create route, which will add the data to our list of reviews and then display this new review on our index page.

#### Sending a POST Request

Because this is a `POST` request with data, you can't just use a URL in the browser to send it. Instead, you can use a tool like `curl` or `Postman` to simulate sending data from a client to the server.

```bash
curl -X POST http://127.0.0.1:5000/reviews -d "book_title=New Book&review_text=Great read&score=5"
```

- `-X POST` specifies the request method (POST).

- `-d` indicates that data is being sent with the request. The data is formatted as `key=value` pairs, where key corresponds to the form field name and value is the data being sent.

<br>

<div class="activity group-exercise">
  <h2 class="title">Creating New Reviews</h2>
  <span class="minutes">10 min</span>
</div>

Create a route that accepts a `POST` request to `/reviews` and adds a new review to the reviews list.

- Define a new route in your Flask application that listens for `POST` requests at the `/reviews` endpoint.

- Extract the data sent in the request (book title, review text, score) and add this data to your existing list of reviews.

- Use `Postman` or `curl` to practice sending data to your new create route.

<img src="./assets/open-book.png" alt="Open Book Image" style="width: 300px; height: auto;">
