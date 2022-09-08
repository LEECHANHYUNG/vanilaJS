# 📚BookList
- css -> bootswatch(yeti)
- 클래스를 통한 기능 구현 



### `1. 입력된 값을 List에 추가`
1) 책의 정보를 담는 클래스를 생성
	- title, author, isbn 프로퍼티가 있다.

2) 테이블 형식에 List를 추가
	- `const row = document.createElement('tr');`
	- 내용은 `innerHTML`로 추가

3) `preventDefault`
 - submit 버튼을 통해 제출 -> 새로고침 발생(a태그의 특성)
	 - submit 할 때 새로고침을 방지하기 위해 `e.preventDefault()` 추가

## 📝innerHTML / insertAdjacentHTML / textContent
- innerHTML : 요소 내에 포함된 HTML, XML 마크업을 가져오거나 설정
- insertAdjacentHTML : 기존 element 변경 x(자식노드 삭제 x)
- textContent : 마크업을 제외한 텍스트만

### `2. List에 있는 값을 삭제`
- List에 추가할 때 버튼(a태그)을 추가 -> 리스트 삭제 버튼
- 삭제 버튼(submit)이 눌러진 경우 해당 row의 부모 노드를 삭제
```
document.querySelector("#book-list").addEventListener("click", (e) => {
  UI.deleteBook(e.target);
}
```
- `e.target`
	- 이벤트가 발생한 대상 얻기 -> 요소를 리턴

- e.target을 통해 얻은 요소로 해당 요소가 속한 리스트를 삭제
```
static deleteBook(el) {
    if (el.classList.contains("delete")) {
      el.parentElement.parentElement.remove();
  }
}
```