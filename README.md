# Demo Elixir Phoenix LiveView

Demonstration of:

* Elixir programming language
* Phoenix web framework
* LiveView socket module
* Chirp Twitter-like app 
* Credit to Chris McCord

Create a Phoenix app named "chirp":

```sh
mix phx.new chirp --live && cd chirp
```

Generate a live resource:

```sh
mix phx.gen.live Timeline Post posts username body likes_count:integer reposts_count:integer
```

Output:

```sh
* creating lib/chirp_web/live/post_live/show.ex
* creating lib/chirp_web/live/post_live/index.ex
* creating lib/chirp_web/live/post_live/form_component.ex
* creating lib/chirp_web/live/post_live/form_component.html.leex
* creating lib/chirp_web/live/post_live/index.html.leex
* creating lib/chirp_web/live/post_live/show.html.leex
* creating test/chirp_web/live/post_live_test.exs
* creating lib/chirp_web/live/modal_component.ex
* creating lib/chirp_web/live/live_helpers.ex
* creating lib/chirp/timeline/post.ex
* creating priv/repo/migrations/20200724010645_create_posts.exs
* creating lib/chirp/timeline.ex
* injecting lib/chirp/timeline.ex
* creating test/chirp/timeline_test.exs
* injecting test/chirp/timeline_test.exs
* injecting lib/chirp_web.ex

Add the live routes to your browser scope in lib/chirp_web/router.ex:

    live "/posts", PostLive.Index, :index
    live "/posts/new", PostLive.Index, :new
    live "/posts/:id/edit", PostLive.Index, :edit

    live "/posts/:id", PostLive.Show, :show
    live "/posts/:id/show/edit", PostLive.Show, :edit


Remember to update your repository by running migrations:

    $ mix ecto.migrate
```

Migrate:

```sh
mix ecto.migrate
```

Output:

```sh
...

18:09:15.939 [info]  == Running 20200724010645 Chirp.Repo.Migrations.CreatePosts.change/0 forward

18:09:15.942 [info]  create table posts

18:09:15.957 [info]  == Migrated 20200724010645 in 0.0s
```

Run server:

```sh
mix phx.server
```

Browse http://localhost:4000/posts

