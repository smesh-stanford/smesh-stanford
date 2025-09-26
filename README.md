# smesh-stanford
This is created with GitHub pages/Hugo! View it here: [https://smesh-stanford.github.io/]()

The coolest part about this theme is a majority of pages can be created in simple markdown. And if you're feeling real fancy, then you can add HTML/CSS. This is supported via Hugo which allows you to create entire websites using mainly markdown and *some* HTML/CSS snippets (so the barrier to entry to adding to this website is very low).

The way GitHub pages work is that we can host the page under the `smesh-stanford` organization for free using static pages. Since our website doesn't require a database, complex bells and whistles, GitHub pages and Hugo is a perfect use case for SMesh's website.

## Prerequisites
- [Install hugo](https://gohugo.io/installation/)
- Understand that this website is based on the template [here](https://github.com/iossefy/kaslaanka?tab=readme-ov-file). Please refer to it if you want more details on the capabilities of the template although it is quite bare bones.


## Create a blog post
To create a post you'll be having people read about SMesh so speedy. Just do this:
```
hugo new blog/name_of_my_post.md
```

This will create a file in `content/blog`. Any posts will appear under the `Blog` tab and will also be listed on the homepage. Write away!

## Local Development
If you want to see your changes locally prior to merging to main do:
```
hugo server
```

In the case your markdown files are defined as drafts (which is in the header of the `.md` file under `draft:`), compile it as
```
hugo server -D
```

When you compile the server, the render of the website appears in your `public` folder. So if you need to troubleshoot issues with the pages you're writing vs. how it's getting compiled by hugo, refer to the `public` folder.

## Testing deployment to GitHub
Although there are much better ways to test deployment in stage and production environments to not affect the deployed website, here's an easy way to double check when you merge you won't break the way GitHub deploys the page:
- Navigate to the repo settings (gear on front repo page)
- Under code and automation, click pages
- For the branch it's deploying to, pick the one you are actively developing on

> [!WARNING] This will change the actual site that's hosted!

### General Recommendations/Troubleshooting
- hugo doesn't like it when you add HTML directly into markdown. Instead it supports `shortcodes`. Refer to `layouts/shortcodes` for examples
- If a file is failing to display: 
    - Check the log ensuring hugo doesn't think your markdown doesn't contain HTML (in this case it will omit it, causing it to be blank)
    - Ensure it's not a draft and you're compiling with the `-D` flag for running the server with drafts
## Push new changes
If you made some new changes, go ahead and make a branch, push it up to a MR, then merge it to main. Whatever is on main becomes the version that is deployed to our github.io page!