# Best Practice Structure

> “소프트웨어 아키텍처는 선을 긋는 기술이며, 나는 이러한 선을 경계\(boundary\)라고 부른다. 경계는 소프트웨어 요소를 서로 분리하고, 경계 한편에 있는 요소가 반대편에 있는 요소를 알지 못하도록 막는다.” - Robert C. Martin, Clean Architecture, Ch. 17

**Robert C. Martin** 말 처럼 계층간에 선만 잘 그으면 유지보수하기 쉬운 코드가 됩니다. 

```text
View(컴포넌트) <-----> Hooks(logic) <-----> Service(side effect)
```

저는 주로 위와 같은 형태로 작성합니다. 

* View - 화면을 그려주는 계층 - 컴포넌트,  JSX
* Hooks - UI로직이나 데이터 처리 - custom hooks
  * 데이터 공유는 Recoil을 이용해서 해당 영역에서만 사용합니다.
* Service - 외부에 연결하는 부분, \(httpClient, store\)

```javascript
// 1. View
function Component(){
   const { data } = useMySelf()

  ... <div> {data.name} </div>
}

// 2. Hooks
function useMySelf(){
   const [user,setUser] = useState(null);
   
   useEffect(()=>{
      const data = userService.getMySelf();
      ...
      setUser(data)
      ...
   },[])

  ... <div> {data.name} </div>
}

// 3. Service
const userService = {
   getMySelf: () => httpClient.get("/myself")
   ...
}
```



#### Redux는 어떤식으로 설계하는 것이 좋은가요?

Redux는 Redux-devtool로 디버깅하기 좋습니다. 다만 저는 사용하지 않습니다. 여러가지 이유가 있습니다.

1. 하나의 기능을 만드는데 4개의 파일을 만들어야한다. 작업량이 늘어난다.
   * dispatch -&gt; action -&gt; reducer -&gt; store
2. Store간에 의존성이 심해진다.
3. Rx-observable 같은 라이브러리 사용시, epic에서 커플링이 심해진다.
   * A epic에서 a action을 호출해서 B epic에 영향을 주는 현상
   * Flow같은 문서화가 안되어 있으면 매우 복잡해진다.
4. 주로 주니어들이 어떠한 데이터든 Store에 넣는 경우가 생긴다.

저는 **Recoil** 같은 심플한 라이브러리나 **React context**로 주로 처리합니다. 

**Redux를 써야하는 경우가 생긴다면, 반드시 흐름도를 보여주는 문서화를 잘해주시길 바랍니다.**

* user Store는 A, B, C 컴포넌트에서 사용중입니다.
* user Epic에서 profile epic의 getProfile action을 호출합니다.









