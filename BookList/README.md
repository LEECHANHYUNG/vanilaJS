# ๐BookList
- css -> bootswatch(yeti)
- ํด๋์ค๋ฅผ ํตํ ๊ธฐ๋ฅ ๊ตฌํ 



### `1. ์๋ ฅ๋ ๊ฐ์ List์ ์ถ๊ฐ`
1) ์ฑ์ ์ ๋ณด๋ฅผ ๋ด๋ ํด๋์ค๋ฅผ ์์ฑ
	- title, author, isbn ํ๋กํผํฐ๊ฐ ์๋ค.

2) ํ์ด๋ธ ํ์์ List๋ฅผ ์ถ๊ฐ
	- `const row = document.createElement('tr');`
	- ๋ด์ฉ์ `innerHTML`๋ก ์ถ๊ฐ

3) `preventDefault`
 - submit ๋ฒํผ์ ํตํด ์ ์ถ -> ์๋ก๊ณ ์นจ ๋ฐ์(aํ๊ทธ์ ํน์ฑ)
	 - submit ํ  ๋ ์๋ก๊ณ ์นจ์ ๋ฐฉ์งํ๊ธฐ ์ํด `e.preventDefault()` ์ถ๊ฐ

## ๐innerHTML / insertAdjacentHTML / textContent
- innerHTML : ์์ ๋ด์ ํฌํจ๋ HTML, XML ๋งํฌ์์ ๊ฐ์ ธ์ค๊ฑฐ๋ ์ค์ 
- insertAdjacentHTML : ๊ธฐ์กด element ๋ณ๊ฒฝ x(์์๋ธ๋ ์ญ์  x)
- textContent : ๋งํฌ์์ ์ ์ธํ ํ์คํธ๋ง

### `2. List์ ์๋ ๊ฐ์ ์ญ์ `
- List์ ์ถ๊ฐํ  ๋ ๋ฒํผ(aํ๊ทธ)์ ์ถ๊ฐ -> ๋ฆฌ์คํธ ์ญ์  ๋ฒํผ
- ์ญ์  ๋ฒํผ(submit)์ด ๋๋ฌ์ง ๊ฒฝ์ฐ ํด๋น row์ ๋ถ๋ชจ ๋ธ๋๋ฅผ ์ญ์ 
```
document.querySelector("#book-list").addEventListener("click", (e) => {
ย  UI.deleteBook(e.target);
}
```
- `e.target`
	- ์ด๋ฒคํธ๊ฐ ๋ฐ์ํ ๋์ ์ป๊ธฐ -> ์์๋ฅผ ๋ฆฌํด

- e.target์ ํตํด ์ป์ ์์๋ก ํด๋น ์์๊ฐ ์ํ ๋ฆฌ์คํธ๋ฅผ ์ญ์ 
```
static deleteBook(el) {
ย  ย  if (el.classList.contains("delete")) {
ย  ย  ย  el.parentElement.parentElement.remove();
ย  }
}
```