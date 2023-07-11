# 배열과 객체에서의 구조분해할당


## 🚀배열에서의 구조분해할당

<hr />

- 배열의 각 요소를 배열로부터 추출하여, **1개이상의 변수**를 할당한다

```js
const arr = [1,2,3]

//배열의 구조분해 할당
const [a,b,c] = arr;

console.log(a) //1
```

- 배열에서의 구조분해할당의 기준은 **배열의 인덱스**이다. 즉, 순서대로 **할당**된다

```js
const [a,b] = [1,2]
console.log(a,b) //1,2

const [c,d] = [1];
console.log(c,d) //1, undefined

const [e,f] = [1,2,3]
console.log(e,f) //1,2

```

- 배열에서도 Rest 파라미터와 유사하게 Rest 요소를 사용할 수 있다

```js
const [x, ...y] = [1,2,3];
console.log(x,y) // 1 [2,3]
```

<br />

## 🚀객체에서의 구조분해할당

<hr />

- 객체에서도 구조분해할당이가능하다 
- 변수에 할당하기 위해선 프로퍼티의 `key`를 사용해야한다

```js
const user = {name : 'seju', age: 26}

//일반 객체에서의 접근 후 할당법
const name = user.name;
const age = user.age

console.log(name) // 'seju'
```

- 객체의 구조 분해 할당에서 **우변은 객체**여야하고, 할당 기준은 **프로퍼티의 키**이다

### 객체 구조 분해 할당 예시 [1]

```js
const user = {name : 'seju', age: 26}

// 객체에서의 구조 분해 할당
const {name,age} = user;

console.log(name) // 'seju'

```

### 객체 구조 분해 할당 예시 [2]

```js
const todo = {
    id :1, content:'Javascript', complted:true
}

// 객체에서의 구조 분해 할당 ➡️ toDo 객체로부터 id프로퍼티만 추출했다
const {id} = todo;
console.log(id) // 1

```
- 객체의 구조분해할당은 객체를 인수로 전달받는 함수에서의 매개변수로 전달 할 수 도 있다.

```js
//매개변수로 전달받은 객체를 인수에서 객체로 구조분해할당을해서 id,content를 바로 매개변수로 받는다
const printTodo = ({id,content}) => {
    console.log(id) //1
    console.log(content) // 'Javascript'
}

printTodo({id: 1, content : 'Javascript', complted:true});

```

### 객체 구조 분해 할당 예시 [3]
- 배열안의 요소가 객체인경우, 배열 구조분해할당과 객체 구조분해할당을 혼용해서 활용가능

```js
// todos라는 객체로 구성된 배열
const todos = [
    {id : 1, content : 'HTML', completed:true},
    {id : 2, content : 'CSS', completed:false},
    {id : 3, content : 'Javascipr', completed:true},
]

// 배열의 두 번째 요소인 객체로 부터 id 프로퍼티만 추출
const [,{id}] = todos;
console.log(id) //2

```
