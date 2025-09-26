# smesh-stanford
This is created with GitHub pages/Hugo! View it here: https://smesh-stanford.github.io/smesh-stanford/

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
Change in the `.github/workflows/hugo.yml` file the branch from main to whatever your branch you are trying to test deployment for. This is so that we run the GitHub build/deployment pipeline with your branch, since it will only ever try to build/deploy main. Change this back prior to merging!

> [!WARNING]
> Testing deployment will actually update the site being deployed at the github.io link. In the future, we may want to setup a cleaner way of doing this perhaps with some sort of stg/prd. As of right now, any branch can deploy the GitHub pages website for debugging purposes. Although, in the future, it'd be nice to make this safer.

### General Recommendations/Troubleshooting
- hugo doesn't like it when you add HTML directly into markdown. Instead it supports `shortcodes`. Refer to `layouts/shortcodes` for examples
- If a file is failing to display: 
    - Check the log ensuring hugo doesn't think your markdown doesn't contain HTML (in this case it will omit it, causing it to be blank)
    - Ensure it's not a draft and you're compiling with the `-D` flag for running the server with drafts
## Push new changes
If you made some new changes, go ahead and make a branch, push it up to a MR, then merge it to main. Whatever is on main becomes the version that is deployed to our github.io page!
