# How to run Flutter Integration Tests at Hyper Speed

I've been writing some Integration Tests for my upcoming Flutter course.

These go through an entire user flow (10 screens) in less than 20 seconds! ⏱

How did I do it? 🧵

<!-- TODO: Add Video -->

---

How did I make the integration tests run so fast?

First of all, I have used the repository pattern to separate the entire data layer from the rest of the app.

https://codewithandrea.com/articles/flutter-repository-pattern/

---

The app has multiple repositories for various domain areas, such as:

- authentication
- product listings
- shopping cart
- checkout
- product reviews

When the main app runs, it connects to the real data sources (e.g. using Firebase, a REST API, or any other backend)

---

But when I run the tests, I use fake repositories that keep all the data in memory (with 0 delay for async calls).

These are not just simple mocks.

They are fakes that will keep track of state (e.g. shopping cart items), because state is what drives the UI of the entire app.

---

In my tests, I have a big `pumpWidgetAppWithMocks()` method that configures all the fakes (by overriding the default repository providers).

And I can use a technique called Robot Testing to write all the steps in human-readable format:

![](026-full-purchase-flow.png)

---

The result? Super fast integration tests that can test complex user journeys in a matter of seconds.

I'll cover testing in much more detail in my upcoming course.

For now, you can sign up at this page: 
 - [The Complete Flutter Course Bundle](https://codewithandrea.com/courses/complete-flutter-bundle/)

And for more Flutter tips, just follow me: [@biz84](https://twitter.com/biz84)

### Found this useful? Show some love and share the [original tweet](https://twitter.com/biz84/status/1488529134431186946) 🙏
