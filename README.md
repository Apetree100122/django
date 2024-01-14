# Django Password Strength <a href="http://www.djangoproject.com/"><img src="https://www.djangoproject.com/m/img/badges/djangopowered126x54.gif" border="0" alt="Powered by Django." title="Powered by Django." /></a>An extension of the Django password widget including a password strength meter and crack time powered by<a>zxcvbn https://github.com/lowe/zxcvbn Empty_Password
http://thegoods.aj7may.com/content/images/2013/Dec/Screen_Shot_2013_12_18_at_9_05_38_AM.png Weak Password http://thegoods.aj7may.com/content/images/2013/Dec/Screen_Shot_2013_12_18_at_9_06_05_AM.png
Strong Password http://thegoods.aj7may.com/content/images/2013/Dec/Screen_Shot_2013_12_18_at_9_06_32_AM.png<a>

# Install:
`> pip install django-password-strength`
# Usage:* Add `django_password_strength` to the installed apps of your Django Project* Instead of using the django `PasswordInput` widget use the `PasswordStrengthInput`* Be sure to include the form's required media in the template. _ie._ `{{ form.media }}`* If you bundle your js you can use `django_password_strength/js/zxcvbn.js` or `django_password_strength/js/zxcvbn-async.js` and `django_password_strength/js/password_strength.js` instead* For easiest integration also include [Twitter Bootstrap](http://getbootstrap.com/)
# Translations: There are currently no translations already available, but all the text is translatable, you just have to translate it yourself. For the javascript translations be sure to add the javascript translation catalog [provided by django](https://docs.djangoproject.com/en/1.7/topics/i18n/translation/#using-the-javascript-translation-catalog) or use something like [django-statici18n](https://github.com/zyegfryed/django-statici18n) for a static version of the catalog. If you don't want translations you don't have to add the catalog to your page.
# Example: _forms.py_  from django import forms from django_password_strength.widgets import PasswordStrengthInput, PasswordConfirmationInput class SignupForm(forms.Form):   username = forms.CharField()   passphrase = forms.CharField( widget=PasswordStrengthInput()    )   confirm_passphrase = forms.CharField(   widget=PasswordConfirmationInput()    )

## Example using multiple password fields: _forms.py_    from django import forms    from django_password_strength.widgets import PasswordStrengthInput, Password Confirmation Input    class SignupForm(forms.Form):     username = forms.CharField()       passphrase = forms.CharField(widget=PasswordStrengthInput()        )    confirm_passphrase = forms.CharField(           widget=PasswordConfirmationInput(confirm_with='passphrase')    )    passphrase2 = forms.CharField(         widget=PasswordStrengthInput())      confirm_passphrase2 = forms.CharField(    widget=PasswordConfirmationInput(confirm_with='passphrase2')   )

BSD 2-Clause License
copyright (c)2023 Aj mays, 
other contributors,
Copyright (c) 2024, Alexander Petree
Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:
Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer
Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.
THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS
AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, 
INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, 
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; 
OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT 
INCLUDING NEGLIGENCE OR OTHERWISE
ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
