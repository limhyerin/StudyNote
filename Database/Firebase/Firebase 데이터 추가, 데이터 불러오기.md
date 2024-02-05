# 🎃 데이터를 추가할 수 있는 코드 🎃
```js
$("#id").click(async function () {
    let doc = {};
    await addDoc(collection(db, "콜렉션이름"), doc);
})
``` 

근데 이렇게 하면 이제 onclick이 안된다. 그래서 onclick을 없애고 id값을 줘서 아래와 같이 바꾸어준다. <br/>
각각 파이어베이스에 값을 보내는 것 <br/>
```js
$("#postingbtn").click(async function () {
        let image = $("#image").val();
        let title = $("#title").val();
        let content = $("#content").val();
        let date = $("#date").val();

        let doc = {
          image: image,
          title: title,
          content: content,
          date: date,
        };
        await addDoc(collection(db, "albums"), doc);
        alert("저장 완료!");
        window.location.reload(); //새로고침
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
