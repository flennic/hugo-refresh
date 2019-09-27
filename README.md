# The ReFresh theme for Hugo

**ReFresh** is a theme for the [Hugo](https://gohugo.io) static site generator _highly_ modified from the awesome [Fresh](https://github.com/StefMa/hugo-fresh) theme (below you can find the list of changes to the original theme). 

You can find a live demo of the original Fresh theme [here](https://themes.gohugo.io/theme/hugo-fresh/) or a demo of the Hugo ReFresh theme [here](https://themes.gohugo.io/theme/hugo-refresh/).

You can find another example of ReFresh theme in [my personal website](https://rjordaney.is/). 

![ReFresh theme logo](images/screenshot.png)

> This theme is intended for personal website and blog. If you'd like to extend the theme to include other functionalities submit a pull request.

## Getting started

To create a new site using Hugo ReFresh:

```bash
# Create site and cd into it
hugo new site my-site && cd my-site

# Clone the ReFresh theme into the themes folder
git init
git submodule add https://github.com/PippoRJ/hugo-refresh.git themes/hugo-refresh

# Remove the default config
rm config.toml

# Fetch the example config
curl -O https://raw.githubusercontent.com/PippoRJ/hugo-refresh/master/exampleSite/config.yaml

# Run the site locally
hugo server -D

# Open the site in your browser
open http://localhost:1313
```

To run the Example Site using Hugo ReFresh:

```bash
# Create site and cd into it
hugo new site my-site && cd my-site

# Clone the ReFresh theme into the themes folder
git init
git submodule add https://github.com/PippoRJ/hugo-refresh themes/hugo-refresh

# Remove the default config
rm config.toml

# Copy the Example site content and configuration in my-site
cp -R themes/hugo-refresh/exampleSite/* ./

# Open the site in your browser
hugo server -D
```

## Troubleshooting

If you see `error: failed to transform resource: TOCSS: failed to transform "style.sass"` when attempting to run your `hugo server`, make sure you have the extended version of Hugo installed:

```bash
# On Ubuntu:
snap refresh hugo --channel=extended
```

## Customizing your page

There are different configuration options for Hugo ReFresh including options for: the navbar, the sidebar, the homepage, fonts, colours landing and images. 
Read the comments in the `config.yaml` file to know more.


## List of shortcodes you can use in your articles with description:

<details>
<summary> title1.html, title2.html, title3.html, title4.html, title5.html, title6.html </summary>

Usage example:

```
{{< title1 "My awesome title" "my-title-id">}}
```
The **first parameter** is the title of the shortcode (in this example is "My awesome title").

The **second paramter** is the ID of the shortcode (in this example is "my-title-id"). 
It can be used in links to the same page as:
```
[link to the title](#my-title-id)
```

</details>

<details>
<summary> code.html </summary>

This shortcode builds a centered page that is two-third of the full size of the page.

Usage example:

```
{{% code %}}
\`\`\`
    $ sudo bash -c 'echo 0 > /proc/sys/kernel/randomize_va_space'
\`\`\`
{{% /code %}}
```

</details>

<details>
<summary> codeAll.html </summary>

This shortcode builds a centered page that is as wide as the full size of the page.

Usage example:

```
{{% codeAll %}}
\`\`\`
    $ dmesg | tail
    ......
    [13401.299114] overflow64[16566]: segfault at 616161616161 ip 0000616161616161 sp 00007fffffffddb0 error 14 in libc-2.27.so[7ffff79e4000+1e7000]
\`\`\`
{{% /codeAll %}}
```


</details>

<details>
<summary> figure.html </summary>

This shortcode resize an image that with the width and/or height that you specify

Usage example:

```
{{% figure src="images/the_stack.png" width="700" %}}
{{% figure src="images/the_stack.png" height="700" %}}
```

The parameter **src** is the location of the image relative to the location of the file where the shortcode has been used.
The parameter **width** is the width of the image.
The parameter **height** is the height of the image.

</details>

<details>
<summary> twoFigure.html </summary>

This shortcode shows 2 images one next to the other with the possibility to resize them.

Usage example:

```
{{% twoFigure src1="images/overflow_1.png" width1="700" src2="images/overflow_2.png" width2="700" %}}
```

The parameter **src1** is the location of the right image relative to the location of the file where the shortcode has been used.
The parameter **width1** is the width of the right image.
The parameter **height1** is the height of the right image.

The parameter **src2** is the location of the left image relative to the location of the file where the shortcode has been used.
The parameter **width2** is the width of the left image.
The parameter **height2** is the height of the left image.

With a small screen these images will be shown one on top of the other.

</details>

<details>
<summary> book.html </summary>



</details>

<details>
<summary> code_tabs.html </summary>



</details>

<details>
<summary> exercise.html </summary>



</details>


<details>
<summary> code_tabs.html </summary>



</details>


<details>
<summary> codeInLine.html </summary>



</details>

<details>
<summary> message_blue.html, message_dark.html, message_green.html, message_red.html, message_yellow.html </summary>



</details>

<details>
<summary> notificationBlue.html, notificationGreen.html, notificationRed.html, notificationYellow.html </summary>



</details>

<details>
<summary> site_blue.html, site_green.html, site_lightgreen.html, site_red.html, site_yellow.html </summary>



</details>




## List of modifications from the original theme

* The ReFresh theme was transformed from single page template to multipage. 

* The left side menu now contains page tags along with theirs post counter.

* The _list_ and _terms_ types of pages contain a list of the post summaries.

* The images used to build the summares are resized to allow better usage of the bandwith.

* The js and css files are minified (with a configurable option on the `config.yaml`).

* The menu is built following the structure of the `content` folder. Two levels are allowed at the moment.

* The `navbar-burger` used in the theme's menu is removed (it was displayed when the page was resized).

* The `.sass` files are now processed with `resources.ExecuteAsTemplate` so that it is possible to use variables from the `config.yaml`.

* An option in the config.yaml was added to confifure the font-family for the navbar, sidebar and content of the page.

* [Bulma](https://bulma.io/) (the css framework the theme is based on) is now updated to version 0.7.5 because in the new version the class _content_ has a separate style to allow modification that will impact only the contents of the posts.

* [highlight.js](https://highlightjs.org/) was added to better highlight the code sections of the posts. I chose the style **monokai-sublime**.

* [highlightjs-line-number.js](https://github.com/wcoder/highlightjs-line-numbers.js/) was added to have the line number at the beginning of each line of code in a code sections of a post.

* An option was added to show the date of the last modification in a post.

* A shortcode was added to resize the images and save bandwidth in a post content.
