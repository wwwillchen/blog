---
date: 2023-12-26
---

# Server-driven UI

Server-driven UI describes the paradigm where the server is responsible for determining the overall UI composition from the layout to the discrete components rendered on the page.

I see three key motivations of why frameworks adopt a server-driven UI paradigm:

1. Enable a better user experience by making performance optimizations straightforward.
1. Provide a better developer experience, particularly for non-JS developers.
1. Enable faster release velocity, particularly for mobile apps.

## Better user experience

I think [Remix](http://remix.run/) was one of the early entrants (2021) in the React scene to emphasize server-driven UIs. Remix in particular focuses on improving performance by avoiding data waterfalls by emphasizing what they call [nested routes](https://remix.run/docs/en/main/discussion/routes). Essentially, all the main components on the page should *not* have data dependency and instead be able to fetch its data based on the route parameters.

Since then, React itself has embraced server-driven UIs through [React Server Components](https://react.dev/blog/2023/03/22/react-labs-what-we-have-been-working-on-march-2023#react-server-components). Dan Abramov's talk [React from another dimension](https://youtu.be/zMf_xeGPn6s?si=OBGe6XrTW_v-DC1Y) is a fun step-by-step walkthrough of building a React app, but imagining React as a server-driven framework.

## Better developer experience

Another kind of motivation for server-driven UI frameworks is the desire to use another language besides JavaScript to build rich web apps.

[htmx](https://htmx.org/) is a popular option for developers using a non-JS language because it pairs well with standard HTML-based templating solutions by enabling JS-like interactivity without actually writing JS.

In the Python world, there's many server-driven UI frameworks with the main emphasis of catering to Python developers (e.g. data scientists, ML engineers) who don't want to learn a JS and a front-end framework to build a web app to demo something. [Streamlit](https://streamlit.io/) and [Gradio](https://www.gradio.app/) are the two most popular options, but there are many other Python-based UI frameworks such as [Solara](https://solara.dev/), [NiceGUI](https://nicegui.io/), [JustPy](https://justpy.io/), [remi](https://github.com/rawpython/remi), and [Starfyre](https://sanskar.wtf/posts/hello-starfyre).

Other language ecosystem have developed their own equivalent solutions. For example, Elixir has [LiveView](https://youtu.be/FADQAnq0RpA?si=zCECWqZhfk3LXM1V) and Ruby on Rails has [Turbo](https://turbo.hotwired.dev/).

## Faster release velocity

The last kind of motivation that I often see deals with the reality that mobile apps oftentimes have slower release velocity due to the app review cycle.

Flutter's [rfw](https://pub.dev/packages/rfw) package (Remote Flutter Widgets) and Airbnb's [server-driven UI system](https://youtu.be/Ir8lq4rSyyc?si=tcQMo-iDb0DpIJPp) are examples of addressing this issue.

## Conclusion

One of the most interesting projects in this space is [Hyperfiddle electric](https://github.com/hyperfiddle/electric) which compiles a single Clojure codebase into a client and server application. This blurring of the client-server boundary is fascinating and I think it's something to pay attention to as we see more and more traditionally client-driven frameworks become more server-driven.

One of the key takeaways that I have with server-driven UI frameworks is that each of these reasons provide a "big win". Otherwise, it's not really worth embracing a paradigm shift.