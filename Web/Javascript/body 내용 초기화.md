# 🎃 body 내용 초기화 🎃
body 태그 안에 있는 HTML 요소들 중 내용을 초기화 하고 싶을때는 innerHTML 을 사용하면 된다.<br/>
innerHTM은 동적으로 HTML을 추가하는 것으로 내용을 추가하는 것도 가능하지만 이것을 활용하여 body 태그 안의 요소들을 전부 초기화시키거나 원하는 위치의 부분을 초기화시킬 수도 있다.<br/>
```js
document.querySelector('#card').innerHTML=''; // 검색 시 조건에 맞는 영화만 출력하기 위해 비우기
``` 

<br/>

반대로 내용을 추가할때는 아래와 같이 내용을 추가해줄 수 있고
```js
let myHTML = document.querySelector('#card');

let add = '';
add += '<div>내용을 추가</div>';

myHTML.innerHTML = add;
``` 

<br/>

더 나아가서 이전에 했었던 프로젝트에서 백키(`)를 통해 html 문을 통째로 변수에 저장시키고 insertAdjacenHTML을 사용해서 내용을 추가시켜줄 수도 있다.
```js
 let temp_html = `
            <div class="col" onclick="alert('영화 ID : '+${id})">
                <div class="card h-100">
                <img src="${img_url}" class="card-img-top" alt="..."/>
                <div class="card-body">
                    <h5 class="card-title" id="count">${original_title}</h5>
                    <p class="card-text">${overview}</p>
                </div>
                <div class="card-footer">
                    <small class="text-body-secondary">평점 : ${vote_average}</small>
                </div>
                </div>
            </div>`;

document.querySelector('#card').insertAdjacentHTML('beforeend', temp_html);
```
