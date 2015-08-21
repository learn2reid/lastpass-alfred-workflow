# Simple Lastpass Workflow for Alfred

Simple yet powerful integration with the Lastpass CLI so you can now get your passwords out of your Lastpass vault and straight into the clipboard from within Alfred.

## Installation

1. Ensure you have Alfred installed with the Alfred Powerpack License
2. Install Capture::Tiny
	1. Open up a Terminal Window
	2. run the command 'sudo cpan install Capture::Tiny'
	3. Accept the default options and ensure Capture::Tiny installs successfully
3. Install Homebrew (if you do not have it already installed)
	1. You should be able to just run the command in a terminal window (as your own user account NOT with sudo)
	2. ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	3. Alternatively visit http://brew.sh/ for further instructions.
4. Install LastPass command line interface
	1. In a terminal window run
		brew install lastpass-cli --with-pinentry --with-doc
5. Download the .alfredworkflow file
6. Open the .alfredworkflow file to import into Alfred
7. Open up the workflow within Alfred, double click the top "Terminal Command" box in the workflow and change "yourloginemail@yourdomain.com" to your LastPass username.

## Usage

* lpsetemail yourname@example.com - must be run when you first install/upgrade to version 1.2 or higher
* lpsettimeout NUMSEC - Set number of seconds until your login times out (where NUMSEC is an integer such as 28800, if you use 0 that will keep you logged in until your computer restarts)
* lplogin - Log in to LastPass
* lplogout - Log out of LastPass
* lp <query> Search Lastpass vault for item containing <query>, press return to copy to clipboard.
* Shift modifier can be used on lp <query> to copy the username.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

* Version 1.2
	1. Bug - Removed deprecated framework code
	2. Bug - Merged [pull request #4](https://github.com/stuartcryan/lastpass-alfred-workflow/pull/4) from [jsquyres](https://github.com/jsquyres) "we-love-macports-too" to support macports installs of the lastpass-CLI
	3. Bug - Further improved on [jsquyres](https://github.com/jsquyres) code to support some additional install locations.
	4. Bug - Fixed bash script reliability, after two login attempts the script was often failing.
	3. Improvement - Improved sync behaviour to better support extremely large vaults.
	4. Improvement - Added new 'lpsync' command to force a sync on demand.
	5. Improvement - Changed behaviour to store login email in your Apple Keychain (set with 'lpsetemail yourname@example.com').
	6. Improvement - Added the ability to set the logout timeout and store in the keychain (set with 'lpsettimeout NUMSEC' where NUMSEC is an integer such as 28800, if you use 0 that will keep you logged in until your computer restarts).
	7. Improvement - Added hotkeys to the main functions.
* Version 1.1
	1. Removed code that worked around an old buggy version of pinentry
	2. Fixed incorrect handling of no search results found (previously reported CLI tools were not installed)
* Version 1.0 - Initial Release

## Credits

Created by [Stuart Ryan](http://stuartryan.com). If you would like to get into contact you can do so via:
* [@StuartCRyan on Twitter](http://twitter.com/stuartcryan)
* [Stuart Ryan on LinkedIn](https://au.linkedin.com/in/stuartcryan)
* [Technical Notebook Blog](http://technicalnotebook.com)

## License

Released under the GNU GENERAL PUBLIC LICENSE Version 2, June 1991

## Notes
NOTE: This Alfred Workflow is not affiliated in any way with LastPass. The LastPass trademark and logo are owned by LastPass.com. The LastPass logo and product name have been used with permission of the LastPass team.

My thanks go out to LastPass for their awesome product and the new CLI!