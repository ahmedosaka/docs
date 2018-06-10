# Working with images

In Kumu, there are a number of different places where you can use images to enrich your project. This guide covers:

- [Adding images to elements](#add-images-to-elements)
- [Adding a background image](#add-a-background-image)


## Add images to elements

If you are [building a map by hand](/getting-started/first-steps.html#build-your-map-by-hand), you can also easily upload an image file from your computer directly to Kumu. Just click an item (element, connection, or loop) on your map, click the camera icon in the upper right of the [profile](/guides/profiles.html), and click "select a file" to upload your image.

![Gif showing how to upload an image to Kumu](/images/upload-image.gif)

You can upload images to descriptions and the map overview as well. To do this, click to edit any text area in the [side panel](/overview/map-editor.html#side-panel), and look for "select a file" below the text area.

<p class="alert alert-info">
Note: when you're uploading images, only JPEG, PNG, and GIF files smaller than 5mb are supported at this time.
</p>

Instead of uploading a file, you can also add a URL to an image hosted publicly on the web. This is particularly useful when you're [importing a spreadsheet](/guides/import.md) into Kumu—just make sure to add an "Image" column in the the "Elements" sheet, then in the "Image" column, add the public URL for the image that you want to add to each element.


#### Troubleshooting image URLs

Are you using image URLs and not seeing images on the map? Here are a few steps you can take to troubleshoot the problem:

- Make sure your link leads directly to the image, rather than a webpage with the image on it
- Make sure your image URL is using a secure connection—that is, the link starts with `https` instead of just `http`
- Disable image proxy: click the menu icon <i class="fa fa-bars"></i> in the upper left of the map editor, then click **Admin** and click **disable it**.


#### Using decorations to add images

With decorations, you can create rules that add the same image to multiple elements. To do this, [open the element decoration builder](/guides/decorate.html#refine-your-decorations), select which elements the rule will apply to, and check the box next to "Add image". You'll be prompted to add an image URL or upload an image from your computer, and your image will be added to the selected elements.


# Add a background image

To add a background image to a map, you can use a snippet of code in the [Advanced Editor](/overview/view-editors.md#advanced-editor). The following instructions will help you add an image of a world map, but they can be adapted to add any background image.

1. Create an element and change its label to `background`.
2. Copy/paste the following code into your Advanced Editor:
```
#background {
    image-url: url(https://cdn.rawgit.com/AlexVipond/hosted-svgs/master/world-map.svg);
    layer: background;
    shape: square;
    size: 5000;
    color: transparent;
    image-size: contain;
    image-resolution: original;
    label-visibility: none;
}
```
3. Click **SAVE** at the bottom of the Advanced Editor to save your changes.

You can replace the `image-url` in that code with a link to any image online. To get an image URL from any image you see online, you can right-click the image and select "Copy Image Address". When you're pasting your new image url into the Advanced Editor, make sure to put it inside the `url( )` parentheses.

<p class="alert alert-warning">
Some images won't be displayed in Kumu, because they are using an insecure connection (the link starts with <code>http</code> instead of <code>https</code>), or because they are traveling through a proxy server.<br><br>If your image isn't displaying in Kumu, you can save the file to your computer and follow the steps below to upload the image directly to your Kumu project.
</p>

You can also use the [Basic Editor](/overview/view-editors.md#basic-editor) to upload an image from your computer to your Kumu project—this will override the `image-url` in your code. Follow these steps:

1. Complete the initial three steps above to create your background element, add your Advanced Editor code, and save your changes.
1. Click the Settings icon <i class="fa fa-sliders"></i> to open the Basic Editor.
1. Click **More Options**
1. Select **Decorate elements**
1. In the element decoration builder, set the dropdown at the top to "Decorate custom selection"
1. Set the second row of dropdown menus to `Label` `is` `background` (assuming your background element's label is `background`)
1. Check the box next to "Add image", then click "upload image"
1. Upload your image, and click **Done** at the bottom of the decoration builder
1. Click **SAVE** at the bottom of the Basic Editor

<p class="alert alert-info">
If you need to adjust the position of the image element in the map, you'll need to remove the <code>layer: background;</code> line. Click and drag the element to adjust its position, and then add back that line of code when you're done.
</p>


**Notes:**
* "background" is the label of the element that will contain the background image in this example, but the label can be anything you want. Just make sure you update the `#background` [selector](/guides/selectors.html) in your code to match your new label.
* `image-resolution` can have values of `auto`, `original`, or any number. The number you include (e.g. `1000`) will adapt the resolution for an image of that width (1000px).

As always, if you have any questions on how this works, email us at [support@kumu.io](mailto:support@kumu.io) for help!



<span class="edit-link"><a href="https://github.com/kumu/docs/blob/master/guides/images.md" target="_blank"><i class="fa fa-github"></i> edit this page</a></span>