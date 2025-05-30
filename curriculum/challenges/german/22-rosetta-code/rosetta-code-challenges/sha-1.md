---
id: 5eb3e4b5f629b9a07429a5d2
title: SHA-1
challengeType: 1
forumTopicId: 385326
dashedName: sha-1
---

# --description--

**SHA-1** oder **SHA1** ist eine Einweg-Hashfunktion; die eine 160-Bit Message-Digest berechnet.

SHA-1 taucht häufig in Sicherheitsprotokollen auf; viele HTTPS-Websites verwenden zum Beispiel RSA mit SHA-1, um ihre Verbindungen zu sichern.

BitTorrent verwendet SHA-1, um Downloads zu verifizieren.

Git und Mercurial verwenden SHA-1 Digests, um Commits zu identifizieren.

Eine Norm der US-Regierung, <a href="https://rosettacode.org/wiki/SHA-1/FIPS-180-1" target="_blank" rel="noopener noreferrer nofollow">FIPS 180-1</a>, definiert SHA-1.

# --instructions--

Schreibe eine Funktion, die den SHA-1 Message Digest für eine gegebene Zeichenkette zurückgibt.

# --hints--

`SHA1` sollte eine Funktion sein.

```js
assert(typeof SHA1 === 'function');
```

`SHA1("abc")` sollte einen String zurückgeben.

```js
assert(typeof SHA1('abc') === 'string');
```

`SHA1("abc")` sollte `"a9993e364706816aba3e25717850c26c9cd0d89d"` zurückgeben.

```js
assert.equal(SHA1('abc'), 'a9993e364706816aba3e25717850c26c9cd0d89d');
```

`SHA1("Rosetta Code")` sollte `"48c98f7e5a6e736d790ab740dfc3f51a61abe2b5"` zurückgeben.

```js
assert.equal(SHA1('Rosetta Code'), '48c98f7e5a6e736d790ab740dfc3f51a61abe2b5');
```

`SHA1("Hello world")` sollte `"7b502c3a1f48c8609ae212cdfb639dee39673f5e"` zurückgeben.

```js
assert.equal(SHA1('Hello world'), '7b502c3a1f48c8609ae212cdfb639dee39673f5e');
```

`SHA1("Programming")` sollte `"d1a946bf8b2f2a7292c250063ee28989d742cd4b"` zurückgeben.

```js
assert.equal(SHA1('Programming'), 'd1a946bf8b2f2a7292c250063ee28989d742cd4b');
```

`SHA1("is Awesome")` sollte `"6537205da59c72b57ed3881843c2d24103d683a3"` zurückgeben.

```js
assert.equal(SHA1('is Awesome'), '6537205da59c72b57ed3881843c2d24103d683a3');
```

# --seed--

## --seed-contents--

```js
function SHA1(input) {

}
```

# --solutions--

```js
function SHA1(input) {
  var hexcase = 0;
  var b64pad = '';
  var chrsz = 8;

  function hex_sha1(s) {
    return binb2hex(core_sha1(str2binb(s), s.length * chrsz));
  }

  function core_sha1(x, len) {
    x[len >> 5] |= 0x80 << (24 - (len % 32));
    x[(((len + 64) >> 9) << 4) + 15] = len;

    var w = Array(80);
    var a = 1732584193;
    var b = -271733879;
    var c = -1732584194;
    var d = 271733878;
    var e = -1009589776;

    for (var i = 0; i < x.length; i += 16) {
      var olda = a;
      var oldb = b;
      var oldc = c;
      var oldd = d;
      var olde = e;

      for (var j = 0; j < 80; j++) {
        if (j < 16) w[j] = x[i + j];
        else w[j] = rol(w[j - 3] ^ w[j - 8] ^ w[j - 14] ^ w[j - 16], 1);
        var t = safe_add(
          safe_add(rol(a, 5), sha1_ft(j, b, c, d)),
          safe_add(safe_add(e, w[j]), sha1_kt(j))
        );
        e = d;
        d = c;
        c = rol(b, 30);
        b = a;
        a = t;
      }

      a = safe_add(a, olda);
      b = safe_add(b, oldb);
      c = safe_add(c, oldc);
      d = safe_add(d, oldd);
      e = safe_add(e, olde);
    }
    return Array(a, b, c, d, e);
  }

  function sha1_ft(t, b, c, d) {
    if (t < 20) return (b & c) | (~b & d);
    if (t < 40) return b ^ c ^ d;
    if (t < 60) return (b & c) | (b & d) | (c & d);
    return b ^ c ^ d;
  }

  function sha1_kt(t) {
    return t < 20
      ? 1518500249
      : t < 40
      ? 1859775393
      : t < 60
      ? -1894007588
      : -899497514;
  }

  function safe_add(x, y) {
    var lsw = (x & 0xffff) + (y & 0xffff);
    var msw = (x >> 16) + (y >> 16) + (lsw >> 16);
    return (msw << 16) | (lsw & 0xffff);
  }

  function rol(num, cnt) {
    return (num << cnt) | (num >>> (32 - cnt));
  }

  function str2binb(str) {
    var bin = Array();
    var mask = (1 << chrsz) - 1;
    for (var i = 0; i < str.length * chrsz; i += chrsz)
      bin[i >> 5] |= (str.charCodeAt(i / chrsz) & mask) << (24 - (i % 32));
    return bin;
  }

  function binb2hex(binarray) {
    var hex_tab = hexcase ? '0123456789ABCDEF' : '0123456789abcdef';
    var str = '';
    for (var i = 0; i < binarray.length * 4; i++) {
      str +=
        hex_tab.charAt((binarray[i >> 2] >> ((3 - (i % 4)) * 8 + 4)) & 0xf) +
        hex_tab.charAt((binarray[i >> 2] >> ((3 - (i % 4)) * 8)) & 0xf);
    }
    return str;
  }

  return hex_sha1(input);
}
```
