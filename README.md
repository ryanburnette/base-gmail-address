# effective-email-address

Dots and anything after a + are ignored in Gmail addresses.
https://gmail.googleblog.com/2008/03/2-hidden-ways-to-get-more-from-your.html

The most useful case is figuring out that multiple differetiated addresses are actually the same
effective address. For example, `foo.bar@gmail.com` and `f.o.o.b.a.r@gmail.com` are the same effective address
of `foobar@gmail.com`.

There are some other services that ignore dots.
https://stackoverflow.com/a/36125463/2535178
http://www.slate.com/blogs/future_tense/2013/08/01/dots_in_gmail_addresses_what_happens_if_you_leave_out_the_period.html

Maybe a library that returns the base email address as well as the one provided would be helpful.

## Name

This needs a better name.

## Usage

```javascript
const Email = require('effective-email-address')

// Gmail
let x = 'foo.bar+test@gmail.com'
Email.parse(x)
// { provider: 'gmail', provided: 'foo.bar+test@gmail.com', effective: 'foobar@gmail.com', extra: 'test' }

// iCloud
let y = 'foo.bar@icloud.com'
Email.parse(y)
// { provider: 'icloud', provided: 'foo.bar@icloud.com', effective: 'foo.bar@icloud.com }

// Facebook
let z = 'foo.bar@facebook.com'
Email.parse(z)
// { provider: 'facebook', provided: 'foo.bar@facebook.com', effective: 'foobar@facebook.com }
```

## Contribute

This is a good project to collaborate on because there are many services that handle things differently and it would be nice
to have all the logic in one place.

## Not Yet

This isn't a library yet. Just an idea.
