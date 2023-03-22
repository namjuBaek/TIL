#### React 리액트 기초부터 쇼핑몰 프로젝트까지

---

- 자식 태그를 클릭하면 자식 태그를 포함하고 있는 부모 태그들의 클릭 이벤트까지 실행됨.

-> 이벤트버블링 현상

<br>

**이벤트 버블링 현상을 막는 방법**

- e.stopPropagation



state

- state 변경함수는 늦게처리됨 (비동기처리)



public 폴더 이미지

process.env.PUBLIC_URL -> public 폴더 이미지 쓰는 권장방식



##### react-router-dom

---

useNavigate

- 페이지 이동 도와주는 훅

<br>

**404 페이지**

- route path = "*" 로 지정

<br>

**Nested Routes**

```react
<Route path="/about" element={<About/>} >
  <Route path="member" element={<About/>} />
  <Route path="location" element={<About/>} />
</Route>
```

- Route 태그 안에 태그를 넣어 경로를 설정하는 방식
- nested route 접속시엔 상/하위 태그의 컴포넌트가 모두 보임
- nested routes의 element를 보여주는 곳은 <Outlet>
- 유사항 페이지일 때 주로 사용



**useParams()**

---

URL 파라미터에 입력한 값 가져오는 훅



**styled-components**

---

- 컴포넌트t.module.css 로 작명하면 해당 컴포넌트.js에만 스타일 적용됨



**컴포넌트의 LifeCycle**

---

**useEffect**

- mount, update 시 코드 실행해주는 훅
- html 렌더링 이후에 실행됨.

```react
useEffect(() => {
    setTimeout(() => {
      setAlert(false);
    }, 2000);

    return () => {
      // useEffect 동작 전에 실행됨
    }
  }, [count])
  // count state가 변할 때만 실행
```

- dependency에 []만 작성하면 update시에는 실행되지 않고, mount 시에만 실행됨
- useEffect 동작 전에 실행되는 return() => {}



**정리**

```react
useEffect(()=> {}) // mount, update 시 실해
useEffect(()=> {}, []) // mount 시에만 실행, 특정 state 변경 시에만 실행하려면 [state명]
useEffect(()=> {
  return () => {
    
  }
}. [])
```











