# ๐fe-sprint-framework-practice

## ๐How to use REDUX

### โจnpm
```bash
$ npm i redux
```

### โจREDUX

#### Store
```js
import { createStore } from 'redux';

const store = createStore(rootReducer);
```

#### Reducer
```js
const count = 1

// Reducer๋ฅผ ์์ฑํ  ๋์๋ ์ด๊ธฐ ์ํ๋ฅผ ์ธ์๋ก ์๊ตฌํฉ๋๋ค.
const counterReducer = (state = count, action) => {

  // Action ๊ฐ์ฒด์ type ๊ฐ์ ๋ฐ๋ผ ๋ถ๊ธฐํ๋ switch ์กฐ๊ฑด๋ฌธ์๋๋ค.
  switch (action.type) {

    //action === 'INCREASE'์ผ ๊ฒฝ์ฐ
    case 'INCREASE':
			return state + 1

    // action === 'DECREASE'์ผ ๊ฒฝ์ฐ
    case 'DECREASE':
			return state - 1

    // action === 'SET_NUMBER'์ผ ๊ฒฝ์ฐ
    case 'SET_NUMBER':
			return action.payload

    // ํด๋น ๋๋ ๊ฒฝ์ฐ๊ฐ ์์ ๋ ๊ธฐ์กด ์ํ๋ฅผ ๊ทธ๋๋ก ๋ฆฌํด
    default:
      return state;
	}
}
// Reducer๊ฐ ๋ฆฌํดํ๋ ๊ฐ์ด ์๋ก์ด ์ํ๊ฐ ๋ฉ๋๋ค.
```

#### Action
```
// payload๊ฐ ํ์ ์๋ ๊ฒฝ์ฐ
{ type: 'INCREASE' }

{ type: 'SET_NUMBER', payload: 5 }
```
```js
// payload๊ฐ ํ์ ์๋ ๊ฒฝ์ฐ
const increase = () => {
  return {
    type: 'INCREASE'
  }
}

// payload๊ฐ ํ์ํ ๊ฒฝ์ฐ
const setNumber = (num) => {
  return {
    type: 'SET_NUMBER',
    payload: num
  }
}
```

#### Dispatch
```js
// Action ๊ฐ์ฒด๋ฅผ ์ง์  ์์ฑํ๋ ๊ฒฝ์ฐ
dispatch( { type: 'INCREASE' } );
dispatch( { type: 'SET_NUMBER', payload: 5 } );

// ์ก์ ์์ฑ์(Action Creator)๋ฅผ ์ฌ์ฉํ๋ ๊ฒฝ์ฐ
dispatch( increase() );
dispatch( setNumber(5) );
```

### โจRedux Hooks
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
// Redux Hooks ๋ฉ์๋๋ 'redux'๊ฐ ์๋๋ผ 'react-redux'์์ ๋ถ๋ฌ์ต๋๋ค.
import { useSelector } from 'react-redux'
const counter = useSelector(state => state)
console.log(counter) // 1
```

## ๐How to use Styled Components

### โจnpm
```bash
$ npm install --save styled-components
```
### โจuse Styled Components
```js
import styled from "styled-components"

const BlueButton = styled.button`
  background-color: blue;
  color: white;
`;
```