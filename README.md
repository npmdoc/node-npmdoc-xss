# api documentation for  [xss (v0.3.3)](https://github.com/leizongmin/js-xss)  [![npm package](https://img.shields.io/npm/v/npmdoc-xss.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-xss) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-xss.svg)](https://travis-ci.org/npmdoc/node-npmdoc-xss)
#### Sanitize untrusted HTML (to prevent XSS) with a configuration specified by a Whitelist

[![NPM](https://nodei.co/npm/xss.png?downloads=true)](https://www.npmjs.com/package/xss)

[![apidoc](https://npmdoc.github.io/node-npmdoc-xss/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-xss_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-xss/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-xss/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-xss/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Zongmin Lei",
        "email": "leizongmin@gmail.com",
        "url": "http://ucdok.com"
    },
    "bin": {
        "xss": "./bin/xss"
    },
    "bugs": {
        "url": "https://github.com/leizongmin/js-xss/issues"
    },
    "contributors": [
        {
            "name": "Zongmin Lei",
            "email": "leizongmin@gmail.com",
            "url": "http://ucdok.com"
        }
    ],
    "dependencies": {
        "commander": "^2.9.0",
        "cssfilter": "0.0.9"
    },
    "description": "Sanitize untrusted HTML (to prevent XSS) with a configuration specified by a Whitelist",
    "devDependencies": {
        "browserify": "^13.0.1",
        "coveralls": "^2.11.9",
        "debug": "^2.2.0",
        "istanbul": "^0.4.3",
        "mocha": "^3.0.2",
        "uglify-js": "^2.6.1"
    },
    "directories": {},
    "dist": {
        "shasum": "a014360dee10317331f9e74258141f7ed03fc784",
        "tarball": "https://registry.npmjs.org/xss/-/xss-0.3.3.tgz"
    },
    "engines": {
        "node": ">= 0.10.0"
    },
    "files": [
        "lib",
        "bin/xss",
        "dist",
        "typings/*.d.ts"
    ],
    "gitHead": "18e0258ff2d9ecfd8bc99e83cc0c52ea8a28caea",
    "homepage": "https://github.com/leizongmin/js-xss",
    "keywords": [
        "sanitization",
        "xss",
        "sanitize",
        "sanitisation",
        "input",
        "security",
        "escape",
        "encode",
        "filter",
        "validator",
        "html",
        "injection",
        "whitelist"
    ],
    "license": "MIT",
    "main": "./lib/index.js",
    "maintainers": [
        {
            "name": "leizongmin",
            "email": "leizongmin@gmail.com"
        }
    ],
    "name": "xss",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/leizongmin/js-xss.git"
    },
    "scripts": {
        "build": "./bin/build",
        "prepublish": "npm run test && npm run build",
        "test": "export DEBUG=xss:* && mocha -t 5000",
        "test-cov": "export DEBUG=xss:* && istanbul cover _mocha --report lcovonly -- -t 5000 -R spec && cat ./coverage/lcov.info | ./node_modules/coveralls/bin/coveralls.js && rm -rf ./coverage"
    },
    "typings": "./typings/xss.d.ts",
    "version": "0.3.3"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module xss](#apidoc.module.xss)
1.  [function <span class="apidocSignatureSpan">xss.</span>FilterXSS (options)](#apidoc.element.xss.FilterXSS)
1.  [function <span class="apidocSignatureSpan">xss.</span>StripTagBody (tags, next)](#apidoc.element.xss.StripTagBody)
1.  [function <span class="apidocSignatureSpan">xss.</span>clearNonPrintableCharacter (str)](#apidoc.element.xss.clearNonPrintableCharacter)
1.  [function <span class="apidocSignatureSpan">xss.</span>escapeAttrValue (str)](#apidoc.element.xss.escapeAttrValue)
1.  [function <span class="apidocSignatureSpan">xss.</span>escapeDangerHtml5Entities (str)](#apidoc.element.xss.escapeDangerHtml5Entities)
1.  [function <span class="apidocSignatureSpan">xss.</span>escapeHtml (html)](#apidoc.element.xss.escapeHtml)
1.  [function <span class="apidocSignatureSpan">xss.</span>escapeHtmlEntities (str)](#apidoc.element.xss.escapeHtmlEntities)
1.  [function <span class="apidocSignatureSpan">xss.</span>escapeQuote (str)](#apidoc.element.xss.escapeQuote)
1.  [function <span class="apidocSignatureSpan">xss.</span>friendlyAttrValue (str)](#apidoc.element.xss.friendlyAttrValue)
1.  [function <span class="apidocSignatureSpan">xss.</span>getDefaultCSSWhiteList ()](#apidoc.element.xss.getDefaultCSSWhiteList)
1.  [function <span class="apidocSignatureSpan">xss.</span>getDefaultWhiteList ()](#apidoc.element.xss.getDefaultWhiteList)
1.  [function <span class="apidocSignatureSpan">xss.</span>onIgnoreTag (tag, html, options)](#apidoc.element.xss.onIgnoreTag)
1.  [function <span class="apidocSignatureSpan">xss.</span>onIgnoreTagAttr (tag, name, value)](#apidoc.element.xss.onIgnoreTagAttr)
1.  [function <span class="apidocSignatureSpan">xss.</span>onIgnoreTagStripAll ()](#apidoc.element.xss.onIgnoreTagStripAll)
1.  [function <span class="apidocSignatureSpan">xss.</span>onTag (tag, html, options)](#apidoc.element.xss.onTag)
1.  [function <span class="apidocSignatureSpan">xss.</span>onTagAttr (tag, name, value)](#apidoc.element.xss.onTagAttr)
1.  [function <span class="apidocSignatureSpan">xss.</span>parseAttr (html, onAttr)](#apidoc.element.xss.parseAttr)
1.  [function <span class="apidocSignatureSpan">xss.</span>parseTag (html, onTag, escapeHtml)](#apidoc.element.xss.parseTag)
1.  [function <span class="apidocSignatureSpan">xss.</span>safeAttrValue (tag, name, value, cssFilter)](#apidoc.element.xss.safeAttrValue)
1.  [function <span class="apidocSignatureSpan">xss.</span>stripBlankChar (html)](#apidoc.element.xss.stripBlankChar)
1.  [function <span class="apidocSignatureSpan">xss.</span>stripCommentTag (html)](#apidoc.element.xss.stripCommentTag)
1.  [function <span class="apidocSignatureSpan">xss.</span>unescapeQuote (str)](#apidoc.element.xss.unescapeQuote)
1.  object <span class="apidocSignatureSpan">xss.</span>FilterXSS.prototype
1.  object <span class="apidocSignatureSpan">xss.</span>cssFilter
1.  object <span class="apidocSignatureSpan">xss.</span>default
1.  object <span class="apidocSignatureSpan">xss.</span>parser
1.  object <span class="apidocSignatureSpan">xss.</span>util
1.  object <span class="apidocSignatureSpan">xss.</span>whiteList

#### [module xss.FilterXSS](#apidoc.module.xss.FilterXSS)
1.  [function <span class="apidocSignatureSpan">xss.</span>FilterXSS (options)](#apidoc.element.xss.FilterXSS.FilterXSS)

#### [module xss.FilterXSS.prototype](#apidoc.module.xss.FilterXSS.prototype)
1.  [function <span class="apidocSignatureSpan">xss.FilterXSS.prototype.</span>process (html)](#apidoc.element.xss.FilterXSS.prototype.process)

#### [module xss.default](#apidoc.module.xss.default)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>StripTagBody (tags, next)](#apidoc.element.xss.default.StripTagBody)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>clearNonPrintableCharacter (str)](#apidoc.element.xss.default.clearNonPrintableCharacter)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>escapeAttrValue (str)](#apidoc.element.xss.default.escapeAttrValue)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>escapeDangerHtml5Entities (str)](#apidoc.element.xss.default.escapeDangerHtml5Entities)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>escapeHtml (html)](#apidoc.element.xss.default.escapeHtml)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>escapeHtmlEntities (str)](#apidoc.element.xss.default.escapeHtmlEntities)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>escapeQuote (str)](#apidoc.element.xss.default.escapeQuote)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>friendlyAttrValue (str)](#apidoc.element.xss.default.friendlyAttrValue)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>getDefaultCSSWhiteList ()](#apidoc.element.xss.default.getDefaultCSSWhiteList)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>getDefaultWhiteList ()](#apidoc.element.xss.default.getDefaultWhiteList)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>onIgnoreTag (tag, html, options)](#apidoc.element.xss.default.onIgnoreTag)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>onIgnoreTagAttr (tag, name, value)](#apidoc.element.xss.default.onIgnoreTagAttr)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>onIgnoreTagStripAll ()](#apidoc.element.xss.default.onIgnoreTagStripAll)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>onTag (tag, html, options)](#apidoc.element.xss.default.onTag)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>onTagAttr (tag, name, value)](#apidoc.element.xss.default.onTagAttr)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>safeAttrValue (tag, name, value, cssFilter)](#apidoc.element.xss.default.safeAttrValue)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>stripBlankChar (html)](#apidoc.element.xss.default.stripBlankChar)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>stripCommentTag (html)](#apidoc.element.xss.default.stripCommentTag)
1.  [function <span class="apidocSignatureSpan">xss.default.</span>unescapeQuote (str)](#apidoc.element.xss.default.unescapeQuote)
1.  object <span class="apidocSignatureSpan">xss.default.</span>cssFilter
1.  object <span class="apidocSignatureSpan">xss.default.</span>whiteList

#### [module xss.parser](#apidoc.module.xss.parser)
1.  [function <span class="apidocSignatureSpan">xss.parser.</span>parseAttr (html, onAttr)](#apidoc.element.xss.parser.parseAttr)
1.  [function <span class="apidocSignatureSpan">xss.parser.</span>parseTag (html, onTag, escapeHtml)](#apidoc.element.xss.parser.parseTag)

#### [module xss.util](#apidoc.module.xss.util)
1.  [function <span class="apidocSignatureSpan">xss.util.</span>forEach (arr, fn, scope)](#apidoc.element.xss.util.forEach)
1.  [function <span class="apidocSignatureSpan">xss.util.</span>indexOf (arr, item)](#apidoc.element.xss.util.indexOf)
1.  [function <span class="apidocSignatureSpan">xss.util.</span>trim (str)](#apidoc.element.xss.util.trim)



# <a name="apidoc.module.xss"></a>[module xss](#apidoc.module.xss)

#### <a name="apidoc.element.xss.FilterXSS"></a>[function <span class="apidocSignatureSpan">xss.</span>FilterXSS (options)](#apidoc.element.xss.FilterXSS)
- description and source-code
```javascript
function FilterXSS(options) {
  options = shallowCopyObject(options || {});

  if (options.stripIgnoreTag) {
    if (options.onIgnoreTag) {
      console.error('Notes: cannot use these two options "stripIgnoreTag" and "onIgnoreTag" at the same time');
    }
    options.onIgnoreTag = DEFAULT.onIgnoreTagStripAll;
  }

  options.whiteList = options.whiteList || DEFAULT.whiteList;
  options.onTag = options.onTag || DEFAULT.onTag;
  options.onTagAttr = options.onTagAttr || DEFAULT.onTagAttr;
  options.onIgnoreTag = options.onIgnoreTag || DEFAULT.onIgnoreTag;
  options.onIgnoreTagAttr = options.onIgnoreTagAttr || DEFAULT.onIgnoreTagAttr;
  options.safeAttrValue = options.safeAttrValue || DEFAULT.safeAttrValue;
  options.escapeHtml = options.escapeHtml || DEFAULT.escapeHtml;
  this.options = options;

  if (options.css === false) {
    this.cssFilter = false;
  } else {
    options.css = options.css || {};
    this.cssFilter = new FilterCSS(options.css);
  }
}
```
- example usage
```shell
...
'''

To avoid passing 'options' every time, you can also do it in a faster way by
creating a 'FilterXSS' instance:

'''javascript
options = {};  // Custom rules
myxss = new xss.FilterXSS(options);
// then apply myxss.process()
html = myxss.process('<script>alert("xss");</script>');
'''

Details of parameters in 'options' would be described below.

### Whitelist
...
```

#### <a name="apidoc.element.xss.StripTagBody"></a>[function <span class="apidocSignatureSpan">xss.</span>StripTagBody (tags, next)](#apidoc.element.xss.StripTagBody)
- description and source-code
```javascript
function StripTagBody(tags, next) {
  if (typeof(next) !== 'function') {
    next = function () {};
  }

  var isRemoveAllTag = !Array.isArray(tags);
  function isRemoveTag (tag) {
    if (isRemoveAllTag) return true;
    return (_.indexOf(tags, tag) !== -1);
  }

  var removeList = [];   // 要删除的位置范围列表
  var posStart = false;  // 当前标签开始位置

  return {
    onIgnoreTag: function (tag, html, options) {
      if (isRemoveTag(tag)) {
        if (options.isClosing) {
          var ret = '[/removed]';
          var end = options.position + ret.length;
          removeList.push([posStart !== false ? posStart : options.position, end]);
          posStart = false;
          return ret;
        } else {
          if (!posStart) {
            posStart = options.position;
          }
          return '[removed]';
        }
      } else {
        return next(tag, html, options);
      }
    },
    remove: function (html) {
      var rethtml = '';
      var lastPos = 0;
      _.forEach(removeList, function (pos) {
        rethtml += html.slice(lastPos, pos[0]);
        lastPos = pos[1];
      });
      rethtml += html.slice(lastPos);
      return rethtml;
    }
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.clearNonPrintableCharacter"></a>[function <span class="apidocSignatureSpan">xss.</span>clearNonPrintableCharacter (str)](#apidoc.element.xss.clearNonPrintableCharacter)
- description and source-code
```javascript
function clearNonPrintableCharacter(str) {
  var str2 = '';
  for (var i = 0, len = str.length; i < len; i++) {
    str2 += str.charCodeAt(i) < 32 ? ' ' : str.charAt(i);
  }
  return _.trim(str2);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.escapeAttrValue"></a>[function <span class="apidocSignatureSpan">xss.</span>escapeAttrValue (str)](#apidoc.element.xss.escapeAttrValue)
- description and source-code
```javascript
function escapeAttrValue(str) {
  str = escapeQuote(str);
  str = escapeHtml(str);
  return str;
}
```
- example usage
```shell
...

'''javascript
var source = '<div a="1" b="2" data-a="3" data-b="4">hello</div>';
var html = xss(source, {
  onIgnoreTagAttr: function (tag, name, value, isWhiteAttr) {
    if (name.substr(0, 5) === 'data-') {
      // escape its value using built-in escapeAttrValue function
      return name + '="' + xss.escapeAttrValue(value) + '"';
    }
  }
});

console.log('%s\nconvert to:\n%s', source, html);
'''
...
```

#### <a name="apidoc.element.xss.escapeDangerHtml5Entities"></a>[function <span class="apidocSignatureSpan">xss.</span>escapeDangerHtml5Entities (str)](#apidoc.element.xss.escapeDangerHtml5Entities)
- description and source-code
```javascript
function escapeDangerHtml5Entities(str) {
  return str.replace(REGEXP_ATTR_VALUE_COLON, ':')
            .replace(REGEXP_ATTR_VALUE_NEWLINE, ' ');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.escapeHtml"></a>[function <span class="apidocSignatureSpan">xss.</span>escapeHtml (html)](#apidoc.element.xss.escapeHtml)
- description and source-code
```javascript
function escapeHtml(html) {
  return html.replace(REGEXP_LT, '&lt;').replace(REGEXP_GT, '&gt;');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.escapeHtmlEntities"></a>[function <span class="apidocSignatureSpan">xss.</span>escapeHtmlEntities (str)](#apidoc.element.xss.escapeHtmlEntities)
- description and source-code
```javascript
function escapeHtmlEntities(str) {
  return str.replace(REGEXP_ATTR_VALUE_1, function replaceUnicode (str, code) {
    return (code[0] === 'x' || code[0] === 'X')
            ? String.fromCharCode(parseInt(code.substr(1), 16))
            : String.fromCharCode(parseInt(code, 10));
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.escapeQuote"></a>[function <span class="apidocSignatureSpan">xss.</span>escapeQuote (str)](#apidoc.element.xss.escapeQuote)
- description and source-code
```javascript
function escapeQuote(str) {
  return str.replace(REGEXP_QUOTE, '&quot;');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.friendlyAttrValue"></a>[function <span class="apidocSignatureSpan">xss.</span>friendlyAttrValue (str)](#apidoc.element.xss.friendlyAttrValue)
- description and source-code
```javascript
function friendlyAttrValue(str) {
  str = unescapeQuote(str);             // 双引号
  str = escapeHtmlEntities(str);         // 转换HTML实体编码
  str = escapeDangerHtml5Entities(str);  // 转换危险的HTML5新增实体编码
  str = clearNonPrintableCharacter(str); // 清除不可见字符
  return str;
}
```
- example usage
```shell
...
var list = [];
var html = xss(source, {
  onTagAttr: function (tag, name, value, isWhiteAttr) {
    if (tag === 'img' && name === 'src') {
      // Use the built-in friendlyAttrValue function to escape attribute
      // values. It supports converting entity tags such as &lt; to printable
      // characters such as <
      list.push(xss.friendlyAttrValue(value));
    }
    // Return nothing, means keep the default handling measure
  }
});

console.log('image list:\n%s', list.join(', '));
'''
...
```

#### <a name="apidoc.element.xss.getDefaultCSSWhiteList"></a>[function <span class="apidocSignatureSpan">xss.</span>getDefaultCSSWhiteList ()](#apidoc.element.xss.getDefaultCSSWhiteList)
- description and source-code
```javascript
function getDefaultWhiteList() {
  // 白名单值说明：
  // true: 允许该属性
  // Function: function (val) { } 返回true表示允许该属性，其他值均表示不允许
  // RegExp: regexp.test(val) 返回true表示允许该属性，其他值均表示不允许
  // 除上面列出的值外均表示不允许
  var whiteList = {};

  whiteList['align-content'] = false; // default: auto
  whiteList['align-items'] = false; // default: auto
  whiteList['align-self'] = false; // default: auto
  whiteList['alignment-adjust'] = false; // default: auto
  whiteList['alignment-baseline'] = false; // default: baseline
  whiteList['all'] = false; // default: depending on individual properties
  whiteList['anchor-point'] = false; // default: none
  whiteList['animation'] = false; // default: depending on individual properties
  whiteList['animation-delay'] = false; // default: 0
  whiteList['animation-direction'] = false; // default: normal
  whiteList['animation-duration'] = false; // default: 0
  whiteList['animation-fill-mode'] = false; // default: none
  whiteList['animation-iteration-count'] = false; // default: 1
  whiteList['animation-name'] = false; // default: none
  whiteList['animation-play-state'] = false; // default: running
  whiteList['animation-timing-function'] = false; // default: ease
  whiteList['azimuth'] = false; // default: center
  whiteList['backface-visibility'] = false; // default: visible
  whiteList['background'] = true; // default: depending on individual properties
  whiteList['background-attachment'] = true; // default: scroll
  whiteList['background-clip'] = true; // default: border-box
  whiteList['background-color'] = true; // default: transparent
  whiteList['background-image'] = true; // default: none
  whiteList['background-origin'] = true; // default: padding-box
  whiteList['background-position'] = true; // default: 0% 0%
  whiteList['background-repeat'] = true; // default: repeat
  whiteList['background-size'] = true; // default: auto
  whiteList['baseline-shift'] = false; // default: baseline
  whiteList['binding'] = false; // default: none
  whiteList['bleed'] = false; // default: 6pt
  whiteList['bookmark-label'] = false; // default: content()
  whiteList['bookmark-level'] = false; // default: none
  whiteList['bookmark-state'] = false; // default: open
  whiteList['border'] = true; // default: depending on individual properties
  whiteList['border-bottom'] = true; // default: depending on individual properties
  whiteList['border-bottom-color'] = true; // default: current color
  whiteList['border-bottom-left-radius'] = true; // default: 0
  whiteList['border-bottom-right-radius'] = true; // default: 0
  whiteList['border-bottom-style'] = true; // default: none
  whiteList['border-bottom-width'] = true; // default: medium
  whiteList['border-collapse'] = true; // default: separate
  whiteList['border-color'] = true; // default: depending on individual properties
  whiteList['border-image'] = true; // default: none
  whiteList['border-image-outset'] = true; // default: 0
  whiteList['border-image-repeat'] = true; // default: stretch
  whiteList['border-image-slice'] = true; // default: 100%
  whiteList['border-image-source'] = true; // default: none
  whiteList['border-image-width'] = true; // default: 1
  whiteList['border-left'] = true; // default: depending on individual properties
  whiteList['border-left-color'] = true; // default: current color
  whiteList['border-left-style'] = true; // default: none
  whiteList['border-left-width'] = true; // default: medium
  whiteList['border-radius'] = true; // default: 0
  whiteList['border-right'] = true; // default: depending on individual properties
  whiteList['border-right-color'] = true; // default: current color
  whiteList['border-right-style'] = true; // default: none
  whiteList['border-right-width'] = true; // default: medium
  whiteList['border-spacing'] = true; // default: 0
  whiteList['border-style'] = true; // default: depending on individual properties
  whiteList['border-top'] = true; // default: depending on individual properties
  whiteList['border-top-color'] = true; // default: current color
  whiteList['border-top-left-radius'] = true; ...
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.getDefaultWhiteList"></a>[function <span class="apidocSignatureSpan">xss.</span>getDefaultWhiteList ()](#apidoc.element.xss.getDefaultWhiteList)
- description and source-code
```javascript
function getDefaultWhiteList() {
  return {
    a:      ['target', 'href', 'title'],
    abbr:   ['title'],
    address: [],
    area:   ['shape', 'coords', 'href', 'alt'],
    article: [],
    aside:  [],
    audio:  ['autoplay', 'controls', 'loop', 'preload', 'src'],
    b:      [],
    bdi:    ['dir'],
    bdo:    ['dir'],
    big:    [],
    blockquote: ['cite'],
    br:     [],
    caption: [],
    center: [],
    cite:   [],
    code:   [],
    col:    ['align', 'valign', 'span', 'width'],
    colgroup: ['align', 'valign', 'span', 'width'],
    dd:     [],
    del:    ['datetime'],
    details: ['open'],
    div:    [],
    dl:     [],
    dt:     [],
    em:     [],
    font:   ['color', 'size', 'face'],
    footer: [],
    h1:     [],
    h2:     [],
    h3:     [],
    h4:     [],
    h5:     [],
    h6:     [],
    header: [],
    hr:     [],
    i:      [],
    img:    ['src', 'alt', 'title', 'width', 'height'],
    ins:    ['datetime'],
    li:     [],
    mark:   [],
    nav:    [],
    ol:     [],
    p:      [],
    pre:    [],
    s:      [],
    section:[],
    small:  [],
    span:   [],
    sub:    [],
    sup:    [],
    strong: [],
    table:  ['width', 'border', 'align', 'valign'],
    tbody:  ['align', 'valign'],
    td:     ['width', 'rowspan', 'colspan', 'align', 'valign'],
    tfoot:  ['align', 'valign'],
    th:     ['width', 'rowspan', 'colspan', 'align', 'valign'],
    thead:  ['align', 'valign'],
    tr:     ['rowspan', 'align', 'valign'],
    tt:     [],
    u:      [],
    ul:     [],
    video:  ['autoplay', 'controls', 'loop', 'preload', 'src', 'height', 'width']
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.onIgnoreTag"></a>[function <span class="apidocSignatureSpan">xss.</span>onIgnoreTag (tag, html, options)](#apidoc.element.xss.onIgnoreTag)
- description and source-code
```javascript
function onIgnoreTag(tag, html, options) {
  // do nothing
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.onIgnoreTagAttr"></a>[function <span class="apidocSignatureSpan">xss.</span>onIgnoreTagAttr (tag, name, value)](#apidoc.element.xss.onIgnoreTagAttr)
- description and source-code
```javascript
function onIgnoreTagAttr(tag, name, value) {
  // do nothing
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.onIgnoreTagStripAll"></a>[function <span class="apidocSignatureSpan">xss.</span>onIgnoreTagStripAll ()](#apidoc.element.xss.onIgnoreTagStripAll)
- description and source-code
```javascript
function onIgnoreTagStripAll() {
  return '';
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.onTag"></a>[function <span class="apidocSignatureSpan">xss.</span>onTag (tag, html, options)](#apidoc.element.xss.onTag)
- description and source-code
```javascript
function onTag(tag, html, options) {
  // do nothing
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.onTagAttr"></a>[function <span class="apidocSignatureSpan">xss.</span>onTagAttr (tag, name, value)](#apidoc.element.xss.onTagAttr)
- description and source-code
```javascript
function onTagAttr(tag, name, value) {
  // do nothing
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.parseAttr"></a>[function <span class="apidocSignatureSpan">xss.</span>parseAttr (html, onAttr)](#apidoc.element.xss.parseAttr)
- description and source-code
```javascript
function parseAttr(html, onAttr) {
  'user strict';

  var lastPos = 0;        // 当前位置
  var retAttrs = [];      // 待返回的属性列表
  var tmpName = false;    // 临时属性名称
  var len = html.length;  // HTML代码长度

  function addAttr (name, value) {
    name = _.trim(name);
    name = name.replace(REGEXP_ATTR_NAME, '').toLowerCase();
    if (name.length < 1) return;
    var ret = onAttr(name, value || '');
    if (ret) retAttrs.push(ret);
  };

  // 逐个分析字符
  for (var i = 0; i < len; i++) {
    var c = html.charAt(i);
    var v, j;
    if (tmpName === false && c === '=') {
      tmpName = html.slice(lastPos, i);
      lastPos = i + 1;
      continue;
    }
    if (tmpName !== false) {
      // HTML标签内的引号仅当前一个字符是等于号时才有效
      if (i === lastPos && (c === '"' || c === "'") && html.charAt(i - 1) === '=') {
        j = html.indexOf(c, i + 1);
        if (j === -1) {
          break;
        } else {
          v = _.trim(html.slice(lastPos + 1, j));
          addAttr(tmpName, v);
          tmpName = false;
          i = j;
          lastPos = i + 1;
          continue;
        }
      }
    }
    if (c === ' ') {
      if (tmpName === false) {
        j = findNextEqual(html, i);
        if (j === -1) {
          v = _.trim(html.slice(lastPos, i));
          addAttr(v);
          tmpName = false;
          lastPos = i + 1;
          continue;
        } else {
          i = j - 1;
          continue;
        }
      } else {
        j = findBeforeEqual(html, i - 1);
        if (j === -1) {
          v = _.trim(html.slice(lastPos, i));
          v = stripQuoteWrap(v);
          addAttr(tmpName, v);
          tmpName = false;
          lastPos = i + 1;
          continue;
        } else {
          continue;
        }
      }
    }
  }

  if (lastPos < html.length) {
    if (tmpName === false) {
      addAttr(html.slice(lastPos));
    } else {
      addAttr(tmpName, stripQuoteWrap(_.trim(html.slice(lastPos))));
    }
  }

  return _.trim(retAttrs.join(' '));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.parseTag"></a>[function <span class="apidocSignatureSpan">xss.</span>parseTag (html, onTag, escapeHtml)](#apidoc.element.xss.parseTag)
- description and source-code
```javascript
function parseTag(html, onTag, escapeHtml) {
  'user strict';

  var rethtml = '';        // 待返回的HTML
  var lastPos = 0;         // 上一个标签结束位置
  var tagStart = false;    // 当前标签开始位置
  var quoteStart = false;  // 引号开始位置
  var currentPos = 0;      // 当前位置
  var len = html.length;   // HTML长度
  var currentHtml = '';    // 当前标签的HTML代码
  var currentTagName = ''; // 当前标签的名称

  // 逐个分析字符
  for (currentPos = 0; currentPos < len; currentPos++) {
    var c = html.charAt(currentPos);
    if (tagStart === false) {
      if (c === '<') {
        tagStart = currentPos;
        continue;
      }
    } else {
      if (quoteStart === false) {
        if (c === '<') {
          rethtml += escapeHtml(html.slice(lastPos, currentPos));
          tagStart = currentPos;
          lastPos = currentPos;
          continue;
        }
        if (c === '>') {
          rethtml += escapeHtml(html.slice(lastPos, tagStart));
          currentHtml = html.slice(tagStart, currentPos + 1);
          currentTagName = getTagName(currentHtml);
          rethtml += onTag(tagStart,
                           rethtml.length,
                           currentTagName,
                           currentHtml,
                           isClosing(currentHtml));
          lastPos = currentPos + 1;
          tagStart = false;
          continue;
        }
        // HTML标签内的引号仅当前一个字符是等于号时才有效
        if ((c === '"' || c === "'") && html.charAt(currentPos - 1) === '=') {
          quoteStart = c;
          continue;
        }
      } else {
        if (c === quoteStart) {
          quoteStart = false;
          continue;
        }
      }
    }
  }
  if (lastPos < html.length) {
    rethtml += escapeHtml(html.substr(lastPos));
  }

  return rethtml;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.safeAttrValue"></a>[function <span class="apidocSignatureSpan">xss.</span>safeAttrValue (tag, name, value, cssFilter)](#apidoc.element.xss.safeAttrValue)
- description and source-code
```javascript
function safeAttrValue(tag, name, value, cssFilter) {
  // 转换为友好的属性值，再做判断
  value = friendlyAttrValue(value);

  if (name === 'href' || name === 'src') {
    // 过滤 href 和 src 属性
    // 仅允许 http:// | https:// | mailto: | / | # 开头的地址
    value = _.trim(value);
    if (value === '#') return '#';
    if (!(value.substr(0, 7) === 'http://' ||
         value.substr(0, 8) === 'https://' ||
         value.substr(0, 7) === 'mailto:' ||
         value[0] === '#' ||
         value[0] === '/')) {
      return '';
    }
  } else if (name === 'background') {
    // 过滤 background 属性 （这个xss漏洞较老了，可能已经不适用）
    // javascript:
    REGEXP_DEFAULT_ON_TAG_ATTR_4.lastIndex = 0;
    if (REGEXP_DEFAULT_ON_TAG_ATTR_4.test(value)) {
      return '';
    }
  } else if (name === 'style') {
    //<span class="apidocCodeCommentSpan"> /*注释*/
</span>    /*REGEXP_DEFAULT_ON_TAG_ATTR_3.lastIndex = 0;
    if (REGEXP_DEFAULT_ON_TAG_ATTR_3.test(value)) {
      return '';
    }*/
    // expression()
    REGEXP_DEFAULT_ON_TAG_ATTR_7.lastIndex = 0;
    if (REGEXP_DEFAULT_ON_TAG_ATTR_7.test(value)) {
      return '';
    }
    // url()
    REGEXP_DEFAULT_ON_TAG_ATTR_8.lastIndex = 0;
    if (REGEXP_DEFAULT_ON_TAG_ATTR_8.test(value)) {
      REGEXP_DEFAULT_ON_TAG_ATTR_4.lastIndex = 0;
      if (REGEXP_DEFAULT_ON_TAG_ATTR_4.test(value)) {
        return '';
      }
    }
    if (cssFilter !== false) {
      cssFilter = cssFilter || defaultCSSFilter;
      value = cssFilter.process(value);
    }
  }

  // 输出时需要转义<>"
  value = escapeAttrValue(value);
  return value;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.stripBlankChar"></a>[function <span class="apidocSignatureSpan">xss.</span>stripBlankChar (html)](#apidoc.element.xss.stripBlankChar)
- description and source-code
```javascript
function stripBlankChar(html) {
  var chars = html.split('');
  chars = chars.filter(function (char) {
    var c = char.charCodeAt(0);
    if (c === 127) return false;
    if (c <= 31) {
      if (c === 10 || c === 13) return true;
      return false;
    }
    return true;
  });
  return chars.join('');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.stripCommentTag"></a>[function <span class="apidocSignatureSpan">xss.</span>stripCommentTag (html)](#apidoc.element.xss.stripCommentTag)
- description and source-code
```javascript
function stripCommentTag(html) {
  return html.replace(STRIP_COMMENT_TAG_REGEXP, '');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.unescapeQuote"></a>[function <span class="apidocSignatureSpan">xss.</span>unescapeQuote (str)](#apidoc.element.xss.unescapeQuote)
- description and source-code
```javascript
function unescapeQuote(str) {
  return str.replace(REGEXP_QUOTE_2, '"');
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.xss.FilterXSS"></a>[module xss.FilterXSS](#apidoc.module.xss.FilterXSS)

#### <a name="apidoc.element.xss.FilterXSS.FilterXSS"></a>[function <span class="apidocSignatureSpan">xss.</span>FilterXSS (options)](#apidoc.element.xss.FilterXSS.FilterXSS)
- description and source-code
```javascript
function FilterXSS(options) {
  options = shallowCopyObject(options || {});

  if (options.stripIgnoreTag) {
    if (options.onIgnoreTag) {
      console.error('Notes: cannot use these two options "stripIgnoreTag" and "onIgnoreTag" at the same time');
    }
    options.onIgnoreTag = DEFAULT.onIgnoreTagStripAll;
  }

  options.whiteList = options.whiteList || DEFAULT.whiteList;
  options.onTag = options.onTag || DEFAULT.onTag;
  options.onTagAttr = options.onTagAttr || DEFAULT.onTagAttr;
  options.onIgnoreTag = options.onIgnoreTag || DEFAULT.onIgnoreTag;
  options.onIgnoreTagAttr = options.onIgnoreTagAttr || DEFAULT.onIgnoreTagAttr;
  options.safeAttrValue = options.safeAttrValue || DEFAULT.safeAttrValue;
  options.escapeHtml = options.escapeHtml || DEFAULT.escapeHtml;
  this.options = options;

  if (options.css === false) {
    this.cssFilter = false;
  } else {
    options.css = options.css || {};
    this.cssFilter = new FilterCSS(options.css);
  }
}
```
- example usage
```shell
...
'''

To avoid passing 'options' every time, you can also do it in a faster way by
creating a 'FilterXSS' instance:

'''javascript
options = {};  // Custom rules
myxss = new xss.FilterXSS(options);
// then apply myxss.process()
html = myxss.process('<script>alert("xss");</script>');
'''

Details of parameters in 'options' would be described below.

### Whitelist
...
```



# <a name="apidoc.module.xss.FilterXSS.prototype"></a>[module xss.FilterXSS.prototype](#apidoc.module.xss.FilterXSS.prototype)

#### <a name="apidoc.element.xss.FilterXSS.prototype.process"></a>[function <span class="apidocSignatureSpan">xss.FilterXSS.prototype.</span>process (html)](#apidoc.element.xss.FilterXSS.prototype.process)
- description and source-code
```javascript
process = function (html) {
  // 兼容各种奇葩输入
  html = html || '';
  html = html.toString();
  if (!html) return '';

  var me = this;
  var options = me.options;
  var whiteList = options.whiteList;
  var onTag = options.onTag;
  var onIgnoreTag = options.onIgnoreTag;
  var onTagAttr = options.onTagAttr;
  var onIgnoreTagAttr = options.onIgnoreTagAttr;
  var safeAttrValue = options.safeAttrValue;
  var escapeHtml = options.escapeHtml;
  var cssFilter = me.cssFilter;

  // 是否清除不可见字符
  if (options.stripBlankChar) {
    html = DEFAULT.stripBlankChar(html);
  }

  // 是否禁止备注标签
  if (!options.allowCommentTag) {
    html = DEFAULT.stripCommentTag(html);
  }

  // 如果开启了stripIgnoreTagBody
  var stripIgnoreTagBody = false;
  if (options.stripIgnoreTagBody) {
    var stripIgnoreTagBody = DEFAULT.StripTagBody(options.stripIgnoreTagBody, onIgnoreTag);
    onIgnoreTag = stripIgnoreTagBody.onIgnoreTag;
  }

  var retHtml = parseTag(html, function (sourcePosition, position, tag, html, isClosing) {
    var info = {
      sourcePosition: sourcePosition,
      position:       position,
      isClosing:      isClosing,
      isWhite:        (tag in whiteList)
    };

    // 调用onTag处理
    var ret = onTag(tag, html, info);
    if (!isNull(ret)) return ret;

    // 默认标签处理方法
    if (info.isWhite) {
      // 白名单标签，解析标签属性
      // 如果是闭合标签，则不需要解析属性
      if (info.isClosing) {
        return '</' + tag + '>';
      }

      var attrs = getAttrs(html);
      var whiteAttrList = whiteList[tag];
      var attrsHtml = parseAttr(attrs.html, function (name, value) {

        // 调用onTagAttr处理
        var isWhiteAttr = (_.indexOf(whiteAttrList, name) !== -1);
        var ret = onTagAttr(tag, name, value, isWhiteAttr);
        if (!isNull(ret)) return ret;

        // 默认的属性处理方法
        if (isWhiteAttr) {
          // 白名单属性，调用safeAttrValue过滤属性值
          value = safeAttrValue(tag, name, value, cssFilter);
          if (value) {
            return name + '="' + value + '"';
          } else {
            return name;
          }
        } else {
          // 非白名单属性，调用onIgnoreTagAttr处理
          var ret = onIgnoreTagAttr(tag, name, value, isWhiteAttr);
          if (!isNull(ret)) return ret;
          return;
        }
      });

      // 构造新的标签代码
      var html = '<' + tag;
      if (attrsHtml) html += ' ' + attrsHtml;
      if (attrs.closing) html += ' /';
      html += '>';
      return html;

    } else {
      // 非白名单标签，调用onIgnoreTag处理
      var ret = onIgnoreTag(tag, html, info);
      if (!isNull(ret)) return ret;
      return escapeHtml(html);
    }

  }, escapeHtml);

  // 如果开启了stripIgnoreTagBody，需要对结果再进行处理
  if (stripIgnoreTagBody) {
    retHtml = stripIgnoreTagBody.remove(retHtml);
  }

  return retHtml;
}
```
- example usage
```shell
...

To avoid passing 'options' every time, you can also do it in a faster way by
creating a 'FilterXSS' instance:

'''javascript
options = {};  // Custom rules
myxss = new xss.FilterXSS(options);
// then apply myxss.process()
html = myxss.process('<script>alert("xss");</script>');
'''

Details of parameters in 'options' would be described below.

### Whitelist
...
```



# <a name="apidoc.module.xss.default"></a>[module xss.default](#apidoc.module.xss.default)

#### <a name="apidoc.element.xss.default.StripTagBody"></a>[function <span class="apidocSignatureSpan">xss.default.</span>StripTagBody (tags, next)](#apidoc.element.xss.default.StripTagBody)
- description and source-code
```javascript
function StripTagBody(tags, next) {
  if (typeof(next) !== 'function') {
    next = function () {};
  }

  var isRemoveAllTag = !Array.isArray(tags);
  function isRemoveTag (tag) {
    if (isRemoveAllTag) return true;
    return (_.indexOf(tags, tag) !== -1);
  }

  var removeList = [];   // 要删除的位置范围列表
  var posStart = false;  // 当前标签开始位置

  return {
    onIgnoreTag: function (tag, html, options) {
      if (isRemoveTag(tag)) {
        if (options.isClosing) {
          var ret = '[/removed]';
          var end = options.position + ret.length;
          removeList.push([posStart !== false ? posStart : options.position, end]);
          posStart = false;
          return ret;
        } else {
          if (!posStart) {
            posStart = options.position;
          }
          return '[removed]';
        }
      } else {
        return next(tag, html, options);
      }
    },
    remove: function (html) {
      var rethtml = '';
      var lastPos = 0;
      _.forEach(removeList, function (pos) {
        rethtml += html.slice(lastPos, pos[0]);
        lastPos = pos[1];
      });
      rethtml += html.slice(lastPos);
      return rethtml;
    }
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.clearNonPrintableCharacter"></a>[function <span class="apidocSignatureSpan">xss.default.</span>clearNonPrintableCharacter (str)](#apidoc.element.xss.default.clearNonPrintableCharacter)
- description and source-code
```javascript
function clearNonPrintableCharacter(str) {
  var str2 = '';
  for (var i = 0, len = str.length; i < len; i++) {
    str2 += str.charCodeAt(i) < 32 ? ' ' : str.charAt(i);
  }
  return _.trim(str2);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.escapeAttrValue"></a>[function <span class="apidocSignatureSpan">xss.default.</span>escapeAttrValue (str)](#apidoc.element.xss.default.escapeAttrValue)
- description and source-code
```javascript
function escapeAttrValue(str) {
  str = escapeQuote(str);
  str = escapeHtml(str);
  return str;
}
```
- example usage
```shell
...

'''javascript
var source = '<div a="1" b="2" data-a="3" data-b="4">hello</div>';
var html = xss(source, {
  onIgnoreTagAttr: function (tag, name, value, isWhiteAttr) {
    if (name.substr(0, 5) === 'data-') {
      // escape its value using built-in escapeAttrValue function
      return name + '="' + xss.escapeAttrValue(value) + '"';
    }
  }
});

console.log('%s\nconvert to:\n%s', source, html);
'''
...
```

#### <a name="apidoc.element.xss.default.escapeDangerHtml5Entities"></a>[function <span class="apidocSignatureSpan">xss.default.</span>escapeDangerHtml5Entities (str)](#apidoc.element.xss.default.escapeDangerHtml5Entities)
- description and source-code
```javascript
function escapeDangerHtml5Entities(str) {
  return str.replace(REGEXP_ATTR_VALUE_COLON, ':')
            .replace(REGEXP_ATTR_VALUE_NEWLINE, ' ');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.escapeHtml"></a>[function <span class="apidocSignatureSpan">xss.default.</span>escapeHtml (html)](#apidoc.element.xss.default.escapeHtml)
- description and source-code
```javascript
function escapeHtml(html) {
  return html.replace(REGEXP_LT, '&lt;').replace(REGEXP_GT, '&gt;');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.escapeHtmlEntities"></a>[function <span class="apidocSignatureSpan">xss.default.</span>escapeHtmlEntities (str)](#apidoc.element.xss.default.escapeHtmlEntities)
- description and source-code
```javascript
function escapeHtmlEntities(str) {
  return str.replace(REGEXP_ATTR_VALUE_1, function replaceUnicode (str, code) {
    return (code[0] === 'x' || code[0] === 'X')
            ? String.fromCharCode(parseInt(code.substr(1), 16))
            : String.fromCharCode(parseInt(code, 10));
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.escapeQuote"></a>[function <span class="apidocSignatureSpan">xss.default.</span>escapeQuote (str)](#apidoc.element.xss.default.escapeQuote)
- description and source-code
```javascript
function escapeQuote(str) {
  return str.replace(REGEXP_QUOTE, '&quot;');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.friendlyAttrValue"></a>[function <span class="apidocSignatureSpan">xss.default.</span>friendlyAttrValue (str)](#apidoc.element.xss.default.friendlyAttrValue)
- description and source-code
```javascript
function friendlyAttrValue(str) {
  str = unescapeQuote(str);             // 双引号
  str = escapeHtmlEntities(str);         // 转换HTML实体编码
  str = escapeDangerHtml5Entities(str);  // 转换危险的HTML5新增实体编码
  str = clearNonPrintableCharacter(str); // 清除不可见字符
  return str;
}
```
- example usage
```shell
...
var list = [];
var html = xss(source, {
  onTagAttr: function (tag, name, value, isWhiteAttr) {
    if (tag === 'img' && name === 'src') {
      // Use the built-in friendlyAttrValue function to escape attribute
      // values. It supports converting entity tags such as &lt; to printable
      // characters such as <
      list.push(xss.friendlyAttrValue(value));
    }
    // Return nothing, means keep the default handling measure
  }
});

console.log('image list:\n%s', list.join(', '));
'''
...
```

#### <a name="apidoc.element.xss.default.getDefaultCSSWhiteList"></a>[function <span class="apidocSignatureSpan">xss.default.</span>getDefaultCSSWhiteList ()](#apidoc.element.xss.default.getDefaultCSSWhiteList)
- description and source-code
```javascript
function getDefaultWhiteList() {
  // 白名单值说明：
  // true: 允许该属性
  // Function: function (val) { } 返回true表示允许该属性，其他值均表示不允许
  // RegExp: regexp.test(val) 返回true表示允许该属性，其他值均表示不允许
  // 除上面列出的值外均表示不允许
  var whiteList = {};

  whiteList['align-content'] = false; // default: auto
  whiteList['align-items'] = false; // default: auto
  whiteList['align-self'] = false; // default: auto
  whiteList['alignment-adjust'] = false; // default: auto
  whiteList['alignment-baseline'] = false; // default: baseline
  whiteList['all'] = false; // default: depending on individual properties
  whiteList['anchor-point'] = false; // default: none
  whiteList['animation'] = false; // default: depending on individual properties
  whiteList['animation-delay'] = false; // default: 0
  whiteList['animation-direction'] = false; // default: normal
  whiteList['animation-duration'] = false; // default: 0
  whiteList['animation-fill-mode'] = false; // default: none
  whiteList['animation-iteration-count'] = false; // default: 1
  whiteList['animation-name'] = false; // default: none
  whiteList['animation-play-state'] = false; // default: running
  whiteList['animation-timing-function'] = false; // default: ease
  whiteList['azimuth'] = false; // default: center
  whiteList['backface-visibility'] = false; // default: visible
  whiteList['background'] = true; // default: depending on individual properties
  whiteList['background-attachment'] = true; // default: scroll
  whiteList['background-clip'] = true; // default: border-box
  whiteList['background-color'] = true; // default: transparent
  whiteList['background-image'] = true; // default: none
  whiteList['background-origin'] = true; // default: padding-box
  whiteList['background-position'] = true; // default: 0% 0%
  whiteList['background-repeat'] = true; // default: repeat
  whiteList['background-size'] = true; // default: auto
  whiteList['baseline-shift'] = false; // default: baseline
  whiteList['binding'] = false; // default: none
  whiteList['bleed'] = false; // default: 6pt
  whiteList['bookmark-label'] = false; // default: content()
  whiteList['bookmark-level'] = false; // default: none
  whiteList['bookmark-state'] = false; // default: open
  whiteList['border'] = true; // default: depending on individual properties
  whiteList['border-bottom'] = true; // default: depending on individual properties
  whiteList['border-bottom-color'] = true; // default: current color
  whiteList['border-bottom-left-radius'] = true; // default: 0
  whiteList['border-bottom-right-radius'] = true; // default: 0
  whiteList['border-bottom-style'] = true; // default: none
  whiteList['border-bottom-width'] = true; // default: medium
  whiteList['border-collapse'] = true; // default: separate
  whiteList['border-color'] = true; // default: depending on individual properties
  whiteList['border-image'] = true; // default: none
  whiteList['border-image-outset'] = true; // default: 0
  whiteList['border-image-repeat'] = true; // default: stretch
  whiteList['border-image-slice'] = true; // default: 100%
  whiteList['border-image-source'] = true; // default: none
  whiteList['border-image-width'] = true; // default: 1
  whiteList['border-left'] = true; // default: depending on individual properties
  whiteList['border-left-color'] = true; // default: current color
  whiteList['border-left-style'] = true; // default: none
  whiteList['border-left-width'] = true; // default: medium
  whiteList['border-radius'] = true; // default: 0
  whiteList['border-right'] = true; // default: depending on individual properties
  whiteList['border-right-color'] = true; // default: current color
  whiteList['border-right-style'] = true; // default: none
  whiteList['border-right-width'] = true; // default: medium
  whiteList['border-spacing'] = true; // default: 0
  whiteList['border-style'] = true; // default: depending on individual properties
  whiteList['border-top'] = true; // default: depending on individual properties
  whiteList['border-top-color'] = true; // default: current color
  whiteList['border-top-left-radius'] = true; ...
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.getDefaultWhiteList"></a>[function <span class="apidocSignatureSpan">xss.default.</span>getDefaultWhiteList ()](#apidoc.element.xss.default.getDefaultWhiteList)
- description and source-code
```javascript
function getDefaultWhiteList() {
  return {
    a:      ['target', 'href', 'title'],
    abbr:   ['title'],
    address: [],
    area:   ['shape', 'coords', 'href', 'alt'],
    article: [],
    aside:  [],
    audio:  ['autoplay', 'controls', 'loop', 'preload', 'src'],
    b:      [],
    bdi:    ['dir'],
    bdo:    ['dir'],
    big:    [],
    blockquote: ['cite'],
    br:     [],
    caption: [],
    center: [],
    cite:   [],
    code:   [],
    col:    ['align', 'valign', 'span', 'width'],
    colgroup: ['align', 'valign', 'span', 'width'],
    dd:     [],
    del:    ['datetime'],
    details: ['open'],
    div:    [],
    dl:     [],
    dt:     [],
    em:     [],
    font:   ['color', 'size', 'face'],
    footer: [],
    h1:     [],
    h2:     [],
    h3:     [],
    h4:     [],
    h5:     [],
    h6:     [],
    header: [],
    hr:     [],
    i:      [],
    img:    ['src', 'alt', 'title', 'width', 'height'],
    ins:    ['datetime'],
    li:     [],
    mark:   [],
    nav:    [],
    ol:     [],
    p:      [],
    pre:    [],
    s:      [],
    section:[],
    small:  [],
    span:   [],
    sub:    [],
    sup:    [],
    strong: [],
    table:  ['width', 'border', 'align', 'valign'],
    tbody:  ['align', 'valign'],
    td:     ['width', 'rowspan', 'colspan', 'align', 'valign'],
    tfoot:  ['align', 'valign'],
    th:     ['width', 'rowspan', 'colspan', 'align', 'valign'],
    thead:  ['align', 'valign'],
    tr:     ['rowspan', 'align', 'valign'],
    tt:     [],
    u:      [],
    ul:     [],
    video:  ['autoplay', 'controls', 'loop', 'preload', 'src', 'height', 'width']
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.onIgnoreTag"></a>[function <span class="apidocSignatureSpan">xss.default.</span>onIgnoreTag (tag, html, options)](#apidoc.element.xss.default.onIgnoreTag)
- description and source-code
```javascript
function onIgnoreTag(tag, html, options) {
  // do nothing
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.onIgnoreTagAttr"></a>[function <span class="apidocSignatureSpan">xss.default.</span>onIgnoreTagAttr (tag, name, value)](#apidoc.element.xss.default.onIgnoreTagAttr)
- description and source-code
```javascript
function onIgnoreTagAttr(tag, name, value) {
  // do nothing
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.onIgnoreTagStripAll"></a>[function <span class="apidocSignatureSpan">xss.default.</span>onIgnoreTagStripAll ()](#apidoc.element.xss.default.onIgnoreTagStripAll)
- description and source-code
```javascript
function onIgnoreTagStripAll() {
  return '';
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.onTag"></a>[function <span class="apidocSignatureSpan">xss.default.</span>onTag (tag, html, options)](#apidoc.element.xss.default.onTag)
- description and source-code
```javascript
function onTag(tag, html, options) {
  // do nothing
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.onTagAttr"></a>[function <span class="apidocSignatureSpan">xss.default.</span>onTagAttr (tag, name, value)](#apidoc.element.xss.default.onTagAttr)
- description and source-code
```javascript
function onTagAttr(tag, name, value) {
  // do nothing
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.safeAttrValue"></a>[function <span class="apidocSignatureSpan">xss.default.</span>safeAttrValue (tag, name, value, cssFilter)](#apidoc.element.xss.default.safeAttrValue)
- description and source-code
```javascript
function safeAttrValue(tag, name, value, cssFilter) {
  // 转换为友好的属性值，再做判断
  value = friendlyAttrValue(value);

  if (name === 'href' || name === 'src') {
    // 过滤 href 和 src 属性
    // 仅允许 http:// | https:// | mailto: | / | # 开头的地址
    value = _.trim(value);
    if (value === '#') return '#';
    if (!(value.substr(0, 7) === 'http://' ||
         value.substr(0, 8) === 'https://' ||
         value.substr(0, 7) === 'mailto:' ||
         value[0] === '#' ||
         value[0] === '/')) {
      return '';
    }
  } else if (name === 'background') {
    // 过滤 background 属性 （这个xss漏洞较老了，可能已经不适用）
    // javascript:
    REGEXP_DEFAULT_ON_TAG_ATTR_4.lastIndex = 0;
    if (REGEXP_DEFAULT_ON_TAG_ATTR_4.test(value)) {
      return '';
    }
  } else if (name === 'style') {
    //<span class="apidocCodeCommentSpan"> /*注释*/
</span>    /*REGEXP_DEFAULT_ON_TAG_ATTR_3.lastIndex = 0;
    if (REGEXP_DEFAULT_ON_TAG_ATTR_3.test(value)) {
      return '';
    }*/
    // expression()
    REGEXP_DEFAULT_ON_TAG_ATTR_7.lastIndex = 0;
    if (REGEXP_DEFAULT_ON_TAG_ATTR_7.test(value)) {
      return '';
    }
    // url()
    REGEXP_DEFAULT_ON_TAG_ATTR_8.lastIndex = 0;
    if (REGEXP_DEFAULT_ON_TAG_ATTR_8.test(value)) {
      REGEXP_DEFAULT_ON_TAG_ATTR_4.lastIndex = 0;
      if (REGEXP_DEFAULT_ON_TAG_ATTR_4.test(value)) {
        return '';
      }
    }
    if (cssFilter !== false) {
      cssFilter = cssFilter || defaultCSSFilter;
      value = cssFilter.process(value);
    }
  }

  // 输出时需要转义<>"
  value = escapeAttrValue(value);
  return value;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.stripBlankChar"></a>[function <span class="apidocSignatureSpan">xss.default.</span>stripBlankChar (html)](#apidoc.element.xss.default.stripBlankChar)
- description and source-code
```javascript
function stripBlankChar(html) {
  var chars = html.split('');
  chars = chars.filter(function (char) {
    var c = char.charCodeAt(0);
    if (c === 127) return false;
    if (c <= 31) {
      if (c === 10 || c === 13) return true;
      return false;
    }
    return true;
  });
  return chars.join('');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.stripCommentTag"></a>[function <span class="apidocSignatureSpan">xss.default.</span>stripCommentTag (html)](#apidoc.element.xss.default.stripCommentTag)
- description and source-code
```javascript
function stripCommentTag(html) {
  return html.replace(STRIP_COMMENT_TAG_REGEXP, '');
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.default.unescapeQuote"></a>[function <span class="apidocSignatureSpan">xss.default.</span>unescapeQuote (str)](#apidoc.element.xss.default.unescapeQuote)
- description and source-code
```javascript
function unescapeQuote(str) {
  return str.replace(REGEXP_QUOTE_2, '"');
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.xss.parser"></a>[module xss.parser](#apidoc.module.xss.parser)

#### <a name="apidoc.element.xss.parser.parseAttr"></a>[function <span class="apidocSignatureSpan">xss.parser.</span>parseAttr (html, onAttr)](#apidoc.element.xss.parser.parseAttr)
- description and source-code
```javascript
function parseAttr(html, onAttr) {
  'user strict';

  var lastPos = 0;        // 当前位置
  var retAttrs = [];      // 待返回的属性列表
  var tmpName = false;    // 临时属性名称
  var len = html.length;  // HTML代码长度

  function addAttr (name, value) {
    name = _.trim(name);
    name = name.replace(REGEXP_ATTR_NAME, '').toLowerCase();
    if (name.length < 1) return;
    var ret = onAttr(name, value || '');
    if (ret) retAttrs.push(ret);
  };

  // 逐个分析字符
  for (var i = 0; i < len; i++) {
    var c = html.charAt(i);
    var v, j;
    if (tmpName === false && c === '=') {
      tmpName = html.slice(lastPos, i);
      lastPos = i + 1;
      continue;
    }
    if (tmpName !== false) {
      // HTML标签内的引号仅当前一个字符是等于号时才有效
      if (i === lastPos && (c === '"' || c === "'") && html.charAt(i - 1) === '=') {
        j = html.indexOf(c, i + 1);
        if (j === -1) {
          break;
        } else {
          v = _.trim(html.slice(lastPos + 1, j));
          addAttr(tmpName, v);
          tmpName = false;
          i = j;
          lastPos = i + 1;
          continue;
        }
      }
    }
    if (c === ' ') {
      if (tmpName === false) {
        j = findNextEqual(html, i);
        if (j === -1) {
          v = _.trim(html.slice(lastPos, i));
          addAttr(v);
          tmpName = false;
          lastPos = i + 1;
          continue;
        } else {
          i = j - 1;
          continue;
        }
      } else {
        j = findBeforeEqual(html, i - 1);
        if (j === -1) {
          v = _.trim(html.slice(lastPos, i));
          v = stripQuoteWrap(v);
          addAttr(tmpName, v);
          tmpName = false;
          lastPos = i + 1;
          continue;
        } else {
          continue;
        }
      }
    }
  }

  if (lastPos < html.length) {
    if (tmpName === false) {
      addAttr(html.slice(lastPos));
    } else {
      addAttr(tmpName, stripQuoteWrap(_.trim(html.slice(lastPos))));
    }
  }

  return _.trim(retAttrs.join(' '));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xss.parser.parseTag"></a>[function <span class="apidocSignatureSpan">xss.parser.</span>parseTag (html, onTag, escapeHtml)](#apidoc.element.xss.parser.parseTag)
- description and source-code
```javascript
function parseTag(html, onTag, escapeHtml) {
  'user strict';

  var rethtml = '';        // 待返回的HTML
  var lastPos = 0;         // 上一个标签结束位置
  var tagStart = false;    // 当前标签开始位置
  var quoteStart = false;  // 引号开始位置
  var currentPos = 0;      // 当前位置
  var len = html.length;   // HTML长度
  var currentHtml = '';    // 当前标签的HTML代码
  var currentTagName = ''; // 当前标签的名称

  // 逐个分析字符
  for (currentPos = 0; currentPos < len; currentPos++) {
    var c = html.charAt(currentPos);
    if (tagStart === false) {
      if (c === '<') {
        tagStart = currentPos;
        continue;
      }
    } else {
      if (quoteStart === false) {
        if (c === '<') {
          rethtml += escapeHtml(html.slice(lastPos, currentPos));
          tagStart = currentPos;
          lastPos = currentPos;
          continue;
        }
        if (c === '>') {
          rethtml += escapeHtml(html.slice(lastPos, tagStart));
          currentHtml = html.slice(tagStart, currentPos + 1);
          currentTagName = getTagName(currentHtml);
          rethtml += onTag(tagStart,
                           rethtml.length,
                           currentTagName,
                           currentHtml,
                           isClosing(currentHtml));
          lastPos = currentPos + 1;
          tagStart = false;
          continue;
        }
        // HTML标签内的引号仅当前一个字符是等于号时才有效
        if ((c === '"' || c === "'") && html.charAt(currentPos - 1) === '=') {
          quoteStart = c;
          continue;
        }
      } else {
        if (c === quoteStart) {
          quoteStart = false;
          continue;
        }
      }
    }
  }
  if (lastPos < html.length) {
    rethtml += escapeHtml(html.substr(lastPos));
  }

  return rethtml;
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.xss.util"></a>[module xss.util](#apidoc.module.xss.util)

#### <a name="apidoc.element.xss.util.forEach"></a>[function <span class="apidocSignatureSpan">xss.util.</span>forEach (arr, fn, scope)](#apidoc.element.xss.util.forEach)
- description and source-code
```javascript
forEach = function (arr, fn, scope) {
  var i, j;
  if (Array.prototype.forEach) {
    return arr.forEach(fn, scope);
  }
  for (i = 0, j = arr.length; i < j; i++) {
    fn.call(scope, arr[i], i, arr);
  }
}
```
- example usage
```shell
...
    } else {
      return next(tag, html, options);
    }
  },
  remove: function (html) {
    var rethtml = '';
    var lastPos = 0;
    _.forEach(removeList, function (pos) {
      rethtml += html.slice(lastPos, pos[0]);
      lastPos = pos[1];
    });
    rethtml += html.slice(lastPos);
    return rethtml;
  }
};
...
```

#### <a name="apidoc.element.xss.util.indexOf"></a>[function <span class="apidocSignatureSpan">xss.util.</span>indexOf (arr, item)](#apidoc.element.xss.util.indexOf)
- description and source-code
```javascript
indexOf = function (arr, item) {
  var i, j;
  if (Array.prototype.indexOf) {
    return arr.indexOf(item);
  }
  for (i = 0, j = arr.length; i < j; i++) {
    if (arr[i] === item) {
      return i;
    }
  }
  return -1;
}
```
- example usage
```shell
...
if (typeof(next) !== 'function') {
  next = function () {};
}

var isRemoveAllTag = !Array.isArray(tags);
function isRemoveTag (tag) {
  if (isRemoveAllTag) return true;
  return (_.indexOf(tags, tag) !== -1);
}

var removeList = [];   // 要删除的位置范围列表
var posStart = false;  // 当前标签开始位置

return {
  onIgnoreTag: function (tag, html, options) {
...
```

#### <a name="apidoc.element.xss.util.trim"></a>[function <span class="apidocSignatureSpan">xss.util.</span>trim (str)](#apidoc.element.xss.util.trim)
- description and source-code
```javascript
trim = function (str) {
  if (String.prototype.trim) {
    return str.trim();
  }
  return str.replace(/(^\s*)|(\s*$)/g, '');
}
```
- example usage
```shell
...
function safeAttrValue (tag, name, value, cssFilter) {
// 转换为友好的属性值，再做判断
value = friendlyAttrValue(value);

if (name === 'href' || name === 'src') {
  // 过滤 href 和 src 属性
  // 仅允许 http:// | https:// | mailto: | / | # 开头的地址
  value = _.trim(value);
  if (value === '#') return '#';
  if (!(value.substr(0, 7) === 'http://' ||
       value.substr(0, 8) === 'https://' ||
       value.substr(0, 7) === 'mailto:' ||
       value[0] === '#' ||
       value[0] === '/')) {
    return '';
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
