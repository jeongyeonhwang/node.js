# [node.js] 로그인 화면 구현하기

## 1. hard coding
app.js
## 2. View 분리 (View 최적화)

* view 폴더 생성

![image](https://github.com/jeongyeonhwang/node.js/assets/90510701/ece4279f-091e-460c-891a-a22f4f9e8ebf)

* npm install ejs (ejs 설치)

* view 엔진 ejs -> html 역할

![image](https://github.com/jeongyeonhwang/node.js/assets/90510701/3364bcad-a554-4392-85c1-e90f386b2fb4)


## 3. Router 분리

* routes 폴더 생성

![image](https://github.com/jeongyeonhwang/node.js/assets/90510701/d20d859c-b24a-4389-ab78-b0b3ec706fc6)

* 내보내기 명령어 사용 (다른 파일에서 index.js를 불러올 수 있게 하기 위함)

```javascript
module.exports = router;
```

* 라우팅

![image](https://github.com/jeongyeonhwang/node.js/assets/90510701/67504d64-1896-471b-9b6c-974c37e8e335)

## 4. Controller 분리

* home.ctrl.js로 빼줄 기능들
  
```javascript
  (req, res) => {
    res.render("home/login");
}
```

* 내보내기 명령어 사용
  
```javascript
module.exports = {
    hello,
    login,
};
```



