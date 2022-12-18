<!--
 Copyright (c) 2022 [.shovon]
 
 This software is released under the MIT License.
 https://opensource.org/licenses/MIT
-->

# Gdtot CLI Tools

This is a python script that can generate google drive download link from gdtot urls, download gdtot to specific drive folder and generate worker url for that file if available.

### Requirements:

- Python3

- Gdtot account and the crypt

    - How to get crypt: [Link](#gdtot-cookies)

### Optional Requirements:

- Google drive token

    - Getting Google OAuth API credential file and token.pickle: [Link](https://github.com/anasty17/mirror-leech-telegram-bot/tree/master#3-getting-google-oauth-api-credential-file-and-tokenpickle)

- Target google drive folder id

- Worker url


### How to setup and use:

The config for this script is stored in `config.ini`. Make a copy of `config_sample.ini` and rename it to `config.ini`. For a basic setup just put the crypt string in the gdtot section of the config file and save. Install python requirements by running `pip install -r requirements.txt`. Run the script by `python main.py` or `python3 main.py`, paste the gdtot url and the link for drive will be shown on the terminal.

For downloading in a target folder, generate a `token.pickle` and paste it in script's folder, put the target download folder id in `config.ini` drive section and run the script by `python main.py` or `python3 main.py`. Rest is same as above.

To generate a worker direct download url, paste the full worker path in the `config.ini` worker section.



### Gdtot Cookies
To Clone or Leech gdtot link follow these steps:
1. Login/Register to gdtot.
2. Copy this script and paste it in browser address bar.
   - **Note**: After pasting it check at the beginning of the script in broswer address bar if `javascript:` exists or not, if not so write it as shown below.
   ```
   javascript:(function () {
     const input = document.createElement('input');
     input.value = JSON.stringify({url : window.location.href, cookie : document.cookie});
     document.body.appendChild(input);
     input.focus();
     input.select();
     var result = document.execCommand('copy');
     document.body.removeChild(input);
     if(result)
       alert('Cookie copied to clipboard');
     else
       prompt('Failed to copy cookie. Manually copy below cookie\n\n', input.value);
   })();
   ```
   - After pressing enter your browser will prompt a alert.
3. Now you'll get this type of data in your clipboard
   ```
   {"url":"https://new.gdtot.org/","cookie":"PHPSESSID=k2xxxxxxxxxxxxxxxxxxxxj63o; crypt=NGxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxWdSVT0%3D"}

   ```
4. From this you have to paste value of crypt in config.ini file.
