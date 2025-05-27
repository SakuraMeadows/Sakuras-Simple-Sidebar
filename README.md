<h1 align="center">
  🌸Sakura's Simple Sidebar🌸
</h1>

<h2 align="center">
  A simple Firefox theme using Sidebery sidebar.
</h2>

## Getting Started

Follow these steps to install the theme:

1. **Open** Firefox
2. **Install** the [`Sidebery`](https://addons.mozilla.org/en-US/firefox/addon/sidebery/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search) extension from the Firefox extension store.
3. In the adress bar, **Type** `about:config`, then press <kbd>Enter</kbd>.
4. If a warning page appears, **click** `Accept the Risk and Continue` to access the `about:config` page.
5. **Search** for the following preferences using the search bar at the top of the `about:config` page, and **ensure** the following preferences are `true`:

   - `toolkit.legacyUserProfileCustomizations.stylesheets`
   - `svg.context-properties.content.enabled`
   - `sidebar.old-sidebar.has-used`
 
	**ensure** the following preferences are `false`:
   - `sidebar.revamp`

6. <kbd>Right Click</kbd> on the Sidebery extension icon in the top bar, `Open Settings`.
7. On the left side, **Click** `Styles Editor` then input this css:
- If using the `amoledDarkTheme`
```css
#nav_bar{
	display: none;
}
#root_container{
	--s-frame-bg: #000000;
    --s-frame-fg: #fcbccd;
	--s-act-el-fg: #fcbccd;
}
.ScrollBox{
	--scroll-color: #111111;
}
```
- If using the `darkerTheme`
```css
#nav_bar{
	display: none;
}
#root_container{
	--s-frame-bg: #11111b;
    --s-frame-fg: #fcbccd;
	--s-act-el-fg: #fcbccd;
}
.ScrollBox{
	--scroll-color: #181825;
}
```
- If using the `darkTheme`
```css
#nav_bar{
	display: none;
}
#root_container{
	--s-frame-bg: #303446;
    --s-frame-fg: #fcbccd;
	--s-act-el-fg: #fcbccd;
}
.ScrollBox{
	--scroll-color: #414559;
}
```
- If using the `lightTheme`
```css
#nav_bar{
	display: none;
}
#root_container{
	--s-frame-bg: #eff1f5;
    --s-frame-fg: #fcbccd;
	--s-act-el-fg: #fcbccd;
}
.ScrollBox{
	--scroll-color: #e6e9ef;
}
```
- Then **Replace** both `#fcbccd` with your accent color if different.

- Optionally, in `General` settings, **Disable** "Use Native Scroll-bars" to hide the scroll bar entirely.

9. **Type** `about:profiles` in the address bar and press <kbd>Enter</kbd>.
10. **Look for** the in-use profile, or otherwise the profile you wish to theme, and **click** `Open Folder` on the section labeled `Root Directory`.
11. **Download** the `chrome.zip` file from the [**latest release**](https://github.com/SakuraMeadows/Sakuras-Simple-Sidebar/releases/latest).
12. **Extract** the contents of `chrome.zip` into your Firefox profile directory. Ensure the file structure is as follows: Firefox > Profiles > [profile] > chrome > [css files]
13. If you are on **Windows** open the `userChrome.css` file, If you are on **Linux** ignore this step.
- By default the window controls are set up for Linux as I assume that is where people are more likely to theme Firefox, to change it for windows, simply **Uncomment**  `noTablineWindows.css` by removing the `/*` and `*/` on either end, then **Comment** out `noTablineLinux.css` by placing `/*` at the beginning and `*/` at the end.
```css
@import "hideBookmarks.css";
/*@import "noTablineWindows.css";*/
@inpurt "noTablineLinux.css";
```
14. **Restart** Firefox to apply the changes.

## Support & Suggestions

If you have any **suggestions** or **bug reports** please create an issue at [GitHub Issues](https://github.com/SakuraMeadows/Sakuras-Simple-Sidebar/issues) so I can further improve the theme!

## Default Customization

If you wish to change colors such as the accent color, navigate to the `chrome` folder from before. **Open** the `userChrome.css` file in a text editor. It should look something like this:
```css
/* Base Color Theme Options */

/*@import "amoledDarkTheme.css";*/
@import "darkerTheme.css";
/*@import "darkTheme.css";*/
/*@import "lightTheme.css";*/

/* Functional Options */

@import "changeColors.css";
@import "removeExtras.css";
@import "hideBookmarks.css";
@import "noTabline.css";
@import "sidebery.css";

:root{
    --accent-color: #fcbccd; /* Change this color to your liking, default is a Cherry Blossom Pink. Used in Amoled, Dark, and Darker color themes */
    --accent-color-light: #ca56ab; /* Change this color to your liking, default is a Medium Pink. Used in light theme */
}
```
Here, the accent color for both dark and light themes is easily changed. `--accent-color` and `--accent-color-light`. Just change the hex code in those variables.

If you wish to change the theme color, **Comment** out the theme in use by placing `/*` at the beginning and `*/` at the end, then **Uncomment** the color option you want to use by removing the `/*` and `*/` on either end.

After any modifications, **Save** the file and **Restart** Firefox.


## Manual Customization

By default the Darker, Dark, and Light themes use colors picked from the [Catppuccin Color Pallete](https://catppuccin.com/palette/). If you wish to change this, there are 2 options:
**1.  Modifying `:root`**

1. **Navigate** to the `chrome` folder from before. Open the `userChrome.css` file in a text editor. 

2. **Comment** out the theme options by placing `/*` at the beginning and `*/` at the end, the other 3 themes should already be commented out:
```css
/*@import "amoledDarkTheme.css";*/
/*@import "darkerTheme.css";*/
/*@import "darkTheme.css";*/
/*@import "lightTheme.css";*/
```

3. In the `:root` section, **Add** the Theme color variables with the tag `!important`
```css
:root{
    --accent-color: #fcbccd; /* Change this color to your liking, default is a Cherry Blossom Pink. Used in Amoled, Dark, and Darker color themes */
    --accent-color-light: #ca56ab; /* Change this color to your liking, default is a Medium Pink. Used in light theme */
    /* The variables above are already included, add the variables below*/
	--background-color: #000000 !important;
	--background-color2: #000000 !important;
	--background-color3: #000000 !important;
	--link-color: #85c1dc !important;
}
```
4. Change the hex codes to colors of your choosing, then **Save** the file and **Restart** Firefox.

**Make sure to add any color changes to the Sidebery Styles Editor**

**2. Creating a new `theme.css` file.**

1. **Navigate** to the `chrome` folder from before.
2. **Create** a new file, name it whatever you want as long as it ends in `.css`
3. **Add** this to the new file:
```css
:root{
  --background-color: #000000;
  --background-color2: #000000;
  --background-color3: #000000;
  --link-color: #85c1dc !important;
}
```
4. Change the hex codes to colors of your choosing, then **Save** the file
5. Open the `userChrome.css` file.

6. **Comment** out the theme options by placing `/*` at the beginning and `*/` at the end, the other 3 themes should already be commented out:
```css
/*@import "amoledDarkTheme.css";*/
/*@import "darkerTheme.css";*/
/*@import "darkTheme.css";*/
/*@import "lightTheme.css";*/
```
7. **Import** your new theme file:
```css
/*@import "amoledDarkTheme.css";*/
/*@import "darkerTheme.css";*/
/*@import "darkTheme.css";*/
/*@import "lightTheme.css";*/
@import "fileName.css";
```
8. **Save** the file, then **Restart** Firefox.

**Make sure to add any color changes to the Sidebery Styles Editor**

## Credits

- [MaterialFox Updated](https://github.com/edelvarden/material-fox-updated) by [edelvarden](https://github.com/edelvarden) - Used README Markdown as Template
- [Catppuccin Color Pallete](https://catppuccin.com/palette/) - Default colors used
