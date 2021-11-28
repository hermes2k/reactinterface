## 1. npm/node 최신버전으로 설치하기
```bash
$>node -v
$>npm cache clean -f
$>npm install -g n
$>n lts
$>npm -v
$>npm i -g npm
```

## 2. Create React App
```bash
$>npm uninstall -g create-react-app  # 기존에 예전버전이 설치되어있는경우, 삭제
$>npx create-react-app reactinterface
$>cd reactinterface
$>npm start
```

## 3. Modules
- Webpack (public 아래는 webpack에서 관리한다.)
- Babel
- ES Lint
- Jest
- Web Vitals

## 4. External Modules
```
1) React Icons 설치 (https://react-icons.github.io/react-icons/)
$>npm install react-icons --save
import { ICONNAME } from "react-icons/LIBNAME";
...
< ICONNAME />

2) Tailwind CSS (https://tailwindcss.com/docs)
// React에 설치하는법 (https://tailwindcss.com/docs/guides/create-react-app)
$>npm install -D tailwindcss@npm:@tailwindcss/postcss7-compat postcss@^7 autoprefixer@^9
$>npm install @craco/craco
// package.json 파일 수정
"scripts": {
    "start": "craco start",
    "build": "craco build",
    "test": "craco test",
    "eject": "react-scripts eject"
},
// craco.config.js 파일 생성
module.exports = {
    style: {
        postcss: {
            plugins: [
                require('tailwindcss'),
                require('autoprefixer'),
            ],
        },
    },
}

// tailwind.config.js 파일을 아래 명령으로 생성
$>npx tailwindcss-cli@latest init

// production 용으로 빌드시, purge에 기술된 파일들은 빌드에서 제외시켜서 최적화를 한다. 아래와 같이 적어주자.
  purge: ['./src/**/*.{js,jsx,ts,tsx}', './public/index.html'],

// ./src/index.css 파일을 아래로 교체
/* ./src/index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

// src/index.js 파일에 아래 import 추가
import './index.css';
```
