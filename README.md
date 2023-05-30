# Learn Hotwire by building the simplest possible Hotwire and Ruby on Rails - For beginners

## What new in Rails 7?

Rails 7 already comes with lots of things alrady setup for us. It means that now, most of the hard work is alrady done for us:
- Redis is alrady setup and running in our Procfile, and Rails knows how to start using it without us needing to config anything.
- ActionCable is alrady configured in **config/cable.yml**, and will connect to our Redis instance automatically (as long as we are using the default Redis config).
- Stimulus, which handles the frontend side of things, is already setup and running in **app/javascript/controllers**.
- Turbo, which let's use create **turbo_streams** and **turbo_frames**, is also already setup and ready for use to use. 

## Description
1. What is `Hotwire`?
    > Hotwire is a (relatively) new part of Ruby on Rails that allows your Rails frontend to **update live and realtime** - in many cases, **totally replacing frontend framework** like React or Vue.

- Under the hood, Hotwire uses Action cable to send message to the frontend (called **broadcasts**).
- With a couple of `broadcast_to` lines in models, and a few `turbo_stream_from` helpers in views, we can build live UIs without any sort of Javascript framework. Just pure Rails and ERB.

2. More
- `Hotwire` requires `redis` to be running, and a `Procfile` makes it really easy to get it running.
- `Procfile` makes a few things to run in parallel.

3. How to add a broadcast to model?
- Example:
    ```ruby
    class Post < ApplicationRecord
        broadcasts_to -> (post) { :posts }
    end
    ```
- Explain: With this setup, we telling our model to create a `broadcast` whenever it gets either `created`, `updated`, `deleted`. We also specify a specific stream we want it to broadcast to, called `:posts`.
- References: [broadcastable](https://github.com/hotwired/turbo-rails/blob/main/app/models/concerns/turbo/broadcastable.rb)
