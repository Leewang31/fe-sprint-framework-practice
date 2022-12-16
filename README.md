# 🎆fe-sprint-framework-practice

## 🎇How to use REDUX

### ✨npm
```bash
$ npm i redux
```

### ✨REDUX

#### Store
```js
import { createStore } from 'redux';

const store = createStore(rootReducer);
```

#### Reducer
```js
const count = 1

// Reducer를 생성할 때에는 초기 상태를 인자로 요구합니다.
const counterReducer = (state = count, action) => {

  // Action 객체의 type 값에 따라 분기하는 switch 조건문입니다.
  switch (action.type) {

    //action === 'INCREASE'일 경우
    case 'INCREASE':
			return state + 1

    // action === 'DECREASE'일 경우
    case 'DECREASE':
			return state - 1

    // action === 'SET_NUMBER'일 경우
    case 'SET_NUMBER':
			return action.payload

    // 해당 되는 경우가 없을 땐 기존 상태를 그대로 리턴
    default:
      return state;
	}
}
// Reducer가 리턴하는 값이 새로운 상태가 됩니다.
```

#### Action
```
// payload가 필요 없는 경우
{ type: 'INCREASE' }

{ type: 'SET_NUMBER', payload: 5 }
```
```js
// payload가 필요 없는 경우
const increase = () => {
  return {
    type: 'INCREASE'
  }
}

// payload가 필요한 경우
const setNumber = (num) => {
  return {
    type: 'SET_NUMBER',
    payload: num
  }
}
```

#### Dispatch
```js
// Action 객체를 직접 작성하는 경우
dispatch( { type: 'INCREASE' } );
dispatch( { type: 'SET_NUMBER', payload: 5 } );

// 액션 생성자(Action Creator)를 사용하는 경우
dispatch( increase() );
dispatch( setNumber(5) );
```

### ✨Redux Hooks
#### useDispatch()
```js
import { useDispatch } from 'react-redux'

const dispatch = useDispatch()
dispatch( increase() )
console.log(counter) // 2

dispatch( setNumber(5) )
console.log(counter) // 5
```

#### useSelector()
```js
// Redux Hooks 메서드는 'redux'가 아니라 'react-redux'에서 불러옵니다.
import { useSelector } from 'react-redux'
const counter = useSelector(state => state)
console.log(counter) // 1
```

## 🎇How to use Styled Components

### ✨npm
```bash
$ npm install --save styled-components
```
### ✨use Styled Components
```js
import styled from "styled-components"

const BlueButton = styled.button`
  background-color: blue;
  color: white;
`;
```