# 🎃 reset CSS 란 🎃
html로 코드를 작성하고 브라우저로 실행하면 내가 적용하지 않았음에도 자동으로 margin값이 들어가거나 다른 설정값이 들어가있는 경우가 있다. 이는 웹 브라우저마나 default값으로 스타일이 적용되어 있기 때문인데. 우리는 브라우저마다 기본 default 스타일 값이 아닌 동일한 CSS 스타일을 보여주기 위해 default 값을 초기화 해주어야한다.

<br/>

그래서 이 default 값을 초기화해주는 코드가 reset.css 이다

<br/>

### 코드
```css
/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
``` 

그다음 style.css 파일 위에 @import "reset.css"; 를 해주면 끝이난다.
