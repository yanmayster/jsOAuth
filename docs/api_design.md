#API Design#

This document is intended to put forward ideas for the way that jsOAuth 2 will be designed, focussing on API and backwards compatablility with previous versions of jsOAuth.

##Constructor##
There are several options for constructing the OAuth object.

###Version flag###
    var oauth = OAuth({
        consumerKey: 'CONSUMER-KEY',
        consumerSecret: 'CONSUMER-SECRET'
	}, OAUTH.V2);

This method has the advantage that, if the API is the same, nothing needs to be done by existing developers when they upgrade if the default is v1, however as OAuth2 becomes more wide-spread defaulting to v1 will be a headache for developers expecting the library to see the latest OAuth version.

###Alternate constructors###
    var oauth = OAuth.V2({
        consumerKey: 'CONSUMER-KEY',
        consumerSecret: 'CONSUMER-SECRET'
    });

This method is more verbose, and shorter. However it requires existing jsOAuth developers to upgrade thier code or dual-running both versions of jsOAuth.