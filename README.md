# disqus

Module Disqus for AJAX applications - includes or reloads the disqus script and updates the comment count on item lists

## Usage

Install the package

    npm -i install disqus_ap

Create the object and setup the initial parameters

    var DisqusAP = require("disqus_ap")
    
    var disqus = new DisqusAP()

    disqus.setup('disqus_shortname', 'disqusPublicKey', 'disqusBaseUrl')


Being

    // your disqus shortname
    disqus_shortname = '';

    // your disqus public key
    disqusPublicKey = "";

    // any prefix you want to prepend to disqus_identifier or disqus_url
    // 
    // IMPORTANT: in AJAX applications both disqus identifier and disqus url are needed
    // and because DISQUS only accepts the full hashbang #! 
    // you can use this variable to include it if needed
    disqusBaseUrl = '';

Then you can call _init_ for the inclusion of the comment box

    disqus.init('newIdentifier', 'newUrl', 'newTitle', 'newLanguage')

Being

    // the disqus identifier
	disqus_identifier = disqusBaseUrl + newIdentifier;

	// the page title
	disqus_title = newTitle;

	// the disqus url
	// in AJAX applications both disqus identifier and disqus url are needed
	disqus_url = disqusBaseUrl + newUrl;

Or call _commentCount_ to update an element with the number of comments

    disqus.commentCount('_element', 'pluralTag', 'singularTag')

Being
    
    // The element (e.g. a jquery selector) that contains a "data-disqus-url" attribute
    _element
    
    // A plural suffix for the number (when there's only one comment)
    pluralTag

    // A singular suffix for the number (when there more than one comment)
    singularTag