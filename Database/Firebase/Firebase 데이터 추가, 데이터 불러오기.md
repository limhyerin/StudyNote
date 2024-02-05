# 🎃 데이터를 추가할 수 있는 코드 🎃
```js
$("#id").click(async function () {
    let doc = {};
    await addDoc(collection(db, "콜렉션이름"), doc);
})
``` 

기록하기 버튼에서 평소에는 되는데 script type="module"을 해주었을때 onclick이 안되기때문에 없애주고 id 값을 지정
```js
$("#postingbtn").click(async function () {
        let image = $("#image").val();
        let title = $("#title").val();
        let star = $("#star").val();
        let comment = $("#comment").val();

        let doc = {
          image: image,
          title: title,
          star: star,
          comment: comment,
        };
        await addDoc(collection(db, "movies"), doc);
        alert("저장 완료!");
        window.location.reload(); //새로고침
      });
$("#savebtn").click(async function () {
        $("#postingbox").toggle(); //나와있으면 꺼지고 켜져있으면 꺼지고
      });
```

<br/>

버튼 클릭시 접었다 펴는 기능도, $(document).ready(function() {}) 기능도 의미가 없어져서 다른 것을 할 필요는 없고 그 안에 있는 코드들은 다 빼놓으면 된다.
```js
$("#savebtn").click(async function () {
        $("#postingbox").toggle(); //나와있으면 꺼지고 켜져있으면 꺼지고
      });
``` 

<br/>

# 🎃 파이어베이스에서 값을 가져와서 붙이는 코드 🎃
```js
let docs = await getDocs(collection(db, "albums"));
      docs.forEach((doc) => {
        let row = doc.data();

        let image = row['image'];
        let title = row['title'];
        let content = row['content'];
        let date = row['date'];

        let temp_html = `
              <div class="col">
                <div class="card h-100">
                  <img
                    src="${image}"
                    class="card-img-top"
                    alt="..."
                  />
                  <div class="card-body">
                    <h5 class="card-title">${title}</h5>
                    <p class="card-text">${content}</p>
                  </div>
                  <div class="card-footer">
                    <small class="text-body-secondary">${date}</small>
                  </div>
                </div>
              </div>`;

        $("#card").append(temp_html);
      });
```
