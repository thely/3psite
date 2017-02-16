## Third Practice NMF Site

### Site Setup

Each year of the festival is its own folder (called 3p16, 3p17, etc), with the homepage set to the folder page. Each year will also have its own sub-theme that inherits from `3pbase`.

### Important File Locations

Everything we change is in `user`.

```
- grav/
- - user/
- - - pages/  		# all page content
- - - themes/
- - - - 3pbase/ 	# base theme

### 3pbase Theme/Page Settings

The following is from `3pbase.yaml`:

```
menufromhomepage:
  enabled: true
poster_image_location: /3p16/bgimg
```

Keep `menufromhomepage` enabled; it displays navigation for the current year's pages only. Otherwise, all pages in the Pages folder would be in the nav.

`poster_image_location` is the location of the background image that corresponds to that year's poster. To set this correctly:

1. First, add a new page. Set the Folder Name to `bgimg`, the Parent Page to the current year's folder, and set Visible to "No."
2. In the page's edit mode, add the image to the Page Media.
3. Set `poster_image_location` to `/3pXX/bgimg/`, where XX is the current year.

#### Making New Themes

Make a copy of `/grav/user/themes/3pbase`, and give the folder a different name (like `3p17` or similar). Rename `3pbase.yaml` to `3p17.yaml`, and add `/user/themes/3p17` to the `streams: prefixes: ` section of `3p17.yaml`, following the formatting of all the lines below. This means that your new theme will inherit both from the 3pbase theme, and from Grav's bones-vanilla theme.

Finally, under blueprints.yaml, give the theme a different title and description (e.g. Third Practice 2017 or something).

Assuming 3p17, go to each page in the 3p17 folder (including 3p17 itself) and change their Theme to "Third Practice 2017". Alternatively, you can also do this by editing each page's `default.md` (ex: `/user/pages/01.about/default.md`) and adding `theme: 3p17` in the area where `title, visible, fontawesome`, etc. are listed.