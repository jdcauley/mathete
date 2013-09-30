# Harp's Blog Boilerplate

_This is a boilerplate to use with the [Harp Platform](http://harp.io/) and [Harp APF](https://github.com/sintaxi/harp) (an open source Asset Pipeline Framework powered by NodeJS)_

## Index

- [How to use it?](#how-to-use-it)
    - [On the Harp Platform](#on-the-harp-platform)
    - [On your own computer](#on-your-own-computer)
- [Controlling your content](#controlling-your-content)
- [Adding new posts](#adding-new-posts)
- [Adding new pages](#adding-new-pages)
- [Migrating from different platforms](#migrating-from-different-platforms)
    - [WordPress](#wordpress)
    - [Tumblr](#tumblr)
- [TODOs](#todos)
- [Support](#support)
- [License](#license)

---

## How to use it?

### On the Harp Platform

1. Login/Signup to the [Harp Platform](http://harp.io/)
2. Create a new application
3. Choose "Blog Boilerplate" as your starting point
4. Start your application
5. Open and edit the files in your Dropbox

### On your own computer

1. [Install Harp APF](http://docs.harp.io/apf/install-update) on your computer
2. Open your terminal and start a new project:

````
$ git clone git@github.com:harp-boilerplates/hb-blog.git my-blog
$ cd my-blog
$ harp server
````

Go to [http://localhost:9966](http://localhost:9966/) from your browser to see your website.

## Controlling your content

Harp brings you back to the basics of the web. Always keep in mind that your directory structure and file names are your URL paths.

What that means is that creating a new page is as simple as creating a new file a throwing some content in it.

### `public/posts`

This is where your posts and their content live.

### `public/_layout.jade`

Indicates the layout of your site, including header, footer and sidebar. External scripts or stylesheets are included in this file. Global elements belong here as well (i.e.: header, nav, sidebar, etc.)

### `public/index.jade`

This is the default page when you visit your domain (i.e.: `http://localhost:9966/`). Here we build the loop that goes through your posts and shows them in the front page.

### `public/_bootstrap`

[Twitter Bootstrap](http://twitter.github.com/bootstrap/) files. This blog boilerplate was built so you can simply replace the `public/_bootstrap` directory whenever you want to upgrade to a new version of Twitter Bootstrap.

You shouldn't modify this directories unless you want to upgrade or downgrade the library.

### `public/fontawesome`

[FontAwesome](http://fortawesome.github.com/Font-Awesome/) files. Same as Twitter Boostrap, this blog boilerplate was built so you can simply replace the `public/fontawesome` directory with a newer or older version of FontAwesome.

You shouldn't modify this directories unless you want to upgrade or downgrade the library.

### `public/css`

This is the place where your custom CSS should live.

## Adding new posts

__1__. Create a new `.jade`, `.html` or `.md` file under `public/posts/`

````
touch public/posts/kittens.html
````

__2__. Enter your post content in the file you just created

__file public/posts/kittens.html:__
````
<h1><a href="/posts/kittens">I love kittens!</a></h1>
<p>This is my first post using Harp!</p>
````

__3__. Open `public/_data.json` and add your new post data

````
{
  "posts": {
    "kittens": {         <-- post's slug
      "type": "post",    <-- 'post' or 'quote'
      "date": {
        "day": "18",
        "month": "feb",
        "year": "2013"
      }
    }
    ...
  }
}
````

## Adding new pages

__1__. Create a new file in public (actually, it can be anywhere you want)

````
touch public/about.html
````

__2__. Enter the page content in the newly created file

__file public/about.html:__
````
<h1>About me</h1>
<p>I love the fotoshopz and taking pictures of foods</p>
````

__3__. Your can now access your page in the browser. I.e.: `http://localhost:9966/about`

## Migrating from a different platform

### WordPress

If you're planning to move your WordPress site, I'd recommend cloning it using wget or curl, i.e.:

```
$ wget --recursive --no-clobber --page-requisites --html-extension --convert-links yourwebsite.com
```

Optionally, you can use [wp2static](https://github.com/jorgepedret/wp2static), a migration tool for WordPress. I created it in a couple of hours, so it's by no means a finished tool, but it'll get you half way there.

### Tumblr

TODO

## TODO
- Integrate [discuss](http://disqus.com/) for comments
- Create sitemap.xml for improving SEO

## Support

Please [create an issue](https://github.com/harp-boilerplates/hb-blog/issues) on github's bug tracker. Feedback and bug reports are greatly appreciated.

## License

MIT