# meteor-client-side

Use Meteor's client side DDP protocol and Minimongo in a non Meteor project.

### Installation

`bower install meteor-client-side` 


### Usage

1. Set DDP connection url:
    
    * Load the script `<script src="meteor-runtime-config.js"></script>` (Sets the url to `http://localhost:3000`).
    
    Or 

    * Set `__meteor_runtime_config__.DDP_DEFAULT_CONNECTION_URL` global variable with the desired url.

3. Load the meteor-client-side code:
    
    * Minified: `<script src="meteor-client-side.min.js"></script>`
    
    Or

    * The packages one-by-one:

        ```
        <script src="packages/underscore.js"></script>
        <script src="packages/meteor.js"></script>
        <script src="packages/base64.js"></script>
        <script src="packages/json.js"></script>
        <script src="packages/ejson.js"></script>
        <script src="packages/check.js"></script>
        <script src="packages/random.js"></script>
        <script src="packages/tracker.js"></script>
        <script src="packages/retry.js"></script>
        <script src="packages/id-map.js"></script>
        <script src="packages/ordered-dict.js"></script>
        <script src="packages/geojson-utils.js"></script>
        <script src="packages/minimongo.js"></script>
        <script src="packages/logging.js"></script>
        <script src="packages/ddp.js"></script>
        <script src="packages/mongo.js"></script>
        <script src="packages/global-imports.js"></script>
        ```


### What I've done

I wanted to be able to use meteor's DDP protocol and Minimongo without the process of change my current project infrastructure and architecture.

In order to make it possible I looked at Meteor's code and try figure out how to set the DDP connection url outside of a Meteor project.
I found that `__meteor_runtime_config__.DDP_DEFAULT_CONNECTION_URL` runtime variable need to be set and then it left me with the need to extract meteor code to external use. It was realy simple :)

I run `meteor build --directory` and got the minified version `meteor-client-side.min.js`

In addition, I wanted to use Meteor Accounts packages so I extracted it too [accounts-password-client-side][accounts-password-client-side]

[accounts-password-client-side]: https://github.com/idanwe/accounts-password-client-side

