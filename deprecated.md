# deprecated



해당 Gitbook은 나의 정리 목적도 있지만, 다른 사람들이 깊게 공부했으면 하는 바람에 쓴 글이다. 나는 원래 글을 잘 안쓴다. 오히려 키워드\(기억 앵커링 단어\)는 쓰는 방식으로 공부한다. 그 이유는 글 작성하는 시간이 아깝다고 생각하고, 무엇보다 글을 잘 못쓴다.

여러 개발자들을 만나면서, React를 사용중인 사람을 여럿 만났지만... 깊게 아는 사람은 찾아보기 힘들었다. 뭐 한편으로 너무 깊게 할 필요도 없기도 하다. _네카라쿠배_ 정도가 아니면, **내가 면접에서 느낀 거는 대부분의 회사들이 경력이 있고, 대충 어느정도 작성할 줄 아는 사람을 원한다.**  나는 중학생때 Assembly를 통해서 리버스엔지니어링을 했었다. 하지만, 웹 개발자로 일하면서 해당 지식을 사용한 적이 단 한번도 없다. 그래도 깊게 공부하고 싶은 개발자를 위해서 Gitbook을 정리하였다. 

> 네카라쿠배 - 네이버, 카카오, 라인, 쿠팡, 배민의 줄임말

나는 여러 면접을 보았지만, 아직까지는 네카라쿠배 정도 말고는 면접관이 나에게 깊게 물어본적이 없었다. 그 이외는 그냥 경험이나 자신이나 같은 라이브러리를 쓰는지 더 궁금했다. 반대로 내가 물어보면 모르는 면접관도 은근히 있었다. 

나는 개발자의 실력은 `설계, 디버깅, 레거시 리팩토링`  능력이라고 본다. 언어는 API만 사용하는 도구일뿐이다. Java 경력 5년? 10년 의미없다. Java API를 까본다던가, GC마다 어떻게 처리방식이 다르고, 어떤점이 변했는지 알면 좋다. 

> G1 GC의 String Deduplication
>
> Java 버젼에 따른에서 HashMap 차이 \( red-black tree \)
>
> V8의 inline Cache

예\) G1 GC - String Deduplication, 

* 해당 Gitbook은 비판가처럼 썼지만, 나는 TMI병이 있어서... 나에게 물어보면.. 상대방이 이해할때까지 말을 하거나, 관련 레퍼런스를 보내준다. 오해하지 말도록....



> A 개발자: 얕은 비교\(ShallowEqual\) 를 해서 rerendering을 하잖아?
>
> 저자 : 얕은 비교가 어떻게 이루어지는데 ???
>
> A 개발자: 해당객체가 같은지, 값이 같은지 비교하지...

> 저자 : ===\(strict equality\)랑 뭐가 달라??
>
> A 개발자: 거기까지는 모르겠어. 음 같은거 아닐까?? 여태까지 문제없었는데

얕은비교에 대해서는 React Core 에서 설명할 예정이다. 실제로 나는 실무에서 해당 지식이 없어도 





