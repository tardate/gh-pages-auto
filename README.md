# gh_pages_test

...just playing with GH pages.

* original pages generated with the [automatic page generator](https://help.github.com/articles/creating-pages-with-the-automatic-generator/)
* produces a static HTML site on the [gh-pages branch](https://github.com/tardate/gh_pages_test/tree/gh-pages)
* pages automatically published at [tardate.github.io/gh_pages_test](http://tardate.github.io/gh_pages_test/)
* more info, see [github pages help](https://help.github.com/categories/github-pages-basics/)

## Adding custom domain
So I'm going to test setting up a custom subdomain. Seems like I just need to do two things:

* [add a CNAME in DNS](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider/)
* and [add a CNAME file to the pages repo](https://help.github.com/articles/adding-a-cname-file-to-your-repository/)

More info, see https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/

So now the GitHub pages from this repo are available at both:
* [tardate.github.io/gh_pages_test](https://github.com/tardate/gh_pages_test), and
* [gh-pages-test.tardate.com](http://gh-pages-test.tardate.com)

Note that although gh-pages-test.tardate.com may also be accessed with HTTPS, it will give a security warning since I don't have a certificate in place.

```
$ dig gh-pages-test.tardate.com

; <<>> DiG 9.8.3-P1 <<>> gh-pages-test.tardate.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 15073
;; flags: qr rd ra; QUERY: 1, ANSWER: 3, AUTHORITY: 0, ADDITIONAL: 0

;; QUESTION SECTION:
;gh-pages-test.tardate.com. IN  A

;; ANSWER SECTION:
gh-pages-test.tardate.com. 7200 IN  CNAME tardate.github.io.
tardate.github.io.  3600  IN  CNAME github.map.fastly.net.
github.map.fastly.net.  4 IN  A 185.31.18.133

;; Query time: 134 msec
;; SERVER: 10.188.0.1#53(10.188.0.1)
;; WHEN: Tue Nov 10 12:02:13 2015
;; MSG SIZE  rcvd: 125
```