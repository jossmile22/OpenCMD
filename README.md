<!DOCTYPE html>
<html lang="en">
  <head>
    <script type="module">
      import { createHotContext } from &#34;/@vite/client&#34;;
const hot = createHotContext(&#34;/__dummy__runtime-error-plugin&#34;);

function sendError(error) {
  if (!(error instanceof Error)) {
    error = new Error(&#34;(unknown runtime error)&#34;);
  }
  const serialized = {
    message: error.message,
    stack: error.stack,
  };
  hot.send(&#34;runtime-error-plugin:error&#34;, serialized);
}

// Only notify the parent frame after the server confirms the error passed
// the filter and the overlay will be shown.
hot.on(&#34;runtime-error-plugin:notify-parent&#34;, () =&gt; {
  try {
    window.parent.postMessage({ type: &#34;runtime-error&#34;, id: null }, &#34;*&#34;);
  } catch (_) {}
});

window.addEventListener(&#34;error&#34;, (evt) =&gt; {
  sendError(evt.error);
});

window.addEventListener(&#34;unhandledrejection&#34;, (evt) =&gt; {
  sendError(evt.reason);
});
    </script>
    <script type="module">
      import { injectIntoGlobalHook } from &#34;/@react-refresh&#34;;
injectIntoGlobalHook(window);
window.$RefreshReg$ = () =&gt; {};
window.$RefreshSig$ = () =&gt; (type) =&gt; type;
    </script>
    <script type="module" src="/@vite/client">
    </script>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1" />
    <title>
      OpenCmd
    </title>
    <link rel="icon" type="image/svg+xml" href="/favicon.svg" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="" />
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&amp;display=swap" rel="stylesheet" />
    <script type="module">
      &#34;use strict&#34;;(()=&gt;{var O=&#34;0.5.1&#34;;var v={HIGHLIGHT_COLOR:&#34;#0079F2&#34;,HIGHLIGHT_BG:&#34;#0079F210&#34;,ALLOWED_PARENT_DOMAINS:[&#34;.replit.dev&#34;,&#34;.replit.com&#34;,&#34;.replit-staging.com&#34;,&#34;.repl.co&#34;],THEME_PREVIEW_STYLE_ID:&#34;replit-theme-preview&#34;,MAX_SIBLING_HIGHLIGHTERS:1e3,MAX_DESCENDANTS_FOR_SCREENSHOT:1500},ie=`
  [contenteditable] {
    outline: none !important;
  }

  [contenteditable]:focus {
    outline: none !important;
  }
`,ne=`
  .beacon-highlighter {
    content: &#39;&#39;;
    position: absolute;
    z-index: ${Number.MAX_SAFE_INTEGER-3};
    box-sizing: border-box;
    pointer-events: none;
    outline: 2px dashed ${v.HIGHLIGHT_COLOR} !important;
    outline-offset: 0 !important;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;
    background: ${v.HIGHLIGHT_BG} !important;
    opacity: 0;
  }
  
  .beacon-hover-highlighter {
    position: fixed;
    z-index: ${Number.MAX_SAFE_INTEGER};
  }
  
  .beacon-selected-highlighter {
    position: fixed;
    pointer-events: none;
    outline: 2px solid ${v.HIGHLIGHT_COLOR} !important;
    outline-offset: 3px !important;
    background: none !important;
  }
  
  .beacon-label {
    position: absolute;
    background-color: ${v.HIGHLIGHT_COLOR};
    color: #FFFFFF;
    padding: 4px 8px;
    border-radius: 4px;
    font-size: 14px;
    font-family: monospace;
    line-height: 1;
    white-space: nowrap;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
    transform: translateY(-100%);
    margin-top: -4px;
    left: 0;
    z-index: ${Number.MAX_SAFE_INTEGER-2};
    pointer-events: none;
    opacity: 0;
  }
  
  .beacon-hover-label {
    position: fixed;
    z-index: ${Number.MAX_SAFE_INTEGER};
  }
  
  .beacon-selected-label {
    position: fixed;
    pointer-events: none;
  }
  
  .beacon-sibling-highlighter {
    position: fixed;
    pointer-events: none;
    outline: 2px dashed ${v.HIGHLIGHT_COLOR} !important;
    outline-offset: 0 !important;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;
    background: ${v.HIGHLIGHT_BG} !important;
  }
`;function Fe(e,i){return e[13]=1,e[14]=i&gt;&gt;8,e[15]=i&amp;255,e[16]=i&gt;&gt;8,e[17]=i&amp;255,e}var he=112,de=72,ue=89,ge=115,G;function Ue(){let e=new Int32Array(256);for(let i=0;i&lt;256;i++){let t=i;for(let n=0;n&lt;8;n++)t=t&amp;1?3988292384^t&gt;&gt;&gt;1:t&gt;&gt;&gt;1;e[i]=t}return e}function $e(e){let i=-1;G||(G=Ue());for(let t=0;t&lt;e.length;t++)i=G[(i^e[t])&amp;255]^i&gt;&gt;&gt;8;return i^-1}function We(e){let i=e.length-1;for(let t=i;t&gt;=4;t--)if(e[t-4]===9&amp;&amp;e[t-3]===he&amp;&amp;e[t-2]===de&amp;&amp;e[t-1]===ue&amp;&amp;e[t]===ge)return t-3;return 0}function Ge(e,i,t=!1){let n=new Uint8Array(13);i*=39.3701,n[0]=he,n[1]=de,n[2]=ue,n[3]=ge,n[4]=i&gt;&gt;&gt;24,n[5]=i&gt;&gt;&gt;16,n[6]=i&gt;&gt;&gt;8,n[7]=i&amp;255,n[8]=n[4],n[9]=n[5],n[10]=n[6],n[11]=n[7],n[12]=1;let r=$e(n),o=new Uint8Array(4);if(o[0]=r&gt;&gt;&gt;24,o[1]=r&gt;&gt;&gt;16,o[2]=r&gt;&gt;&gt;8,o[3]=r&amp;255,t){let l=We(e);return e.set(n,l),e.set(o,l+13),e}else{let l=new Uint8Array(4);l[0]=0,l[1]=0,l[2]=0,l[3]=9;let s=new Uint8Array(54);return s.set(e,0),s.set(l,33),s.set(n,37),s.set(o,50),s}}var me=&#34;[modern-screenshot]&#34;,C=typeof window&lt;&#34;u&#34;,Ve=C&amp;&amp;&#34;Worker&#34;in window,je=C&amp;&amp;&#34;atob&#34;in window,ii=C&amp;&amp;&#34;btoa&#34;in window,j=C?window.navigator?.userAgent:&#34;&#34;,fe=j.includes(&#34;Chrome&#34;),B=j.includes(&#34;AppleWebKit&#34;)&amp;&amp;!fe,z=j.includes(&#34;Firefox&#34;),ze=e=&gt;e&amp;&amp;&#34;__CONTEXT__&#34;in e,qe=e=&gt;e.constructor.name===&#34;CSSFontFaceRule&#34;,Xe=e=&gt;e.constructor.name===&#34;CSSImportRule&#34;,S=e=&gt;e.nodeType===1,_=e=&gt;typeof e.className==&#34;object&#34;,pe=e=&gt;e.tagName===&#34;image&#34;,Ye=e=&gt;e.tagName===&#34;use&#34;,R=e=&gt;S(e)&amp;&amp;typeof e.style&lt;&#34;u&#34;&amp;&amp;!_(e),Ke=e=&gt;e.nodeType===8,Je=e=&gt;e.nodeType===3,L=e=&gt;e.tagName===&#34;IMG&#34;,k=e=&gt;e.tagName===&#34;VIDEO&#34;,Qe=e=&gt;e.tagName===&#34;CANVAS&#34;,Ze=e=&gt;e.tagName===&#34;TEXTAREA&#34;,et=e=&gt;e.tagName===&#34;INPUT&#34;,tt=e=&gt;e.tagName===&#34;STYLE&#34;,it=e=&gt;e.tagName===&#34;SCRIPT&#34;,nt=e=&gt;e.tagName===&#34;SELECT&#34;,rt=e=&gt;e.tagName===&#34;SLOT&#34;,ot=e=&gt;e.tagName===&#34;IFRAME&#34;,st=(...e)=&gt;console.warn(me,...e);function lt(e){let i=e?.createElement?.(&#34;canvas&#34;);return i&amp;&amp;(i.height=i.width=1),!!i&amp;&amp;&#34;toDataURL&#34;in i&amp;&amp;!!i.toDataURL(&#34;image/webp&#34;).includes(&#34;image/webp&#34;)}var V=e=&gt;e.startsWith(&#34;data:&#34;);function be(e,i){if(e.match(/^[a-z]+:\/\//i))return e;if(C&amp;&amp;e.match(/^\/\//))return window.location.protocol+e;if(e.match(/^[a-z]+:/i)||!C)return e;let t=F().implementation.createHTMLDocument(),n=t.createElement(&#34;base&#34;),r=t.createElement(&#34;a&#34;);return t.head.appendChild(n),t.body.appendChild(r),i&amp;&amp;(n.href=i),r.href=e,r.href}function F(e){return(e&amp;&amp;S(e)?e?.ownerDocument:e)??window.document}var U=&#34;http://www.w3.org/2000/svg&#34;;function at(e,i,t){let n=F(t).createElementNS(U,&#34;svg&#34;);return n.setAttributeNS(null,&#34;width&#34;,e.toString()),n.setAttributeNS(null,&#34;height&#34;,i.toString()),n.setAttributeNS(null,&#34;viewBox&#34;,`0 0 ${e} ${i}`),n}function ct(e,i){let t=new XMLSerializer().serializeToString(e);return i&amp;&amp;(t=t.replace(/[\u0000-\u0008\v\f\u000E-\u001F\uD800-\uDFFF\uFFFE\uFFFF]/gu,&#34;&#34;)),`data:image/svg+xml;charset=utf-8,${encodeURIComponent(t)}`}async function ht(e,i=&#34;image/png&#34;,t=1){try{return await new Promise((n,r)=&gt;{e.toBlob(o=&gt;{o?n(o):r(new Error(&#34;Blob is null&#34;))},i,t)})}catch(n){if(je)return dt(e.toDataURL(i,t));throw n}}function dt(e){let[i,t]=e.split(&#34;,&#34;),n=i.match(/data:(.+);/)?.[1]??void 0,r=window.atob(t),o=r.length,l=new Uint8Array(o);for(let s=0;s&lt;o;s+=1)l[s]=r.charCodeAt(s);return new Blob([l],{type:n})}function Ee(e,i){return new Promise((t,n)=&gt;{let r=new FileReader;r.onload=()=&gt;t(r.result),r.onerror=()=&gt;n(r.error),r.onabort=()=&gt;n(new Error(`Failed read blob to ${i}`)),i===&#34;dataUrl&#34;?r.readAsDataURL(e):i===&#34;arrayBuffer&#34;&amp;&amp;r.readAsArrayBuffer(e)})}var ut=e=&gt;Ee(e,&#34;dataUrl&#34;),gt=e=&gt;Ee(e,&#34;arrayBuffer&#34;);function H(e,i){let t=F(i).createElement(&#34;img&#34;);return t.decoding=&#34;sync&#34;,t.loading=&#34;eager&#34;,t.src=e,t}function x(e,i){return new Promise(t=&gt;{let{timeout:n,ownerDocument:r,onError:o,onWarn:l}=i??{},s=typeof e==&#34;string&#34;?H(e,F(r)):e,c=null,h=null;function a(){t(s),c&amp;&amp;clearTimeout(c),h?.()}if(n&amp;&amp;(c=setTimeout(a,n)),k(s)){let d=s.currentSrc||s.src;if(!d)return s.poster?x(s.poster,i).then(t):a();if(s.readyState&gt;=2)return a();let u=a,m=g=&gt;{l?.(&#34;Failed video load&#34;,d,g),o?.(g),a()};h=()=&gt;{s.removeEventListener(&#34;loadeddata&#34;,u),s.removeEventListener(&#34;error&#34;,m)},s.addEventListener(&#34;loadeddata&#34;,u,{once:!0}),s.addEventListener(&#34;error&#34;,m,{once:!0})}else{let d=pe(s)?s.href.baseVal:s.currentSrc||s.src;if(!d)return a();let u=async()=&gt;{if(L(s)&amp;&amp;&#34;decode&#34;in s)try{await s.decode()}catch(g){l?.(&#34;Failed to decode image, trying to render anyway&#34;,s.dataset.originalSrc||d,g)}a()},m=g=&gt;{l?.(&#34;Failed image load&#34;,s.dataset.originalSrc||d,g),a()};if(L(s)&amp;&amp;s.complete)return u();h=()=&gt;{s.removeEventListener(&#34;load&#34;,u),s.removeEventListener(&#34;error&#34;,m)},s.addEventListener(&#34;load&#34;,u,{once:!0}),s.addEventListener(&#34;error&#34;,m,{once:!0})}})}async function mt(e,i){R(e)&amp;&amp;(L(e)||k(e)?await x(e,i):await Promise.all([&#34;img&#34;,&#34;video&#34;].flatMap(t=&gt;Array.from(e.querySelectorAll(t)).map(n=&gt;x(n,i)))))}var ve=function(){let i=0,t=()=&gt;`0000${(Math.random()*36**4&lt;&lt;0).toString(36)}`.slice(-4);return()=&gt;(i+=1,`u${t()}${i}`)}();function we(e){return e?.split(&#34;,&#34;).map(i=&gt;i.trim().replace(/&#34;|&#39;/g,&#34;&#34;).toLowerCase()).filter(Boolean)}var re=0;function ft(e){let i=`${me}[#${re}]`;return re++,{time:t=&gt;e&amp;&amp;console.time(`${i} ${t}`),timeEnd:t=&gt;e&amp;&amp;console.timeEnd(`${i} ${t}`),warn:(...t)=&gt;e&amp;&amp;st(...t)}}function pt(e){return{cache:e?&#34;no-cache&#34;:&#34;force-cache&#34;}}async function q(e,i){return ze(e)?e:bt(e,{...i,autoDestruct:!0})}async function bt(e,i){let{scale:t=1,workerUrl:n,workerNumber:r=1}=i||{},o=!!i?.debug,l=i?.features??!0,s=e.ownerDocument??(C?window.document:void 0),c=e.ownerDocument?.defaultView??(C?window:void 0),h=new Map,a={width:0,height:0,quality:1,type:&#34;image/png&#34;,scale:t,backgroundColor:null,style:null,filter:null,maximumCanvasSize:0,timeout:3e4,progress:null,debug:o,fetch:{requestInit:pt(i?.fetch?.bypassingCache),placeholderImage:&#34;data:image/png;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7&#34;,bypassingCache:!1,...i?.fetch},fetchFn:null,font:{},drawImageInterval:100,workerUrl:null,workerNumber:r,onCloneNode:null,onEmbedNode:null,onCreateForeignObjectSvg:null,includeStyleProperties:null,autoDestruct:!1,...i,__CONTEXT__:!0,log:ft(o),node:e,ownerDocument:s,ownerWindow:c,dpi:t===1?null:96*t,svgStyleElement:ye(s),svgDefsElement:s?.createElementNS(U,&#34;defs&#34;),svgStyles:new Map,defaultComputedStyles:new Map,workers:[...Array.from({length:Ve&amp;&amp;n&amp;&amp;r?r:0})].map(()=&gt;{try{let m=new Worker(n);return m.onmessage=async g=&gt;{let{url:f,result:p}=g.data;p?h.get(f)?.resolve?.(p):h.get(f)?.reject?.(new Error(`Error receiving message from worker: ${f}`))},m.onmessageerror=g=&gt;{let{url:f}=g.data;h.get(f)?.reject?.(new Error(`Error receiving message from worker: ${f}`))},m}catch(m){return a.log.warn(&#34;Failed to new Worker&#34;,m),null}}).filter(Boolean),fontFamilies:new Map,fontCssTexts:new Map,acceptOfImage:`${[lt(s)&amp;&amp;&#34;image/webp&#34;,&#34;image/svg+xml&#34;,&#34;image/*&#34;,&#34;*/*&#34;].filter(Boolean).join(&#34;,&#34;)};q=0.8`,requests:h,drawImageCount:0,tasks:[],features:l,isEnable:m=&gt;m===&#34;restoreScrollPosition&#34;?typeof l==&#34;boolean&#34;?!1:l[m]??!1:typeof l==&#34;boolean&#34;?l:l[m]??!0};a.log.time(&#34;wait until load&#34;),await mt(e,{timeout:a.timeout,onWarn:a.log.warn}),a.log.timeEnd(&#34;wait until load&#34;);let{width:d,height:u}=Et(e,a);return a.width=d,a.height=u,a}function ye(e){if(!e)return;let i=e.createElement(&#34;style&#34;),t=i.ownerDocument.createTextNode(`
.______background-clip--text {
  background-clip: text;
  -webkit-background-clip: text;
}
`);return i.appendChild(t),i}function Et(e,i){let{width:t,height:n}=i;if(S(e)&amp;&amp;(!t||!n)){let r=e.getBoundingClientRect();t=t||r.width||Number(e.getAttribute(&#34;width&#34;))||0,n=n||r.height||Number(e.getAttribute(&#34;height&#34;))||0}return{width:t,height:n}}async function vt(e,i){let{log:t,timeout:n,drawImageCount:r,drawImageInterval:o}=i;t.time(&#34;image to canvas&#34;);let l=await x(e,{timeout:n,onWarn:i.log.warn}),{canvas:s,context2d:c}=wt(e.ownerDocument,i),h=()=&gt;{try{c?.drawImage(l,0,0,s.width,s.height)}catch(a){i.log.warn(&#34;Failed to drawImage&#34;,a)}};if(h(),i.isEnable(&#34;fixSvgXmlDecode&#34;))for(let a=0;a&lt;r;a++)await new Promise(d=&gt;{setTimeout(()=&gt;{h(),d()},a+o)});return i.drawImageCount=0,t.timeEnd(&#34;image to canvas&#34;),s}function wt(e,i){let{width:t,height:n,scale:r,backgroundColor:o,maximumCanvasSize:l}=i,s=e.createElement(&#34;canvas&#34;);s.width=Math.floor(t*r),s.height=Math.floor(n*r),s.style.width=`${t}px`,s.style.height=`${n}px`,l&amp;&amp;(s.width&gt;l||s.height&gt;l)&amp;&amp;(s.width&gt;l&amp;&amp;s.height&gt;l?s.width&gt;s.height?(s.height*=l/s.width,s.width=l):(s.width*=l/s.height,s.height=l):s.width&gt;l?(s.height*=l/s.width,s.width=l):(s.width*=l/s.height,s.height=l));let c=s.getContext(&#34;2d&#34;);return c&amp;&amp;o&amp;&amp;(c.fillStyle=o,c.fillRect(0,0,s.width,s.height)),{canvas:s,context2d:c}}function Se(e,i){if(e.ownerDocument)try{let o=e.toDataURL();if(o!==&#34;data:,&#34;)return H(o,e.ownerDocument)}catch(o){i.log.warn(&#34;Failed to clone canvas&#34;,o)}let t=e.cloneNode(!1),n=e.getContext(&#34;2d&#34;),r=t.getContext(&#34;2d&#34;);try{return n&amp;&amp;r&amp;&amp;r.putImageData(n.getImageData(0,0,e.width,e.height),0,0),t}catch(o){i.log.warn(&#34;Failed to clone canvas&#34;,o)}return t}function yt(e,i){try{if(e?.contentDocument?.body)return X(e.contentDocument.body,i)}catch(t){i.log.warn(&#34;Failed to clone iframe&#34;,t)}return e.cloneNode(!1)}function St(e){let i=e.cloneNode(!1);return e.currentSrc&amp;&amp;e.currentSrc!==e.src&amp;&amp;(i.src=e.currentSrc,i.srcset=&#34;&#34;),i.loading===&#34;lazy&#34;&amp;&amp;(i.loading=&#34;eager&#34;),i}async function Tt(e,i){if(e.ownerDocument&amp;&amp;!e.currentSrc&amp;&amp;e.poster)return H(e.poster,e.ownerDocument);let t=e.cloneNode(!1);t.crossOrigin=&#34;anonymous&#34;,e.currentSrc&amp;&amp;e.currentSrc!==e.src&amp;&amp;(t.src=e.currentSrc);let n=t.ownerDocument;if(n){let r=!0;if(await x(t,{onError:()=&gt;r=!1,onWarn:i.log.warn}),!r)return e.poster?H(e.poster,e.ownerDocument):t;t.currentTime=e.currentTime,await new Promise(l=&gt;{t.addEventListener(&#34;seeked&#34;,l,{once:!0})});let o=n.createElement(&#34;canvas&#34;);o.width=e.offsetWidth,o.height=e.offsetHeight;try{let l=o.getContext(&#34;2d&#34;);l&amp;&amp;l.drawImage(t,0,0,o.width,o.height)}catch(l){return i.log.warn(&#34;Failed to clone video&#34;,l),e.poster?H(e.poster,e.ownerDocument):t}return Se(o,i)}return t}function At(e,i){return Qe(e)?Se(e,i):ot(e)?yt(e,i):L(e)?St(e):k(e)?Tt(e,i):e.cloneNode(!1)}function Ct(e){let i=e.sandbox;if(!i){let{ownerDocument:t}=e;try{t&amp;&amp;(i=t.createElement(&#34;iframe&#34;),i.id=`__SANDBOX__-${ve()}`,i.width=&#34;0&#34;,i.height=&#34;0&#34;,i.style.visibility=&#34;hidden&#34;,i.style.position=&#34;fixed&#34;,t.body.appendChild(i),i.contentWindow?.document.write(&#39;&lt;!DOCTYPE html&gt;&lt;meta charset=&#34;UTF-8&#34;&gt;&lt;title&gt;&lt;/title&gt;&lt;body&gt;&#39;),e.sandbox=i)}catch(n){e.log.warn(&#34;Failed to getSandBox&#34;,n)}}return i}var Ht=[&#34;width&#34;,&#34;height&#34;,&#34;-webkit-text-fill-color&#34;],Lt=[&#34;stroke&#34;,&#34;fill&#34;];function Te(e,i,t){let{defaultComputedStyles:n}=t,r=e.nodeName.toLowerCase(),o=_(e)&amp;&amp;r!==&#34;svg&#34;,l=o?Lt.map(f=&gt;[f,e.getAttribute(f)]).filter(([,f])=&gt;f!==null):[],s=[o&amp;&amp;&#34;svg&#34;,r,l.map((f,p)=&gt;`${f}=${p}`).join(&#34;,&#34;),i].filter(Boolean).join(&#34;:&#34;);if(n.has(s))return n.get(s);let h=Ct(t)?.contentWindow;if(!h)return new Map;let a=h?.document,d,u;o?(d=a.createElementNS(U,&#34;svg&#34;),u=d.ownerDocument.createElementNS(d.namespaceURI,r),l.forEach(([f,p])=&gt;{u.setAttributeNS(null,f,p)}),d.appendChild(u)):d=u=a.createElement(r),u.textContent=&#34; &#34;,a.body.appendChild(d);let m=h.getComputedStyle(u,i),g=new Map;for(let f=m.length,p=0;p&lt;f;p++){let b=m.item(p);Ht.includes(b)||g.set(b,m.getPropertyValue(b))}return a.body.removeChild(d),n.set(s,g),g}function Ae(e,i,t){let n=new Map,r=[],o=new Map;if(t)for(let s of t)l(s);else for(let s=e.length,c=0;c&lt;s;c++){let h=e.item(c);l(h)}for(let s=r.length,c=0;c&lt;s;c++)o.get(r[c])?.forEach((h,a)=&gt;n.set(a,h));function l(s){let c=e.getPropertyValue(s),h=e.getPropertyPriority(s),a=s.lastIndexOf(&#34;-&#34;),d=a&gt;-1?s.substring(0,a):void 0;if(d){let u=o.get(d);u||(u=new Map,o.set(d,u)),u.set(s,[c,h])}i.get(s)===c&amp;&amp;!h||(d?r.push(d):n.set(s,[c,h]))}return n}function Rt(e,i,t,n){let{ownerWindow:r,includeStyleProperties:o,currentParentNodeStyle:l}=n,s=i.style,c=r.getComputedStyle(e),h=Te(e,null,n);l?.forEach((d,u)=&gt;{h.delete(u)});let a=Ae(c,h,o);a.delete(&#34;transition-property&#34;),a.delete(&#34;all&#34;),a.delete(&#34;d&#34;),a.delete(&#34;content&#34;),t&amp;&amp;(a.delete(&#34;margin-top&#34;),a.delete(&#34;margin-right&#34;),a.delete(&#34;margin-bottom&#34;),a.delete(&#34;margin-left&#34;),a.delete(&#34;margin-block-start&#34;),a.delete(&#34;margin-block-end&#34;),a.delete(&#34;margin-inline-start&#34;),a.delete(&#34;margin-inline-end&#34;),a.set(&#34;box-sizing&#34;,[&#34;border-box&#34;,&#34;&#34;])),a.get(&#34;background-clip&#34;)?.[0]===&#34;text&#34;&amp;&amp;i.classList.add(&#34;______background-clip--text&#34;),fe&amp;&amp;(a.has(&#34;font-kerning&#34;)||a.set(&#34;font-kerning&#34;,[&#34;normal&#34;,&#34;&#34;]),(a.get(&#34;overflow-x&#34;)?.[0]===&#34;hidden&#34;||a.get(&#34;overflow-y&#34;)?.[0]===&#34;hidden&#34;)&amp;&amp;a.get(&#34;text-overflow&#34;)?.[0]===&#34;ellipsis&#34;&amp;&amp;e.scrollWidth===e.clientWidth&amp;&amp;a.set(&#34;text-overflow&#34;,[&#34;clip&#34;,&#34;&#34;]));for(let d=s.length,u=0;u&lt;d;u++)s.removeProperty(s.item(u));return a.forEach(([d,u],m)=&gt;{s.setProperty(m,d,u)}),a}function xt(e,i){(Ze(e)||et(e)||nt(e))&amp;&amp;i.setAttribute(&#34;value&#34;,e.value)}var Nt=[&#34;:before&#34;,&#34;:after&#34;],_t=[&#34;:-webkit-scrollbar&#34;,&#34;:-webkit-scrollbar-button&#34;,&#34;:-webkit-scrollbar-thumb&#34;,&#34;:-webkit-scrollbar-track&#34;,&#34;:-webkit-scrollbar-track-piece&#34;,&#34;:-webkit-scrollbar-corner&#34;,&#34;:-webkit-resizer&#34;];function It(e,i,t,n,r){let{ownerWindow:o,svgStyleElement:l,svgStyles:s,currentNodeStyle:c}=n;if(!l||!o)return;function h(a){let d=o.getComputedStyle(e,a),u=d.getPropertyValue(&#34;content&#34;);if(!u||u===&#34;none&#34;)return;r?.(u),u=u.replace(/(&#39;)|(&#34;)|(counter\(.+\))/g,&#34;&#34;);let m=[ve()],g=Te(e,a,n);c?.forEach((E,y)=&gt;{g.delete(y)});let f=Ae(d,g,n.includeStyleProperties);f.delete(&#34;content&#34;),f.delete(&#34;-webkit-locale&#34;),f.get(&#34;background-clip&#34;)?.[0]===&#34;text&#34;&amp;&amp;i.classList.add(&#34;______background-clip--text&#34;);let p=[`content: &#39;${u}&#39;;`];if(f.forEach(([E,y],A)=&gt;{p.push(`${A}: ${E}${y?&#34; !important&#34;:&#34;&#34;};`)}),p.length===1)return;try{i.className=[i.className,...m].join(&#34; &#34;)}catch(E){n.log.warn(&#34;Failed to copyPseudoClass&#34;,E);return}let b=p.join(`
  `),w=s.get(b);w||(w=[],s.set(b,w)),w.push(`.${m[0]}:${a}`)}Nt.forEach(h),t&amp;&amp;_t.forEach(h)}var oe=new Set([&#34;symbol&#34;]);async function se(e,i,t,n,r){if(S(t)&amp
