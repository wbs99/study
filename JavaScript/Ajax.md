```
const request = new XMLHttpRequest();
request.open("get", url, true);
request.onreadystatechange(() => {
  if (request.readyState === 4) {
    if (request.status >= 200 && request.status < 300) {
      console.log(request.responseText);
    }
  }
});
request.send();
```