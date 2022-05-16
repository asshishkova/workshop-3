# workshop-3
Show the list of titles with links from https://edition.cnn.com/

```
const results = Array.prototype.map.call(document.querySelectorAll('.cd--card'), (el => {
    const text = el.innerText;
    const link = el.querySelector('a')?.href;
    return {text, link};
}))

const body = document.getElementsByTagName('BODY')[0];

body.innerHTML = '';

for (let i = 8; i < 20; i++) {
    const list = document.createElement("li");
    const newlink = document.createElement("a");
    newlink.setAttribute("href", results[i].link);
    newlink.textContent = results[i].text;
    list.appendChild(newlink);
    body.appendChild(list);
}
```
