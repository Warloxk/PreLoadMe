# PreLoadMe, a lightweight jQuery website preloader
PreLoadMe is a lightweight preloader for any webcontent. Powered by jQuery and CSS it is fully responsive and will run on all modern desktop- and mobile browsers with no additionals plugins. PreLoadMe displays a loading animation until the browser fetched the whole webcontent and will fade out the moment the page has been completely chached. Because the simplicity of PreLoadMe, it can be easily customized and adapted to your needs.

PreLoadMe displays a loading animation until the browser fetched the whole web content and will fade out the moment the page has been completely cached. Because the simplicity of PreLoadMe, it can be easily customized and adapted to your needs.

You can see a live preview here: <a href='https://codepen.io/vonvlaho/pen/XgYOyo' title='PreLoadMe Live Preview' target='_blank'>PreLoadMe Live Preview</a>

## Implementation
PreLoadMe is jQuery driven. You will need to implement an up to date jQuery version and the corresponding JavaScript for executing the preloader.

    <!-- jQuery Plugin -->
    <script type="text/javascript" src="https://code.jquery.com/jquery-1.12.3.min.js"></script>

    <!-- Preloader -->
    <script type="text/javascript">
        //<![CDATA[
            $(window).on('load', function() { // makes sure the whole site is loaded
                $('#status').fadeOut(); // will first fade out the loading animation
                $('#preloader').delay(350).fadeOut('slow'); // will fade out the white DIV that covers the website.
                $('body').delay(350).css({'overflow':'visible'});
              })
        //]]>
    </script>

The CSS-Markup will help you style the preloader. Make sure to include it on your website.

```
  #preloader {
      display: block;
      position: fixed;
      top:0;
      left:0;
      right:0;
      bottom:0;
  		background: #C9D6FF;  /* fallback for old browsers */
  		background: -webkit-linear-gradient(to bottom, #E2E2E2, #C9D6FF);  /* Chrome 10-25, Safari 5.1-6 */
  		background: linear-gradient(to bottom, #E2E2E2, #C9D6FF); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  		z-index:99; /* makes sure it stays on top */
  }

  #status {
      display: block;
      width:40px;
      height:40px;
      position:absolute;
      left:50%; /* centers the loading animation horizontally on the screen */
      top:50%; /* centers the loading animation vertically on the screen */
      border-radius: 50%;
      border: 0.25rem solid rgba(255, 255, 255, 0.2);
      border-top-color: white;
      -webkit-animation: spin 1s infinite linear;
      animation: spin 1s infinite linear;
      margin:-20px 0 0 -20px; /* is width and height divided by two */
  }
```

Finally place the following HTML Code directly after the `<body>` tag.

	<div id="preloader">
		<div id="status">&nbsp;</div>
	</div>

The outer DIV `preloader` will be called from the CSS file and will cover the entire website with a white DIV. The inner DIV `status` will show the loading animation. Also you should not forget to give your document a proper doctype. Otherwise the preloader might not work.

## Credits
Please support humans.txt (http://humanstxt.org/). It's an initiative for knowing the people behind a website. It's a TXT file that contains information about the different people who have contributed to building the website.

	PreLoadMe: https://github.com/niklausgerber/PreLoadMe
	Niklaus Gerber
	Twitter: @niklausgerber
	URL: https://www.niklausgerber.com
	Location: Zürich, Switzerland

### Download, Fork, Commit.
If you think you can make this better, please Download, Fork, & Commit. I'd love to see your ideas.

## Donation
I love to create and I won't ask for repayment. If you appreciate my work and would like to support me I am sure you will earn some extra Karma points. <a href="https://www.paypal.me/NiklausGerber" target="_blank" title="Please donate">Please donate</a>.
