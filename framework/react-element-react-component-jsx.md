# React Element, React Component, JSX



## I. React Element

{% hint style="info" %}
`type`과 `props`를 가지는 React의 객체
{% endhint %}

1. createElement를 이용해서 React Element 만들기

```javascript
// createElement를 이용해서 React Element 만들기
React.createElement(
'div',
{ className: 'name' },
'React'
)

// createElement를 이용해서 만들어진 React Element 객체
{
    type: 'div',
    props: {
        className: 'name',
        children: 'React'
    }
}


```



### II. React Component

{% hint style="info" %}
createElement를 이용해서 만들어진 React Element 객체
{% endhint %}

```javascript
// Button.jsx
function Button(props){
    return(
    <button>
        <strong>
            {props.children}
        </strong>
    </button>
    )
}

```



#### III. JSX

```jsx
<div className='name'>React</div>
```



### IV. 정리

React Elementㄹ

