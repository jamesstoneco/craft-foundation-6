## Craft Foundation 6 Sass/Gulp Starter Kit
#### Configuration starter kit for Sassy  [Foundation 6](http://foundation.zurb.com/sites/docs/) with [CraftCMS](http://craftcms.com/) 2 OR 3  

With this simple configuration you will be able to
- add Foundation 6 to your Craft site
- save hours of time in your front-end development
- get live previews in the browser while developing without ever hitting reload (browser-sync)

You can get Foundation 6 a plethora of ways, we'll use the foundation-cli for this.

You can `$ npm install --global foundation-cli` and then use this starter kit 
- or - 
You can grab/setup Foundation 6 one of the many other ways and copy over the `_settings.scss` file into your `/src/` directory yourself.

**Foundation Install Docs**:
[Foundation Cli Installation Guide](http://foundation.zurb.com/sites/docs/installation.html)  
[foundation-sites on github](https://github.com/zurb/foundation-sites)  

**Note**: this is simply a jumping off point for those looking to work with Foundation in their Craft build. there are endless ways to do this, if you have an idea - please feel free to add to or correct this repo, and hey, thank you.

#### Setup:  
********************

#####Step 1.
    git clone https://github.com/fndaily/craft-foundation-6 your_project_dir
    cd your_project_dir
    bower install
    npm install
    cp bower_components/foundation-sites/scss/settings/_settings.scss src/scss/_settings.scss

#####Step 2.
    Grab a copy of Craft CMS and replace the /craft/ directory with your newly downloaded copy.

#####Step 3.
    Optionally, update "http://YOURDOMAIN.dev" in `gulpfile.babel.js` line 97

********************

**Directory Structure**:

- `/bower_components` - where bower gets installed when running `$bower install`
    - `/foundation-sites`
    - `/jquery`
    - `/motion-ui`
    - `/what-input`
- `/craft/` - where you put your [craftcms](http://craftcms.com/) installation (step 2 above)   
- `/node_modules/` - where node gets installed when running `$npm install`
- `/site/` - where you point apache
    - `/lib` - compiled when you run `foundation watch` or `foundation build`
        - `/css`
            - `/display.css` - the single css generated by gulpfile.babel.js (line 63)
        - `/gr` - fonts moved from /src/ by gulpfile.babel.js (line 42)            
        - `/gr` - your compressed graphics generated by gulpfile.babel.js (line 90)
        - `/js`
            - `/app.js` - the single js generated by gulpfile.babel.js (line 78)            
        - `/svg` - svg moved from /src/ by gulpfile.babel.js (line 42)                 
- `/src`
    - `/fonts` - source fonts here
    - `/gr` - put your source graphics here and auto-compress them on build
    - `/js`
        - `/app.js` - adds $(document).foundation(); at the end of your compiled js
    - `/scss` - source foundation 6 sass files
        - `/components` - your custom sass/css goes inside here
        - `/mixins` - your custom mixins go inside here
        - `/_settings.scss` - a copy of the default Foundation config
        - `/app.scss` - included foundation dependencies
    - `/svg` - source svg files
- `/bower.json` - module configuration for your `/bower_components/`
- `/config.yml` - central config file to manage your paths and foundation components
- `/gulpfile.babel.js` - where it all comes together - update according to your needs
- `/package.json` - module configuration for your `/node_modules/`
- `/README.md` - this file =)
