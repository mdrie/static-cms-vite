# Minimal project to test Static CMS with local git and vite

## Issues

### Dependency Conflicts, Deprecated Packages, and Vulnerabilities

```log
$ npm install
npm WARN ERESOLVE overriding peer dependency
npm WARN While resolving: @mui/system@5.4.1
npm WARN Found: react@18.2.0
npm WARN node_modules/react
npm WARN   react@"18.2.0" from @staticcms/core@1.0.0-beta2
npm WARN   node_modules/@staticcms/core
npm WARN     @staticcms/core@"^1.0.0-beta2" from the root project
npm WARN   25 more (@emotion/react, @emotion/styled, @mui/icons-material, ...)
npm WARN 
npm WARN Could not resolve dependency:
npm WARN peer react@"^17.0.0" from @mui/system@5.4.1
npm WARN node_modules/@mui/system
npm WARN   @mui/system@"5.4.1" from @staticcms/core@1.0.0-beta2
npm WARN   node_modules/@staticcms/core
npm WARN   1 more (@mui/x-date-pickers)
npm WARN
npm WARN Conflicting peer dependency: react@17.0.2
npm WARN node_modules/react
npm WARN   peer react@"^17.0.0" from @mui/system@5.4.1
npm WARN   node_modules/@mui/system
npm WARN     @mui/system@"5.4.1" from @staticcms/core@1.0.0-beta2
npm WARN     node_modules/@staticcms/core
npm WARN     1 more (@mui/x-date-pickers)
npm WARN ERESOLVE overriding peer dependency
npm WARN While resolving: @toast-ui/react-editor@3.2.2
npm WARN Found: react@18.2.0
npm WARN node_modules/react
npm WARN   react@"18.2.0" from @staticcms/core@1.0.0-beta2
npm WARN   node_modules/@staticcms/core
npm WARN     @staticcms/core@"^1.0.0-beta2" from the root project
npm WARN   25 more (@emotion/react, @emotion/styled, @mui/icons-material, ...)
npm WARN
npm WARN Could not resolve dependency:
npm WARN peer react@"^17.0.1" from @toast-ui/react-editor@3.2.2
npm WARN node_modules/@toast-ui/react-editor
npm WARN   @toast-ui/react-editor@"3.2.2" from @staticcms/core@1.0.0-beta2
npm WARN   node_modules/@staticcms/core
npm WARN
npm WARN Conflicting peer dependency: react@17.0.2
npm WARN node_modules/react
npm WARN   peer react@"^17.0.1" from @toast-ui/react-editor@3.2.2
npm WARN   node_modules/@toast-ui/react-editor
npm WARN     @toast-ui/react-editor@"3.2.2" from @staticcms/core@1.0.0-beta2
npm WARN     node_modules/@staticcms/core
npm WARN ERESOLVE overriding peer dependency
npm WARN While resolving: react-codemirror2@7.2.1
npm WARN Found: react@18.2.0
npm WARN node_modules/react
npm WARN   react@"18.2.0" from @staticcms/core@1.0.0-beta2
npm WARN   node_modules/@staticcms/core
npm WARN     @staticcms/core@"^1.0.0-beta2" from the root project
npm WARN   25 more (@emotion/react, @emotion/styled, @mui/icons-material, ...)
npm WARN
npm WARN Could not resolve dependency:
npm WARN peer react@">=15.5 <=16.x" from react-codemirror2@7.2.1
npm WARN node_modules/react-codemirror2
npm WARN   react-codemirror2@"7.2.1" from @staticcms/core@1.0.0-beta2
npm WARN   node_modules/@staticcms/core
npm WARN
npm WARN Conflicting peer dependency: react@16.14.0
npm WARN node_modules/react
npm WARN   peer react@">=15.5 <=16.x" from react-codemirror2@7.2.1
npm WARN   node_modules/react-codemirror2
npm WARN     react-codemirror2@"7.2.1" from @staticcms/core@1.0.0-beta2
npm WARN     node_modules/@staticcms/core
npm WARN deprecated querystring@0.2.0: The querystring API is considered Legacy. new code should use the URLSearchParams API instead.
npm WARN deprecated uuid@3.4.0: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm WARN deprecated @ltd/j-toml@1.35.2: => v1.35.3

added 638 packages, and audited 639 packages in 5m

105 packages are looking for funding
  run `npm fund` for details

2 high severity vulnerabilities
[...]
$ npm audit
# npm audit report

minimatch  <3.0.5
Severity: high
minimatch ReDoS vulnerability - https://github.com/advisories/GHSA-f8q6-p94x-37v3
No fix available
node_modules/minimatch
  @staticcms/core  *
  Depends on vulnerable versions of minimatch
  node_modules/@staticcms/core

2 high severity vulnerabilities

Some issues need review, and may require choosing
a different dependency.
```

### Running locally with vite does not work

```log
$ npm run cms:serve

> cms:serve        
> vite public/admin


  VITE v3.2.4  ready in 332 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
X [ERROR] Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)

    node_modules/@staticcms/core/dist/static-cms-core.js:204:6009:
      204 │ ...);const t="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=t&&t<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372...
          ╵                                                                                ~~~~~~~~~~~~~~~~~~~~

X [ERROR] Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)

    node_modules/@staticcms/core/dist/static-cms-core.js:204:6037:
      204 │ ...eplace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=t&&t<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,37...
          ╵                                                                                ~~~~~~~~~~~~~~~~~~~~

X [ERROR] Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)

    node_modules/@staticcms/core/dist/static-cms-core.js:204:6597:
      204 │ ...t;const n="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=n&&n<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372...
          ╵                                                                                ~~~~~~~~~~~~~~~~~~~~

X [ERROR] Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)

    node_modules/@staticcms/core/dist/static-cms-core.js:204:6625:
      204 │ ...eplace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=n&&n<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,37... 
          ╵                                                                                ~~~~~~~~~~~~~~~~~~~~

C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:1574
  let error = new Error(`${text}${summary}`);
              ^

Error: Build failed with 4 errors:
node_modules/@staticcms/core/dist/static-cms-core.js:204:6009: ERROR: Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)
node_modules/@staticcms/core/dist/static-cms-core.js:204:6037: ERROR: Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)
node_modules/@staticcms/core/dist/static-cms-core.js:204:6597: ERROR: Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)
node_modules/@staticcms/core/dist/static-cms-core.js:204:6625: ERROR: Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)
    at failureErrorWithLog (C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:1574:15)
    at C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:1032:28
    at runOnEndCallbacks (C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:1446:61)
    at buildResponseToResult (C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:1030:7)
    at C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:1142:14
    at responseCallbacks.<computed> (C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:679:9)
    at handleIncomingPacket (C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:734:9)
    at Socket.readFromStdout (C:\Users\[somedir]\static-cms-vite\node_modules\esbuild\lib\main.js:655:7)
    at Socket.emit (node:events:513:28)
    at addChunk (node:internal/streams/readable:324:12) {
  errors: [
    {
      detail: undefined,
      id: '',
      location: {
        column: 6009,
        file: 'node_modules/@staticcms/core/dist/static-cms-core.js',
        length: 20,
        line: 204,
        lineText: '\t$`.valueOf(),Zo=/[ t]/,Ho=/[-T:.]/g,Uo=/\\.?0+$/,Yo=/\\.(\\d*?)0+$/,Wo=(e,t)=>t,qo=(()=>{const e=function(){return this},t=Tn(null);{const e=Tn(null);for(const n of In(ko.prototype))"constructor"===n||"toJSON"===n||(t[n]=e)}return e.prototype=Co(Ct(ko.prototype,t)),Tt(e)})(),Vo=e=>e.replace(Yo,Wo).replace(Ho,""),$o=/./gs,Go=e=>"          "[e],Ko=e=>{if(e.startsWith("02-29",5)){const t=+e.slice(0,4);return!(3&t||!(t%100)&&(t%400||!(t%3200)))}return!0},{test:Xo}=fn.s`^.....(?:06.30|12.31).23:59:59`.valueOf(),Jo=Eo(new ko(0),Mo(ko.prototype)),Qo=uo("OffsetDateTime_ISOString"),ea=uo("OffsetDateTime_value"),ta=(e,t=0)=>(Jo.setTime(+e[ea]+t),Jo),na=To(class extends qo{[Qo];[ea];valueOf(){return this[ea]}toISOString(){return this[Qo]}constructor(e){Ko(e)||_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at ")));const t=e.startsWith("60",17);let n=t?e.slice(0,17)+"59"+e.slice(19):e;const{1:r}=(Mi?No(n):jo(n))??_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at "))),i=So(n=n.replace(Zo,"T").replace("z","Z"));return t&&(Jo.setTime(i),Xo(Jo.toISOString())||_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at ")))),super(),this[Qo]=n,this[ea]=((e,t)=>e<0?(""+(e+6216730554e4)).replace($o,Go).padStart(14," ")+t.replace($o,Go)+e:t?(e+".").padStart(16,"0")+t:(""+e).padStart(15,"0"))(i,r),this}getUTCFullYear(){return ta(this).getUTCFullYear()}getUTCMonth(){return ta(this).getUTCMonth()}getUTCDate(){return ta(this).getUTCDate()}getUTCHours(){return ta(this).getUTCHours()}getUTCMinutes(){return ta(this).getUTCMinutes()}getUTCSeconds(){return ta(this).getUTCSeconds()}getUTCMilliseconds(){return ta(this).getUTCMilliseconds()}getUTCDay(){return ta(this).getUTCDay()}getTimezoneOffset(){const e=Io(this[Qo]);return e?60*+e[1]+ +(e[2]+e[3]):0}getTime(){return Zt(+this[ea])}}),ra=uo("LocalDateTime_ISOString"),ia=uo("LocalDateTime_value"),oa=(e,t,n)=>+e[ra].slice(t,n),aa=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ia]=Vo(e[ra]=e[ra].slice(0,t)+i.padStart(o,"0")+e[ra].slice(n))},sa=To(class extends qo{[ra];[ia];valueOf(){return this[ia]}toISOString(){return this[ra]}constructor(e){return Fo(e)&&Ko(e)||_r(yt(`Invalid Local Date-Time ${e}`+Cr(" at "))),super(),this[ia]=Vo(this[ra]=e.replace(Zo,"T")),this}getFullYear(){return oa(this,0,4)}setFullYear(e){aa(this,0,4,e)}getMonth(){return oa(this,5,7)-1}setMonth(e){aa(this,5,7,e+1)}getDate(){return oa(this,8,10)}setDate(e){aa(this,8,10,e)}getHours(){return oa(this,11,13)}setHours(e){aa(this,11,13,e)}getMinutes(){return oa(this,14,16)}setMinutes(e){aa(this,14,16,e)}getSeconds(){return oa(this,17,19)}setSeconds(e){aa(this,17,19,e)}getMilliseconds(){return+this[ia].slice(14,17).padEnd(3,"0")}setMilliseconds(e){this[ia]=Vo(this[ra]=this[ra].slice(0,19)+(e?("."+(""+e).padStart(3,"0")).replace(Uo,""):""))}}),la=uo("LocalDate_ISOString"),ca=uo("LocalDate_value"),ua=(e,t,n)=>+e[la].slice(t,n),da=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ca]=Vo(e[la]=e[la].slice(0,t)+i.padStart(o,"0")+e[la].slice(n))},pa=To(class extends qo{[la];[ca];valueOf(){return this[ca]}toISOString(){return this[la]}constructor(e){return zo(e)&&Ko(e)||_r(yt(`Invalid Local Date ${e}`+Cr(" at "))),super(),this[ca]=Vo(this[la]=e),this}getFullYear(){return ua(this,0,4)}setFullYear(e){da(this,0,4,e)}getMonth(){return ua(this,5,7)-1}setMonth(e){da(this,5,7,e+1)}getDate(){return ua(this,8,10)}setDate(e){da(this,8,10,e)}}),fa=uo("LocalTime_ISOString"),ha=uo("LocalTime_value"),ma=(e,t,n)=>+e[fa].slice(t,n),ga=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ha]=Vo(e[fa]=e[fa].slice(0,t)+i.padStart(2,"0")+e[fa].slice(n))},va=To(class extends qo{[fa];[ha];valueOf(){return this[ha]}toISOString(){return this[fa]}constructor(e){return Bo(e)||_r(yt(`Invalid Local Time ${e}`+Cr(" at "))),super(),this[ha]=Vo(this[fa]=e),this}getHours(){return ma(this,0,2)}setHours(e){ga(this,0,2,e)}getMinutes(){return ma(this,3,5)}setMinutes(e){ga(this,3,5,e)}getSeconds(){return ma(this,6,8)}setSeconds(e){ga(this,6,8,e)}getMilliseconds(){return+this[ha].slice(6,9).padEnd(3,"0")}setMilliseconds(e){this[ha]=Vo(this[fa]=this[fa].slice(0,8)+(e?("."+(""+e).padStart(3,"0")).replace(Uo,""):""))}}),ya=parseInt,ba=String.fromCodePoint,wa=/[^\\\\]+|\\\\(?:[\\\\"btnfr/]|u.{4}|U.{8})/gs,_a=/[^\\n\\\\]+|\\n|\\\\(?:[\\t ]*\\n[\\t\\n ]*|[\\\\"btnfr/]|u.{4}|U.{8})/gs,xa=e=>{if(!e)return"";const t=e.match(wa),{length:n}=t;let r=0;do{const e=t[r];if("\\\\"===e[0])switch(e[1]){case"\\\\":t[r]="\\\\";break;case\'"\':t[r]=\'"\';break;case"b":t[r]="\\b";break;case"t":t[r]="\\t";break;case"n":t[r]="\\n";break;case"f":t[r]="\\f";break;case"r":t[r]="\\r";break;case"u":const n=ya(e.slice(2),16);gi&&55295<n&&n<57344&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at "))),t[r]=Yt(n);break;case"U":const i=ya(e.slice(2),16);(gi&&55295<i&&i<57344||1114111<i)&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at "))),t[r]=ba(i);break;case"/":t[r]="/"}}while(++r!==n);return t.join("")},ka=(e,t,n)=>{if(!e)return"";const r=e.match(_a),{length:i}=r;let o=0;do{const e=r[o];if("\\n"===e)++n,r[o]=t;else if("\\\\"===e[0])switch(e[1]){case"\\n":case" ":case"\\t":for(let t=0;t=e.indexOf("\\n",t)+1;)++n;r[o]="";break;case"\\\\":r[o]="\\\\";break;case\'"\':r[o]=\'"\';break;case"b":r[o]="\\b";break;case"t":r[o]="\\t";break;case"n":r[o]="\\n";break;case"f":r[o]="\\f";break;case"r":r[o]="\\r";break;case"u":const t=ya(e.slice(2),16);gi&&55295<t&&t<57344&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at ",wr+n))),r[o]=Yt(t);break;case"U":const i=ya(e.slice(2),16);(gi&&55295<i&&i<57344||1114111<i)&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at ",wr+n))),r[o]=ba(i);break;case"/":r[o]="/"}}while(++o!==i);return r.join("")},Sa=BigInt,Ca=/[-+]?(?:0|[1-9][_\\d]*)/,{test:Ma}=fn`_(?!\\d)`.valueOf(),{test:Ea}=fn`^${Ca}$`.valueOf(),{test:Ta}=rn(/^0(?:x[\\dA-Fa-f][_\\dA-Fa-f]*|o[0-7][_0-7]*|b[01][_01]*)$/),{test:La}=fn`_(?![\\dA-Fa-f])`.valueOf(),Oa=/_/g,Pa=/_|^[-+]/g,Aa=e=>(Ea(e)||Ta(e))&&!La(e),Da=e=>{if(!0===bi)return(e=>{Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=t&&t<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807), not includes ${e}`+Cr(" meet at "))),t})(e);if(!1===bi)return(e=>{Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t=ya(e.replace(Oa,""));return Mt(t)||_r(bt(`Integer did not use BitInt must fit Number.isSafeInteger, not includes ${e}`+Cr(" meet at "))),t})(e);Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t=ya(e.replace(Oa,""));if(wi<=t&&t<=_i)return t;const n="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=n&&n<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807), not includes ${e}`+Cr(" meet at "))),n},Ra=isFinite,{test:Ia}=fn`',
        namespace: '',
        suggestion: ''
      },
      notes: [],
      pluginName: '',
      text: 'Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)'
    },
    {
      detail: undefined,
      id: '',
      location: {
        column: 6037,
        file: 'node_modules/@staticcms/core/dist/static-cms-core.js',
        length: 20,
        line: 204,
        lineText: '\t$`.valueOf(),Zo=/[ t]/,Ho=/[-T:.]/g,Uo=/\\.?0+$/,Yo=/\\.(\\d*?)0+$/,Wo=(e,t)=>t,qo=(()=>{const e=function(){return this},t=Tn(null);{const e=Tn(null);for(const n of In(ko.prototype))"constructor"===n||"toJSON"===n||(t[n]=e)}return e.prototype=Co(Ct(ko.prototype,t)),Tt(e)})(),Vo=e=>e.replace(Yo,Wo).replace(Ho,""),$o=/./gs,Go=e=>"          "[e],Ko=e=>{if(e.startsWith("02-29",5)){const t=+e.slice(0,4);return!(3&t||!(t%100)&&(t%400||!(t%3200)))}return!0},{test:Xo}=fn.s`^.....(?:06.30|12.31).23:59:59`.valueOf(),Jo=Eo(new ko(0),Mo(ko.prototype)),Qo=uo("OffsetDateTime_ISOString"),ea=uo("OffsetDateTime_value"),ta=(e,t=0)=>(Jo.setTime(+e[ea]+t),Jo),na=To(class extends qo{[Qo];[ea];valueOf(){return this[ea]}toISOString(){return this[Qo]}constructor(e){Ko(e)||_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at ")));const t=e.startsWith("60",17);let n=t?e.slice(0,17)+"59"+e.slice(19):e;const{1:r}=(Mi?No(n):jo(n))??_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at "))),i=So(n=n.replace(Zo,"T").replace("z","Z"));return t&&(Jo.setTime(i),Xo(Jo.toISOString())||_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at ")))),super(),this[Qo]=n,this[ea]=((e,t)=>e<0?(""+(e+6216730554e4)).replace($o,Go).padStart(14," ")+t.replace($o,Go)+e:t?(e+".").padStart(16,"0")+t:(""+e).padStart(15,"0"))(i,r),this}getUTCFullYear(){return ta(this).getUTCFullYear()}getUTCMonth(){return ta(this).getUTCMonth()}getUTCDate(){return ta(this).getUTCDate()}getUTCHours(){return ta(this).getUTCHours()}getUTCMinutes(){return ta(this).getUTCMinutes()}getUTCSeconds(){return ta(this).getUTCSeconds()}getUTCMilliseconds(){return ta(this).getUTCMilliseconds()}getUTCDay(){return ta(this).getUTCDay()}getTimezoneOffset(){const e=Io(this[Qo]);return e?60*+e[1]+ +(e[2]+e[3]):0}getTime(){return Zt(+this[ea])}}),ra=uo("LocalDateTime_ISOString"),ia=uo("LocalDateTime_value"),oa=(e,t,n)=>+e[ra].slice(t,n),aa=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ia]=Vo(e[ra]=e[ra].slice(0,t)+i.padStart(o,"0")+e[ra].slice(n))},sa=To(class extends qo{[ra];[ia];valueOf(){return this[ia]}toISOString(){return this[ra]}constructor(e){return Fo(e)&&Ko(e)||_r(yt(`Invalid Local Date-Time ${e}`+Cr(" at "))),super(),this[ia]=Vo(this[ra]=e.replace(Zo,"T")),this}getFullYear(){return oa(this,0,4)}setFullYear(e){aa(this,0,4,e)}getMonth(){return oa(this,5,7)-1}setMonth(e){aa(this,5,7,e+1)}getDate(){return oa(this,8,10)}setDate(e){aa(this,8,10,e)}getHours(){return oa(this,11,13)}setHours(e){aa(this,11,13,e)}getMinutes(){return oa(this,14,16)}setMinutes(e){aa(this,14,16,e)}getSeconds(){return oa(this,17,19)}setSeconds(e){aa(this,17,19,e)}getMilliseconds(){return+this[ia].slice(14,17).padEnd(3,"0")}setMilliseconds(e){this[ia]=Vo(this[ra]=this[ra].slice(0,19)+(e?("."+(""+e).padStart(3,"0")).replace(Uo,""):""))}}),la=uo("LocalDate_ISOString"),ca=uo("LocalDate_value"),ua=(e,t,n)=>+e[la].slice(t,n),da=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ca]=Vo(e[la]=e[la].slice(0,t)+i.padStart(o,"0")+e[la].slice(n))},pa=To(class extends qo{[la];[ca];valueOf(){return this[ca]}toISOString(){return this[la]}constructor(e){return zo(e)&&Ko(e)||_r(yt(`Invalid Local Date ${e}`+Cr(" at "))),super(),this[ca]=Vo(this[la]=e),this}getFullYear(){return ua(this,0,4)}setFullYear(e){da(this,0,4,e)}getMonth(){return ua(this,5,7)-1}setMonth(e){da(this,5,7,e+1)}getDate(){return ua(this,8,10)}setDate(e){da(this,8,10,e)}}),fa=uo("LocalTime_ISOString"),ha=uo("LocalTime_value"),ma=(e,t,n)=>+e[fa].slice(t,n),ga=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ha]=Vo(e[fa]=e[fa].slice(0,t)+i.padStart(2,"0")+e[fa].slice(n))},va=To(class extends qo{[fa];[ha];valueOf(){return this[ha]}toISOString(){return this[fa]}constructor(e){return Bo(e)||_r(yt(`Invalid Local Time ${e}`+Cr(" at "))),super(),this[ha]=Vo(this[fa]=e),this}getHours(){return ma(this,0,2)}setHours(e){ga(this,0,2,e)}getMinutes(){return ma(this,3,5)}setMinutes(e){ga(this,3,5,e)}getSeconds(){return ma(this,6,8)}setSeconds(e){ga(this,6,8,e)}getMilliseconds(){return+this[ha].slice(6,9).padEnd(3,"0")}setMilliseconds(e){this[ha]=Vo(this[fa]=this[fa].slice(0,8)+(e?("."+(""+e).padStart(3,"0")).replace(Uo,""):""))}}),ya=parseInt,ba=String.fromCodePoint,wa=/[^\\\\]+|\\\\(?:[\\\\"btnfr/]|u.{4}|U.{8})/gs,_a=/[^\\n\\\\]+|\\n|\\\\(?:[\\t ]*\\n[\\t\\n ]*|[\\\\"btnfr/]|u.{4}|U.{8})/gs,xa=e=>{if(!e)return"";const t=e.match(wa),{length:n}=t;let r=0;do{const e=t[r];if("\\\\"===e[0])switch(e[1]){case"\\\\":t[r]="\\\\";break;case\'"\':t[r]=\'"\';break;case"b":t[r]="\\b";break;case"t":t[r]="\\t";break;case"n":t[r]="\\n";break;case"f":t[r]="\\f";break;case"r":t[r]="\\r";break;case"u":const n=ya(e.slice(2),16);gi&&55295<n&&n<57344&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at "))),t[r]=Yt(n);break;case"U":const i=ya(e.slice(2),16);(gi&&55295<i&&i<57344||1114111<i)&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at "))),t[r]=ba(i);break;case"/":t[r]="/"}}while(++r!==n);return t.join("")},ka=(e,t,n)=>{if(!e)return"";const r=e.match(_a),{length:i}=r;let o=0;do{const e=r[o];if("\\n"===e)++n,r[o]=t;else if("\\\\"===e[0])switch(e[1]){case"\\n":case" ":case"\\t":for(let t=0;t=e.indexOf("\\n",t)+1;)++n;r[o]="";break;case"\\\\":r[o]="\\\\";break;case\'"\':r[o]=\'"\';break;case"b":r[o]="\\b";break;case"t":r[o]="\\t";break;case"n":r[o]="\\n";break;case"f":r[o]="\\f";break;case"r":r[o]="\\r";break;case"u":const t=ya(e.slice(2),16);gi&&55295<t&&t<57344&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at ",wr+n))),r[o]=Yt(t);break;case"U":const i=ya(e.slice(2),16);(gi&&55295<i&&i<57344||1114111<i)&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at ",wr+n))),r[o]=ba(i);break;case"/":r[o]="/"}}while(++o!==i);return r.join("")},Sa=BigInt,Ca=/[-+]?(?:0|[1-9][_\\d]*)/,{test:Ma}=fn`_(?!\\d)`.valueOf(),{test:Ea}=fn`^${Ca}$`.valueOf(),{test:Ta}=rn(/^0(?:x[\\dA-Fa-f][_\\dA-Fa-f]*|o[0-7][_0-7]*|b[01][_01]*)$/),{test:La}=fn`_(?![\\dA-Fa-f])`.valueOf(),Oa=/_/g,Pa=/_|^[-+]/g,Aa=e=>(Ea(e)||Ta(e))&&!La(e),Da=e=>{if(!0===bi)return(e=>{Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=t&&t<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807), not includes ${e}`+Cr(" meet at "))),t})(e);if(!1===bi)return(e=>{Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t=ya(e.replace(Oa,""));return Mt(t)||_r(bt(`Integer did not use BitInt must fit Number.isSafeInteger, not includes ${e}`+Cr(" meet at "))),t})(e);Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t=ya(e.replace(Oa,""));if(wi<=t&&t<=_i)return t;const n="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=n&&n<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807), not includes ${e}`+Cr(" meet at "))),n},Ra=isFinite,{test:Ia}=fn`',
        namespace: '',
        suggestion: ''
      },
      notes: [],
      pluginName: '',
      text: 'Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)'
    },
    {
      detail: undefined,
      id: '',
      location: {
        column: 6597,
        file: 'node_modules/@staticcms/core/dist/static-cms-core.js',
        length: 20,
        line: 204,
        lineText: '\t$`.valueOf(),Zo=/[ t]/,Ho=/[-T:.]/g,Uo=/\\.?0+$/,Yo=/\\.(\\d*?)0+$/,Wo=(e,t)=>t,qo=(()=>{const e=function(){return this},t=Tn(null);{const e=Tn(null);for(const n of In(ko.prototype))"constructor"===n||"toJSON"===n||(t[n]=e)}return e.prototype=Co(Ct(ko.prototype,t)),Tt(e)})(),Vo=e=>e.replace(Yo,Wo).replace(Ho,""),$o=/./gs,Go=e=>"          "[e],Ko=e=>{if(e.startsWith("02-29",5)){const t=+e.slice(0,4);return!(3&t||!(t%100)&&(t%400||!(t%3200)))}return!0},{test:Xo}=fn.s`^.....(?:06.30|12.31).23:59:59`.valueOf(),Jo=Eo(new ko(0),Mo(ko.prototype)),Qo=uo("OffsetDateTime_ISOString"),ea=uo("OffsetDateTime_value"),ta=(e,t=0)=>(Jo.setTime(+e[ea]+t),Jo),na=To(class extends qo{[Qo];[ea];valueOf(){return this[ea]}toISOString(){return this[Qo]}constructor(e){Ko(e)||_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at ")));const t=e.startsWith("60",17);let n=t?e.slice(0,17)+"59"+e.slice(19):e;const{1:r}=(Mi?No(n):jo(n))??_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at "))),i=So(n=n.replace(Zo,"T").replace("z","Z"));return t&&(Jo.setTime(i),Xo(Jo.toISOString())||_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at ")))),super(),this[Qo]=n,this[ea]=((e,t)=>e<0?(""+(e+6216730554e4)).replace($o,Go).padStart(14," ")+t.replace($o,Go)+e:t?(e+".").padStart(16,"0")+t:(""+e).padStart(15,"0"))(i,r),this}getUTCFullYear(){return ta(this).getUTCFullYear()}getUTCMonth(){return ta(this).getUTCMonth()}getUTCDate(){return ta(this).getUTCDate()}getUTCHours(){return ta(this).getUTCHours()}getUTCMinutes(){return ta(this).getUTCMinutes()}getUTCSeconds(){return ta(this).getUTCSeconds()}getUTCMilliseconds(){return ta(this).getUTCMilliseconds()}getUTCDay(){return ta(this).getUTCDay()}getTimezoneOffset(){const e=Io(this[Qo]);return e?60*+e[1]+ +(e[2]+e[3]):0}getTime(){return Zt(+this[ea])}}),ra=uo("LocalDateTime_ISOString"),ia=uo("LocalDateTime_value"),oa=(e,t,n)=>+e[ra].slice(t,n),aa=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ia]=Vo(e[ra]=e[ra].slice(0,t)+i.padStart(o,"0")+e[ra].slice(n))},sa=To(class extends qo{[ra];[ia];valueOf(){return this[ia]}toISOString(){return this[ra]}constructor(e){return Fo(e)&&Ko(e)||_r(yt(`Invalid Local Date-Time ${e}`+Cr(" at "))),super(),this[ia]=Vo(this[ra]=e.replace(Zo,"T")),this}getFullYear(){return oa(this,0,4)}setFullYear(e){aa(this,0,4,e)}getMonth(){return oa(this,5,7)-1}setMonth(e){aa(this,5,7,e+1)}getDate(){return oa(this,8,10)}setDate(e){aa(this,8,10,e)}getHours(){return oa(this,11,13)}setHours(e){aa(this,11,13,e)}getMinutes(){return oa(this,14,16)}setMinutes(e){aa(this,14,16,e)}getSeconds(){return oa(this,17,19)}setSeconds(e){aa(this,17,19,e)}getMilliseconds(){return+this[ia].slice(14,17).padEnd(3,"0")}setMilliseconds(e){this[ia]=Vo(this[ra]=this[ra].slice(0,19)+(e?("."+(""+e).padStart(3,"0")).replace(Uo,""):""))}}),la=uo("LocalDate_ISOString"),ca=uo("LocalDate_value"),ua=(e,t,n)=>+e[la].slice(t,n),da=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ca]=Vo(e[la]=e[la].slice(0,t)+i.padStart(o,"0")+e[la].slice(n))},pa=To(class extends qo{[la];[ca];valueOf(){return this[ca]}toISOString(){return this[la]}constructor(e){return zo(e)&&Ko(e)||_r(yt(`Invalid Local Date ${e}`+Cr(" at "))),super(),this[ca]=Vo(this[la]=e),this}getFullYear(){return ua(this,0,4)}setFullYear(e){da(this,0,4,e)}getMonth(){return ua(this,5,7)-1}setMonth(e){da(this,5,7,e+1)}getDate(){return ua(this,8,10)}setDate(e){da(this,8,10,e)}}),fa=uo("LocalTime_ISOString"),ha=uo("LocalTime_value"),ma=(e,t,n)=>+e[fa].slice(t,n),ga=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ha]=Vo(e[fa]=e[fa].slice(0,t)+i.padStart(2,"0")+e[fa].slice(n))},va=To(class extends qo{[fa];[ha];valueOf(){return this[ha]}toISOString(){return this[fa]}constructor(e){return Bo(e)||_r(yt(`Invalid Local Time ${e}`+Cr(" at "))),super(),this[ha]=Vo(this[fa]=e),this}getHours(){return ma(this,0,2)}setHours(e){ga(this,0,2,e)}getMinutes(){return ma(this,3,5)}setMinutes(e){ga(this,3,5,e)}getSeconds(){return ma(this,6,8)}setSeconds(e){ga(this,6,8,e)}getMilliseconds(){return+this[ha].slice(6,9).padEnd(3,"0")}setMilliseconds(e){this[ha]=Vo(this[fa]=this[fa].slice(0,8)+(e?("."+(""+e).padStart(3,"0")).replace(Uo,""):""))}}),ya=parseInt,ba=String.fromCodePoint,wa=/[^\\\\]+|\\\\(?:[\\\\"btnfr/]|u.{4}|U.{8})/gs,_a=/[^\\n\\\\]+|\\n|\\\\(?:[\\t ]*\\n[\\t\\n ]*|[\\\\"btnfr/]|u.{4}|U.{8})/gs,xa=e=>{if(!e)return"";const t=e.match(wa),{length:n}=t;let r=0;do{const e=t[r];if("\\\\"===e[0])switch(e[1]){case"\\\\":t[r]="\\\\";break;case\'"\':t[r]=\'"\';break;case"b":t[r]="\\b";break;case"t":t[r]="\\t";break;case"n":t[r]="\\n";break;case"f":t[r]="\\f";break;case"r":t[r]="\\r";break;case"u":const n=ya(e.slice(2),16);gi&&55295<n&&n<57344&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at "))),t[r]=Yt(n);break;case"U":const i=ya(e.slice(2),16);(gi&&55295<i&&i<57344||1114111<i)&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at "))),t[r]=ba(i);break;case"/":t[r]="/"}}while(++r!==n);return t.join("")},ka=(e,t,n)=>{if(!e)return"";const r=e.match(_a),{length:i}=r;let o=0;do{const e=r[o];if("\\n"===e)++n,r[o]=t;else if("\\\\"===e[0])switch(e[1]){case"\\n":case" ":case"\\t":for(let t=0;t=e.indexOf("\\n",t)+1;)++n;r[o]="";break;case"\\\\":r[o]="\\\\";break;case\'"\':r[o]=\'"\';break;case"b":r[o]="\\b";break;case"t":r[o]="\\t";break;case"n":r[o]="\\n";break;case"f":r[o]="\\f";break;case"r":r[o]="\\r";break;case"u":const t=ya(e.slice(2),16);gi&&55295<t&&t<57344&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at ",wr+n))),r[o]=Yt(t);break;case"U":const i=ya(e.slice(2),16);(gi&&55295<i&&i<57344||1114111<i)&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at ",wr+n))),r[o]=ba(i);break;case"/":r[o]="/"}}while(++o!==i);return r.join("")},Sa=BigInt,Ca=/[-+]?(?:0|[1-9][_\\d]*)/,{test:Ma}=fn`_(?!\\d)`.valueOf(),{test:Ea}=fn`^${Ca}$`.valueOf(),{test:Ta}=rn(/^0(?:x[\\dA-Fa-f][_\\dA-Fa-f]*|o[0-7][_0-7]*|b[01][_01]*)$/),{test:La}=fn`_(?![\\dA-Fa-f])`.valueOf(),Oa=/_/g,Pa=/_|^[-+]/g,Aa=e=>(Ea(e)||Ta(e))&&!La(e),Da=e=>{if(!0===bi)return(e=>{Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=t&&t<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807), not includes ${e}`+Cr(" meet at "))),t})(e);if(!1===bi)return(e=>{Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t=ya(e.replace(Oa,""));return Mt(t)||_r(bt(`Integer did not use BitInt must fit Number.isSafeInteger, not includes ${e}`+Cr(" meet at "))),t})(e);Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t=ya(e.replace(Oa,""));if(wi<=t&&t<=_i)return t;const n="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=n&&n<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807), not includes ${e}`+Cr(" meet at "))),n},Ra=isFinite,{test:Ia}=fn`',
        namespace: '',
        suggestion: ''
      },
      notes: [],
      pluginName: '',
      text: 'Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)'
    },
    {
      detail: undefined,
      id: '',
      location: {
        column: 6625,
        file: 'node_modules/@staticcms/core/dist/static-cms-core.js',
        length: 20,
        line: 204,
        lineText: '\t$`.valueOf(),Zo=/[ t]/,Ho=/[-T:.]/g,Uo=/\\.?0+$/,Yo=/\\.(\\d*?)0+$/,Wo=(e,t)=>t,qo=(()=>{const e=function(){return this},t=Tn(null);{const e=Tn(null);for(const n of In(ko.prototype))"constructor"===n||"toJSON"===n||(t[n]=e)}return e.prototype=Co(Ct(ko.prototype,t)),Tt(e)})(),Vo=e=>e.replace(Yo,Wo).replace(Ho,""),$o=/./gs,Go=e=>"          "[e],Ko=e=>{if(e.startsWith("02-29",5)){const t=+e.slice(0,4);return!(3&t||!(t%100)&&(t%400||!(t%3200)))}return!0},{test:Xo}=fn.s`^.....(?:06.30|12.31).23:59:59`.valueOf(),Jo=Eo(new ko(0),Mo(ko.prototype)),Qo=uo("OffsetDateTime_ISOString"),ea=uo("OffsetDateTime_value"),ta=(e,t=0)=>(Jo.setTime(+e[ea]+t),Jo),na=To(class extends qo{[Qo];[ea];valueOf(){return this[ea]}toISOString(){return this[Qo]}constructor(e){Ko(e)||_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at ")));const t=e.startsWith("60",17);let n=t?e.slice(0,17)+"59"+e.slice(19):e;const{1:r}=(Mi?No(n):jo(n))??_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at "))),i=So(n=n.replace(Zo,"T").replace("z","Z"));return t&&(Jo.setTime(i),Xo(Jo.toISOString())||_r(yt(`Invalid Offset Date-Time ${e}`+Cr(" at ")))),super(),this[Qo]=n,this[ea]=((e,t)=>e<0?(""+(e+6216730554e4)).replace($o,Go).padStart(14," ")+t.replace($o,Go)+e:t?(e+".").padStart(16,"0")+t:(""+e).padStart(15,"0"))(i,r),this}getUTCFullYear(){return ta(this).getUTCFullYear()}getUTCMonth(){return ta(this).getUTCMonth()}getUTCDate(){return ta(this).getUTCDate()}getUTCHours(){return ta(this).getUTCHours()}getUTCMinutes(){return ta(this).getUTCMinutes()}getUTCSeconds(){return ta(this).getUTCSeconds()}getUTCMilliseconds(){return ta(this).getUTCMilliseconds()}getUTCDay(){return ta(this).getUTCDay()}getTimezoneOffset(){const e=Io(this[Qo]);return e?60*+e[1]+ +(e[2]+e[3]):0}getTime(){return Zt(+this[ea])}}),ra=uo("LocalDateTime_ISOString"),ia=uo("LocalDateTime_value"),oa=(e,t,n)=>+e[ra].slice(t,n),aa=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ia]=Vo(e[ra]=e[ra].slice(0,t)+i.padStart(o,"0")+e[ra].slice(n))},sa=To(class extends qo{[ra];[ia];valueOf(){return this[ia]}toISOString(){return this[ra]}constructor(e){return Fo(e)&&Ko(e)||_r(yt(`Invalid Local Date-Time ${e}`+Cr(" at "))),super(),this[ia]=Vo(this[ra]=e.replace(Zo,"T")),this}getFullYear(){return oa(this,0,4)}setFullYear(e){aa(this,0,4,e)}getMonth(){return oa(this,5,7)-1}setMonth(e){aa(this,5,7,e+1)}getDate(){return oa(this,8,10)}setDate(e){aa(this,8,10,e)}getHours(){return oa(this,11,13)}setHours(e){aa(this,11,13,e)}getMinutes(){return oa(this,14,16)}setMinutes(e){aa(this,14,16,e)}getSeconds(){return oa(this,17,19)}setSeconds(e){aa(this,17,19,e)}getMilliseconds(){return+this[ia].slice(14,17).padEnd(3,"0")}setMilliseconds(e){this[ia]=Vo(this[ra]=this[ra].slice(0,19)+(e?("."+(""+e).padStart(3,"0")).replace(Uo,""):""))}}),la=uo("LocalDate_ISOString"),ca=uo("LocalDate_value"),ua=(e,t,n)=>+e[la].slice(t,n),da=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ca]=Vo(e[la]=e[la].slice(0,t)+i.padStart(o,"0")+e[la].slice(n))},pa=To(class extends qo{[la];[ca];valueOf(){return this[ca]}toISOString(){return this[la]}constructor(e){return zo(e)&&Ko(e)||_r(yt(`Invalid Local Date ${e}`+Cr(" at "))),super(),this[ca]=Vo(this[la]=e),this}getFullYear(){return ua(this,0,4)}setFullYear(e){da(this,0,4,e)}getMonth(){return ua(this,5,7)-1}setMonth(e){da(this,5,7,e+1)}getDate(){return ua(this,8,10)}setDate(e){da(this,8,10,e)}}),fa=uo("LocalTime_ISOString"),ha=uo("LocalTime_value"),ma=(e,t,n)=>+e[fa].slice(t,n),ga=(e,t,n,r)=>{const i=""+r,o=n-t;if(i.length>o)throw bt();e[ha]=Vo(e[fa]=e[fa].slice(0,t)+i.padStart(2,"0")+e[fa].slice(n))},va=To(class extends qo{[fa];[ha];valueOf(){return this[ha]}toISOString(){return this[fa]}constructor(e){return Bo(e)||_r(yt(`Invalid Local Time ${e}`+Cr(" at "))),super(),this[ha]=Vo(this[fa]=e),this}getHours(){return ma(this,0,2)}setHours(e){ga(this,0,2,e)}getMinutes(){return ma(this,3,5)}setMinutes(e){ga(this,3,5,e)}getSeconds(){return ma(this,6,8)}setSeconds(e){ga(this,6,8,e)}getMilliseconds(){return+this[ha].slice(6,9).padEnd(3,"0")}setMilliseconds(e){this[ha]=Vo(this[fa]=this[fa].slice(0,8)+(e?("."+(""+e).padStart(3,"0")).replace(Uo,""):""))}}),ya=parseInt,ba=String.fromCodePoint,wa=/[^\\\\]+|\\\\(?:[\\\\"btnfr/]|u.{4}|U.{8})/gs,_a=/[^\\n\\\\]+|\\n|\\\\(?:[\\t ]*\\n[\\t\\n ]*|[\\\\"btnfr/]|u.{4}|U.{8})/gs,xa=e=>{if(!e)return"";const t=e.match(wa),{length:n}=t;let r=0;do{const e=t[r];if("\\\\"===e[0])switch(e[1]){case"\\\\":t[r]="\\\\";break;case\'"\':t[r]=\'"\';break;case"b":t[r]="\\b";break;case"t":t[r]="\\t";break;case"n":t[r]="\\n";break;case"f":t[r]="\\f";break;case"r":t[r]="\\r";break;case"u":const n=ya(e.slice(2),16);gi&&55295<n&&n<57344&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at "))),t[r]=Yt(n);break;case"U":const i=ya(e.slice(2),16);(gi&&55295<i&&i<57344||1114111<i)&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at "))),t[r]=ba(i);break;case"/":t[r]="/"}}while(++r!==n);return t.join("")},ka=(e,t,n)=>{if(!e)return"";const r=e.match(_a),{length:i}=r;let o=0;do{const e=r[o];if("\\n"===e)++n,r[o]=t;else if("\\\\"===e[0])switch(e[1]){case"\\n":case" ":case"\\t":for(let t=0;t=e.indexOf("\\n",t)+1;)++n;r[o]="";break;case"\\\\":r[o]="\\\\";break;case\'"\':r[o]=\'"\';break;case"b":r[o]="\\b";break;case"t":r[o]="\\t";break;case"n":r[o]="\\n";break;case"f":r[o]="\\f";break;case"r":r[o]="\\r";break;case"u":const t=ya(e.slice(2),16);gi&&55295<t&&t<57344&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at ",wr+n))),r[o]=Yt(t);break;case"U":const i=ya(e.slice(2),16);(gi&&55295<i&&i<57344||1114111<i)&&_r(bt(`Invalid Unicode Scalar ${e}`+Cr(" at ",wr+n))),r[o]=ba(i);break;case"/":r[o]="/"}}while(++o!==i);return r.join("")},Sa=BigInt,Ca=/[-+]?(?:0|[1-9][_\\d]*)/,{test:Ma}=fn`_(?!\\d)`.valueOf(),{test:Ea}=fn`^${Ca}$`.valueOf(),{test:Ta}=rn(/^0(?:x[\\dA-Fa-f][_\\dA-Fa-f]*|o[0-7][_0-7]*|b[01][_01]*)$/),{test:La}=fn`_(?![\\dA-Fa-f])`.valueOf(),Oa=/_/g,Pa=/_|^[-+]/g,Aa=e=>(Ea(e)||Ta(e))&&!La(e),Da=e=>{if(!0===bi)return(e=>{Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=t&&t<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807), not includes ${e}`+Cr(" meet at "))),t})(e);if(!1===bi)return(e=>{Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t=ya(e.replace(Oa,""));return Mt(t)||_r(bt(`Integer did not use BitInt must fit Number.isSafeInteger, not includes ${e}`+Cr(" meet at "))),t})(e);Aa(e)||_r(yt(`Invalid Integer ${e}`+Cr(" at ")));const t=ya(e.replace(Oa,""));if(wi<=t&&t<=_i)return t;const n="-"===e[0]?-Sa(e.replace(Pa,"")):Sa(e.replace(Pa,""));return Di||-9223372036854775808n<=n&&n<=9223372036854775807n||_r(bt(`Integer expect 64 bit range (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807), not includes ${e}`+Cr(" meet at "))),n},Ra=isFinite,{test:Ia}=fn`',
        namespace: '',
        suggestion: ''
      },
      notes: [],
      pluginName: '',
      text: 'Big integer literals are not available in the configured target environment ("chrome87", "edge88", "es2020", "firefox78", "safari13" + 2 overrides)'
    }
  ],
  warnings: []
}

Node.js v18.9.0

 *  The terminal process "C:\Program Files\Git\bin\bash.exe '--login', '-c', 'npm run cms:serve'" terminated with exit code: 1. 
 *  Terminal will be reused by tasks, press any key to close it.
```
