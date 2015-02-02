GitHub Changelog Generator
==================

[![Gem Version](https://badge.fury.io/rb/github_changelog_generator.svg)](http://badge.fury.io/rb/github_changelog_generator)
[![Build Status](https://travis-ci.org/skywinder/Github-Changelog-Generator.svg?branch=master)](https://travis-ci.org/skywinder/Github-Changelog-Generator)

Changelog generation has never been so easy.

This script automatically generate change-log from your tags and merged pull-requests.

## Installation:
You're almost done!

	[sudo] gem install github_changelog_generator

## Example:

># Changelog
> 
> ## [1.3.10](https://github.com/skywinder/ActionSheetPicker-3.0/tree/1.3.10)
> #### 09/01/15
> - *Merged pull-request:* add header file to public [\#115](https://github.com/skywinder/ActionSheetPicker-3.0/pull/115)
> ([skywinder](https://github.com/skywinder))
> 
> - *Merged pull-request:* Fix bad interaction with Git submodules.
> [\#112](https://github.com/skywinder/ActionSheetPicker-3.0/pull/112)
> ([JimDabell](https://github.com/JimDabell))
> 
> - *Implemented enhancement:* Should have minimum/maximum date property exposed
> [\#97](https://github.com/skywinder/ActionSheetPicker-3.0/issues/97)
> 
> ## [1.3.9](https://github.com/skywinder/ActionSheetPicker-3.0/tree/1.3.9)
> #### 11/12/14
> - *Closed issue:* Bad interaction with submodules [\#111](https://github.com/skywinder/ActionSheetPicker-3.0/issues/111)
> 
> - *Closed issue:* No "cancel" button [\#122](https://github.com/skywinder/ActionSheetPicker-3.0/issues/122)


##Features

- **Fully automate changelog generation** - all you need to do - is close issue or merge pull-request by **Github issue tracker**
- Automatically split issues by type:
    - 	**Issues** (closed issues w/o any labels)
    - **Merged pull-requests** (all merged pull-requests)
    - **Bug-fixes** (by label `bug` in issue)
    - **Enhancements** (by label `enhancement` in issue)

- Excluding "questions" from changelog (issues marked as `question` labels)
- Ability to manually specify in which version issue was fixed (in case, when closed date is not match) by setting `milestone` of issue the same name as tag of  required version
- Ability to exclude some issues from changelog (by labels)

## Usage:
**It's really simple**: 

- If your **git remote** `origin` refer to your GitHub repo, then just go to your project folder and run:

		github_changelog_generator

-  or from anywhere:

		github_changelog_generator -u github_username -p github_project
     
As output you will get `CHANGELOG.md` file with pretty *Markdown-formatted* changelog.

### Params:
Type `github_changelog_generator --help` for detailed usage.

    Usage: changelog_generator [options]
        -u, --user [USER]                Username of the owner of target GitHub repo
        -p, --project [PROJECT]          Name of project on GitHub
        -t, --token [TOKEN]              To make more than 50 requests this script required your OAuth token for GitHub. You can generate here: https://github.com/settings/tokens/new
        -h, --help                       Displays Help
            --[no-]verbose               Run verbosely. Default is true
            --[no-]issues                Include closed issues to changelog. Default is true
            --[no-]issues-without-labels Include closed issues without any labels to changelog. Default is true
            --[no-]pull-requests         Include pull-requests to changelog. Default is true
        -l, --last-changes               Generate log between last 2 tags only
            --[no-]author                Add author of pull-request in the end. Default is true
        -f, --date-format [FORMAT]       Date format. Default is %d/%m/%y
        -o, --output [NAME]              Output file. Default is CHANGELOG.md
            --labels  x,y,z              List of labels. Issues with that labels will be included to changelog. Default is 'bug,enhancement'
        -v, --version                    Print version number


### GitHub token

Since GitHub allow to make only 50 requests without authentication it's recommended to run this script with token

**You can easily [generate it here](https://github.com/settings/applications)**.

And:

- Run with key `-t [your-16-digit-token]` 
- Or set environment variable `CHANGELOG_GITHUB_TOKEN` and specify there your token. 
 		
	i.e. add to your `~/.bash_profile` or `~/.zshrc` or any other place to load ENV variables string :

        export CHANGELOG_GITHUB_TOKEN="your-40-digit-github-token"

So, if you got error like this:
>! /Library/Ruby/Gems/2.0.0/gems/github_api-0.12.2/lib/github_api/response/raise_error.rb:14:in `on_complete'

It's time to create this token or wait for 1 hour before GitHub reset the counter for your IP.

## Examples:

- Look at **[CHANGELOG.md](https://github.com/skywinder/Github-Changelog-Generator/blob/master/CHANGELOG.md)** for **this** project
- [ActionSheetPicker-3.0/CHANGELOG.md](https://github.com/skywinder/ActionSheetPicker-3.0/blob/master/CHANGELOG.md)  was generated by command:

		github_changelog_generator -u skywinder -p ActionSheetPicker-3.0


## Projects using this library
[Wikipage with list of projects](https://github.com/skywinder/Github-Changelog-Generator/wiki/Projects-using-Github-Changelog-Generator) 

*If you are using `github_changelog_generator` for generation chamgelog in your project or know of project that uses it, please add it to [this] (https://github.com/skywinder/Github-Changelog-Generator/wiki/Projects-using-Github-Changelog-Generator) list.*

## Am I missed some essential feature?

**Nothing is impossible!** Open an [issue](https://github.com/skywinder/Github-Changelog-Generator/issues/new) and let's make generator better together!

*Bug reports, feature requests, patches, well-wishes are always welcome!*

## Contributing

1. Create an issue to discuss about your idea
2. [Fork it] (https://github.com/skywinder/Github-Changelog-Generator/fork)
3. Create your feature branch (`git checkout -b my-new-feature`)
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Push to the branch (`git push origin my-new-feature`)
6. Create a new Pull Request

## License

Github Changelog Generator is released under the [MIT License](http://www.opensource.org/licenses/MIT).


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/skywinder/github-changelog-generator/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

