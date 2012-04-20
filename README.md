MvcBlanket
==========

MVC compliant captcha generation library

Features
--------

The following features are supported:

* Fully customizable rendering engine
* Integrates into ASP.NET MVC workflow by providing the special CaptchaResult action result and Captcha controller's extension method.
* Provides support of entered captcha code validation using declarative approach by ValidateCaptcha validation attribute

Using
--------

###Generation of the captcha image

Write following code to the controller's action method:

		[ActionName("Captcha")]
		public ActionResult ShowCaptcha()
		{
			return this.Captcha();
		}

		
###Validating captcha code

Write following code to the model you use:

		[Captcha]
		public string Captcha {get;set;}
		
The validation then runs as usual and you can check is the model valid by accessing `ModelState.IsValid` property in your action method.


###Customization

You can customize rendering by setting a number of properies of CaptchaImage instance.
Also you can place a number of captches onto the single page by providing unique captcha identifiers to `Captcha` method and `ValidateCaptcha` attribute.