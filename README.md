<h1 align="center">
  🌸Sakura's Simple Sidebar🌸
</h1>

<h2 align="center">
  A simple Firefox theme using Sidebery sidebar.
</h2>

## Preview

![](https://github.com/SakuraMeadows/Sakuras-Simple-Sidebar/blob/39908072a7fe102f91658d5df73ce24ad24d6290/page%20assets/SakurasSimpleSidebarExample.gif)

## Getting Started

**Note: This theme is meant as a vertical tabs Firefox theme, however, it is possible to enable horizontal tabs as a fallback. I have not put much work into the horizontal tabs yet as it is currently meant to be used temporarily as a fallback if the vertical tabs stop working**

Follow these steps to install the theme:

1. **Open** Firefox
2. **Install** the [`Sidebery`](https://addons.mozilla.org/en-US/firefox/addon/sidebery/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search) extension from the Firefox extension store.
3. In the address bar (aka Search bar, or URL bar), **Type** `about:config`, then press <kbd>Enter</kbd>.

![](https://i.imgur.com/W6MwLA1.png)

4. If a warning page appears, **click** `Accept the Risk and Continue` to access the `about:config` page.
5. **Search** for the following preferences using the search bar at the top of the `about:config` page, and **ensure** the following preferences are `true`:

   - `toolkit.legacyUserProfileCustomizations.stylesheets`
   - `svg.context-properties.content.enabled`
   - `sidebar.old-sidebar.has-used`
 
	**ensure** the following preferences are `false`:
   - `sidebar.revamp`

6. **Download** and **Extract** the `sidebery.zip` file from the [**latest release**](https://github.com/SakuraMeadows/Sakuras-Simple-Sidebar/releases/latest).
7. <kbd>Right Click</kbd> on the Sidebery extension icon in the top bar, `Open Settings`.
8. On the left side, **Click** `Help` and then `Import Addon Data`.

![](https://i.imgur.com/IQ8P3iQ.png)
Then select the downloaded file. This file does not need to be kept after installation.
- Optionally, in `General` settings, **Disable** "Use Native Scroll-bars" to hide the scroll bar entirely.
![](https://i.imgur.com/tHm2KlI.png)
9. **Type** `about:profiles` in the address bar, as done before with `about:config`, and press <kbd>Enter</kbd>.
10. **Look for** the in-use profile, or otherwise the profile you wish to theme, and **click** `Open Folder` on the section labeled `Root Directory`.
![](https://i.imgur.com/rtZVSdW.png)
**If you are on Linux and the `Open Folder` button does not work, check this path: `/home/<user>/.var/app/org.mozilla.firefox/.mozilla/firefox/<profile>`** or submit [an issue.](https://github.com/SakuraMeadows/Sakuras-Simple-Sidebar/issues)

11. **Download** the `chrome.zip` file from the [**latest release**](https://github.com/SakuraMeadows/Sakuras-Simple-Sidebar/releases/latest).
12. **Extract** the contents of `chrome.zip` into your Firefox profile directory. Ensure the file structure is as follows: Firefox > Profiles > [profile] > chrome > [css files]
13. If you are on **Linux** open the `userChrome.css` file, If you are on **Windows** ignore this step.
- By default the window controls are set up for Windows, to change it for linux, simply **Uncomment**  `noTablineLinux.css` by removing the `/*` and `*/` on either end, then **Comment** out `noTablineWindows.css` by placing `/*` at the beginning and `*/` at the end.
```css
@import "hideBookmarks.css";
/*@import "noTablineWindows.css";*/
@inpurt "noTablineLinux.css";
```
14. **Restart** Firefox to apply the changes.

## Support & Suggestions

If you have any **suggestions** or **bug reports** please create an issue at [GitHub Issues](https://github.com/SakuraMeadows/Sakuras-Simple-Sidebar/issues) so I can further improve the theme!
This is my first ever Firefox theme, in fact this is the first time I have used css in general, so any help would be greatly appreciated!

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
- [DownToneUI](https://github.com/oviung/DownToneUI-Firefox/tree/main) - Ideas for better installation instructions and things I could improve
- [Firefox CSS Community](https://www.reddit.com/r/FirefoxCSS/) - Help with various bugs/ideas
- [MrOtherGuy CSS hacks](https://github.com/MrOtherGuy/firefox-csshacks) - Css code ideas, not directly taken but referenced from
