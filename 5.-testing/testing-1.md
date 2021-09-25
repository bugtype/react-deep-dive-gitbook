# Testing

리액트를 만든 Facebook에서는 [testing-library](https://testing-library.com/docs/react-testing-library/intro/)를 사용하기를 권장하고 있다.

해당 라이브러리에서 `act()`메소드가 제일 중요하다.

> act\(\) - 컴포넌트를 렌더링하고 갱신해주는 코드





```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import { act } from 'react-dom/test-utils';
import Counter from './Counter';

let container;

beforeEach(() => {
  container = document.createElement('div');
  document.body.appendChild(container);
});

afterEach(() => {
  document.body.removeChild(container);
  container = null;
});

it('can render and update a counter', () => {
  // 첫 render와 componentDidMount를 테스트
  act(() => {
    ReactDOM.render(<Counter />, container);
  });
  const button = container.querySelector('button');
  const label = container.querySelector('p');
  expect(label.textContent).toBe('You clicked 0 times');
  expect(document.title).toBe('You clicked 0 times');

  // 두 번째 render와 componentDidUpdate를 테스트
  act(() => {
    button.dispatchEvent(new MouseEvent('click', {bubbles: true}));
  });
  expect(label.textContent).toBe('You clicked 1 times');
  expect(document.title).toBe('You clicked 1 times');
});
```

위에 코드는 리액트 공식 사이트에 있는 코드이다. 하나씩 해석해보자



```jsx
beforeEach - 테스트 코드를 실행하기 전에 실행된다.
 만약 10개의 테스트 코드가 있으면 10번 실행된다.
```

