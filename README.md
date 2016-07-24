# &lt;wdpr-wc-polymer-textbox&gt;

> Extending Native Input Text-box using Polymer v1.0



## Installation

1. Clone and Install the package:

```
	 git clone https://github.com/kumaran-is/wc-polymer-textbox.git

   	 cd wdpr-wc-polymer-textbox
	
```

Or [download as ZIP](https://github.com/disney/wdpr-wc-polymer-textbox/archive/master.zip).


1. Install [bower](http://bower.io/) & [polyserve](https://npmjs.com/polyserve):

    ```
    npm install -g bower polyserve
    ```

2. Install local dependencies:

    ```
    bower install
    ```

3. Start development server and open [http://localhost:8080/components/wdpr-wc-polymer-textbox/](http://localhost:8080/components/wdpr-wc-polymer-textbox/).

    ```
    $ polyserve
    ```

## Known Issues

### Scoped styling is not working for Chrome v51.0 if full native DOM is enabled in polymer 

1. By default **Shady DOM** is enabled in Polymer. Styling of Host element using :host for custom input text box element built by extending native element works with **Shady DOM**  in chrome 5.0 , IE11 and Firefox 47.0.1.  But as soon as full native shadow DOM is enabled refer below script, styling of host element is not working for chrome but works for  IE11 and Firefox 47.0.1. This looks like issue with chrome browser. It throws below error for chrome.

		Uncaught InvalidStateError: Failed to execute 'createShadowRoot' on 'Element': 
		Shadow root cannot be created on a host which already hosts an user-agent shadow tree.

	 **Enable native shadow DOM in polymer** 
	  Add this Javascript in your index.html file before include component HTML file.
	 
	 ```JS
	 <script>
	     window.Polymer = {
	       dom: 'shadow',
	       lazyRegister: true
	     };
	   </script>
	 ```


2. Since shady DOM is used instead of shadow DOM while using polymer , styling of custom elements are encapsulated.  For more detail on polymer shady DOM refer [here](https://www.polymer-project.org/1.0/blog/shadydom)