# Hooks Testing



설치

```text
npm install --save-dev @testing-library/react-hooks
```

useCounter.js

```jsx
// https://github.com/testing-library/react-hooks-testing-library

import { useState, useCallback } from 'react'

function useCounter() {
  const [count, setCount] = useState(0)

  const increment = useCallback(() => setCount((x) => x + 1), [])

  return { count, increment }
}

export default useCounter
```





useCounter.test.js

```jsx
import { renderHook, act } from '@testing-library/react-hooks'
import useCounter from './useCounter'

test('should increment counter', () => {
  const { result } = renderHook(() => useCounter())

  act(() => {
    result.current.increment()
  })

  expect(result.current.count).toBe(1)
})
```

