# Learn Hotwire by building the simplest possible Hotwire and Ruby on Rails - For beginners

## Description
1. What is `Hotwire`?
    > Hotwire is a (relatively) new part of Ruby on Rails that allows your Rails frontend to **update live and realtime** - in many cases, **totally replacing frontend framework** like React or Vue.

- Under the hood, Hotwire uses Action cable to send message to the frontend (called **broadcasts**).
- With a couple of `broadcast_to` lines in models, and a few `turbo_stream_from` helpers in views, we can build live UIs without any sort of Javascript framework. Just pure Rails and ERB.

2. More
- `Hotwire` requires `redis` to be running, and a `Procfile` makes it really easy to get it running.
- `Procfile` makes a few things to run in parallel.