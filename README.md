# Adding up Times

A project from [JavaScript 30 - 18](https://youtu.be/SadWPo2KZWg)

应用场景：计算视频列表中全部视频的总时长

## What I leaned

- NodeList 虽然与数组很相似，但并不是数组，它没有数组的很多方法，比如 map,但有 forEach 方法.
- 将 NodeList 转换为真正的数组有两种方法，1 `Array.from(NodeList)` 2 `[...NodeList]`
- `arrayOfString.map(parseFloat)` is the same as `arrayOfString.map(str=>parseFloat(str))`

- Convert MM:SS string to seconds, eg. '1:56' -> 116, [Stackoverflow Link](https://stackoverflow.com/questions/9640266/)

  ```js
  let ms = "1:56";
  let a = ms.split(":"); // ['1','56']
  // +string: convert string to number
  let seconds = +a[0] * 60 + +a[1];
  ```

- Convert seconds(number) to HH:MM:SS(string), [StackOverflow Link](https://stackoverflow.com/questions/1322732/)
  ```js
  new Date(SECONDS * 1000).toISOString().substr(11, 8);
  ```
  If SECONDS<3600 and if you want to show only MM:SS then use below code:
  ```js
  new Date(SECONDS * 1000).toISOString().substr(14, 5);
  ```
- 向 ul 元素添加新 li 元素的方法
  ```js
  let li = document.createElement("li");
  li.appendChild(document.createTextNode(`text content`)); // or li.textContent='text content';
  const ul = document.querySelector("ul");
  ul.appendChild(li);
  ```
