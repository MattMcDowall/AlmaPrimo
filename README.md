# AlmaPrimo
Scripts to automate things in Ex Libris Alma/Primo, typically via the API

## **Let me say up front . . .**
. . . that I’m relatively new and largely self-taught when it comes to both Git and Python. So I probably do things in not-the-most-efficient ways pretty regularly. If you have any advice for better methods to accomplish anything here, by all means please let me know.

## **Requirements**
I'll try to list specific requirements in the README for each subfolder/script. Overall, of course, you're going to need API access to Alma, Primo, and Analytics (depending on which scripts you are interested in). Please see the **note on authentication** below for more on this.

### **Dependencies**
Virtually all of these scripts need the `requests` package, and most also need `json` and/or `xmltodict`. (`Requests` is typically used to access the API, and the other two are used for parsing or packaging API data.)

## **A note on authentication**
Getting API access/keys set up is beyond the scope of this introduction, but I do want to mention how I’ve gone about implementing the authentication.

In order to keep the API credentials private, my approach is to tackle the authentication via an external file, and then call that file from these scripts.

What I’ve done is to create a script called `Credentials.py` which resides in this folder on my computer. To keep it private, I’ve added a line in the `.gitignore` file which filters it out of any pushes to the public repository. So you’ll need to create your own Credentials.py file, in this same directory.

Credentials.py is a very simple file, looking like this:

    prod_api = 'a1aa11111111111111aa1a11aaaa11a111aa'
    sand_api = 'z9zzz99zzz99z9z999zzzzz999zz9999z999'

As you can see in the scripts themselves, we import that file thus:

    import Credentials

and get the API key for use thus:

    apikey = Credentials.prod_api

I hope that makes sense.
