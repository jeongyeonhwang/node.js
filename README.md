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

* controller 모듈화

> index.js 파일
  
```javascript
const ctrl = require("./home.ctrl");

router.get("/", ctrl.hello);
router.get("/login", ctrl.login);
```

## 5. app.listen() 모듈화 시키기

* bin 폴더 생성 후 www.js 에 app.listen() 따로 빼줌

 ![image](https://github.com/jeongyeonhwang/node.js/assets/90510701/4f1ae072-8b2f-43b8-ba14-3d8fb2ad8533)

* app.listen() 코드 작성 주의 사항 !! PORT 번호 가져오는 것 잊지 말기

![image](https://github.com/jeongyeonhwang/node.js/assets/90510701/7b2af180-2c11-49c9-a2b6-92e804262d25)

./bin/www.js vs www.js(디렉터리 안에서 호출)
전자는 문제 없이 잘 돌아갔지만 후자는 error 발생함.
> 컴파일이 실행된 위치를 기반으로 각 파일들의 위치를 상대적으로 검사하기 때문임
>
> 루트 폴더에서 실행해야 하는 이유.

## 6. package.json

```javascript
npm init //패키지 설정 초기화
```

```javascript
npm init -y //패키지 설정 기본값으로 초기화 (yes의 y)
```

