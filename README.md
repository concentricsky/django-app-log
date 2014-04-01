![Concentric Sky](https://concentricsky.com/media/uploads/images/csky_logo.jpg)


# Django App Log

Django App Log is an open-source Django library developed by [Concentric Sky](http://concentricsky.com/). It provides a model to log requests or other information to the database.


## Installation and Usage

Install the library using pip:

    pip install git+https://github.com/concentricsky/django-app-log.git


Add 'app_log' to INSTALLED_APPS in settings.py:

    INSTALLED_APPS = (
        ...
        'app_log',
        ...


Log requests in your views by calling the `log_request()` function:

    from app_log import log_request

    class MyFormView(generic.FormView):

        def form_valid(self, form, *args, **kwargs):
            obj = form.save()
            app_log.log_request(self.request, obj=obj)
            return self.render_to_response(self.get_context_data(form=form))


## License

This project is licensed under the Apache License, Version 2.0. Details can be found in the LICENSE.md file.


## About Concentric Sky

_For nearly a decade, Concentric Sky has been building technology solutions that impact people everywhere. We work in the mobile, enterprise and web application spaces. Our team, based in Eugene Oregon, loves to solve complex problems. Concentric Sky believes in contributing back to our community and one of the ways we do that is by open sourcing our code on GitHub. Contact Concentric Sky at hello@concentricsky.com._
