# Design Experiments Plugin

⚠️ **This plugin is not intended for use in production.**

A simple plugin to prototype design ideas in WP-Admin. This repository is intended to be a quick way for designers to try out ideas and minor CSS updates. Quick, messy code is encouraged to get ideas across.

The `master` branch is just an empty boilerplate: it sets up a plugin that enqueues a new, empty admin stylesheet to get you started. 

## To try an experiment: 

1. Download a zip of the repository.
2. Upload to your test site as a plugin.
3. Activate the "Design Experiments" Plugin.
4. Visit `Settings > General > Design Experiments` to activate an experiment.

## To build your own quick experiment:

1. First, [fork the repository](https://help.github.com/en/articles/fork-a-repo). 
2. [Clone](https://help.github.com/en/articles/cloning-a-repository) your fork. If possible, place your local copy in the Plugins folder of your local dev site. Then you'll be able to activate the plugin directly from your WP Admin dashboard (If this isn't possible, follow the instructions above to install the plugin manually after you've edited it).
3. For simple CSS updates, you can either edit style.css directly, or edit `sass/style.scss` and compile using the method described below. 

## To submit an experiment for inclusion in the plugin: 

1. [Fork the repository](https://help.github.com/en/articles/fork-a-repo). 
2. [Clone](https://help.github.com/en/articles/cloning-a-repository) your fork. If possible, place your local copy in the Plugins folder of your local dev site. Then you'll be able to activate the plugin directly from your WP Admin dashboard (If this isn't possible, follow the instructions above to install the plugin manually after you've edited it).
3. If you're using Sass, create new SASS stylesheet in the `sass` directory, and run `npm run build` to compile it. Otherwise, just add a new CSS file to the `css` directory. 
4. Add your experiment to the `$design_experiments` array in `index.php`. This will properly enqueue your new stylesheet and ensure that your experiment shows up on the Plugin's settings page. This takes just a single line of code. An example is commented out in the file:
		- `stylesheet`: The filename of your experiment's stylesheet, minus the extension. No spaces please.
		- `Experiment title`: A title for your experiment.
		- `url/to/experiment`: A URL to an explanation of your experiment. Ideally a GitHub PR or Trac ticket. (Optional)
5. Once you're ready to share your experiment, [open a PR](https://help.github.com/en/articles/creating-a-pull-request) and share it here. 

### To compile CSS:

1. Run `npm install` to install dependencies (You'll only have to do this once).
2. Run `npm run build` to compile the CSS once, or `npm run watch` to have it compile changes whenever you modify a sass file. 

## Questions or Improvements?

If you'd like to propose improvements to this plugin, feel free to open an [issue](https://github.com/WordPress/design-experiments/issues) or PR. Also feel free to ask in the [#design channel on WordPress.org Slack](http://wordpress.slack.com/messages/design/). 