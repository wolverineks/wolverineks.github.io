---
layout: post
title:  "Slim + Simple Form + HTML5 Validations + Partials + remote: true"
date:   2016-04-11 18:40:52 -0800
categories: jekyll update rspec tdd
---

Rails has a really cool way to automatically ajaxify your forms.
Rails has a really cool way to render collections.
Rails has a really cool gem for making forms.
Rails has a really cool templating engine called Slim.

In this blog post, I'm going to demonstrate how I used all of them on the same project.

--------------------------------------------------------------------------------------

Let's start with a brand new [rails 4][rails] app, and generate some scaffolding...

![rails new](/imgs/rails_new.png)

--------------------------------------------------------------------------------------

Then add the [slim-rails][slim] gem and the [simple_forms][forms] gem to your gemfile.

![gems](/imgs/gems.png)

--------------------------------------------------------------------------------------

Next, bundle install...

![bundle_install](/imgs/bundle_install.png)

--------------------------------------------------------------------------------------

Let's generate some scaffolding for comments

![scaffolding](/imgs/scaffolding.png)

--------------------------------------------------------------------------------------

Create and migrate the database.

![create_migrate](/imgs/create_migrate.png)

--------------------------------------------------------------------------------------

Let's run rails server to see what we get...

![server](/imgs/server.png)

--------------------------------------------------------------------------------------

So far so good...

![rails](/imgs/rails.png)

--------------------------------------------------------------------------------------

Let's checkout some of the magic of rails...

![comments](/imgs/comments.png)

--------------------------------------------------------------------------------------

Just for fun, let's add the comment form to the comment index.
To do this, add this single line to the comments/index,

![form](/imgs/form.png)

--------------------------------------------------------------------------------------

Add this line to the comments_controller.rb

![comment](/imgs/comment.png)

--------------------------------------------------------------------------------------

Copy the inside of the each loop on the index into a partial named "comment.html.slim".

![loop](/imgs/loop.png)

--------------------------------------------------------------------------------------

Change the index to render @comments

![render](/imgs/render.png)

--------------------------------------------------------------------------------------

Change the form to 'remote: true'

![remote](/imgs/remote.png)

--------------------------------------------------------------------------------------

Back in the controller, add this line.

![format_js](/imgs/format_js.png)

--------------------------------------------------------------------------------------

Change the form to use simple_form

![simple_form](/imgs/simple_form.png)

--------------------------------------------------------------------------------------

Add Validations to the comments model

![validations](/imgs/validations.png)

--------------------------------------------------------------------------------------

Adding validations and using simple_form automatically gets you some sweet HTML5 client-side validations.

![html5_validations](/imgs/html5_validations.png)

--------------------------------------------------------------------------------------

Create and add the following to a template in comments called 'create.js.slim'.

[Yes, the pipe at the beginning is necessary][escape].

![create_js](/imgs/create_js.png)

--------------------------------------------------------------------------------------

And if everything went according to plan, you should have a pretty sweet ajaxified comments index/new/form thing.


![blog](/imgs/blog.gif)



[rails]:  http://www.rubyonrails.com
[slim]:   https://github.com/slim-template/slim-rails
[forms]:  https://github.com/plataformatec/simple_form
[escape]: http://www.rubydoc.info/gems/slim/frames#Text_content
