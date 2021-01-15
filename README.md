# Expo(리액트 네이티브) 가이드

2021년 1월 15일 ~ 2021년 1월 15일
작성자: 조민재 (https://github.com/ussr1285)

## Expo와 React-Native의 특징

##### ㅇ우

##### 레이아웃 디자인

```react
import * as React from 'react';
import { Text, View } from 'react-native';

export default function App() {
  return (
    <View style={{ flex: 1, paddingTop: 100 }}>
      <Text>Hello, world!</Text>
    </View>
  );
}
```

React-Native의 레이아웃 디자인은 웹(HTML 과 CSS)의 작동원리와 거의 비슷합니다.  
제가 React-Native의 레이아웃에 대해 아는 점은, 기본적인 웹 레이아웃에 flex 속성을 대폭 적용시켰다는 것입니다.



## 1. 개발환경 세팅

* **Node.js**  
react-native는 Javascript를 사용하기 때문에 먼저 Node.js를 설치해야 합니다. [Node.js 설치하기](https://nodejs.org/ko/)  
제대로 설치 되어 환경변수까지 적용된 것을 확인하려면 터미널(윈도우는 cmd)에서 아래 명렁어를 쳐서 버전이 제대로 나오는지 확인하시면 됩니다.   
```shell
npm -v
```
​	만약 작동하지 않는다면, Node.js를 설치하지 않으셨거나 Node.js에 대한 환경변수가 등록되지 않은 것 입니다.  
​	작동 안한다면 재설치 해보시고 그래도 안되시면 구글에 각 운영체제에 맞는 검색어로 찾아보시면 될 것 같습니다.    
​	ex. "윈도우 npm 환경변수", "macOS npm 환경변수"

​	앞으로 macOS 관련하여 권한 문제가 발생할 경우, macOS 환경설정의 보안 및 개인 정보 보호로 가셔서, 전체 디스크 접근 권한 등의 탭에서 오류와 관련된 프로그램 (ex. watchman)의 권한에 체크를 해주시면 됩니다.  
구글에 관련 오류를 검색하셔서, 시도해보시는 것도 좋습니다.


* **Visual Studio Code**  
react-native(+expo)의 코드 작성은 Visual Studio Code로 하는 것이 일반적이고 효율적이므로 이것으로 사용해주시기 바랍니다. 참고로 MIT 라이센스이므로 걱정없이 사용하셔도 됩니다. [Visual Studio Code 설치하기](https://code.visualstudio.com/)

* **Expo 설치** 

  기본적인 환경은 전부 갖춰져 있으니, 앞으로 [Expo 공식문서](https://docs.expo.io/)를 참고하여 환경을 세팅하시고 개발을 진행하시면 됩니다.  
  아래 명령어로 npm을 사용해 expo 를 설치해주시면 됩니다.

  ```shell
  npm install --global expo-cli
  ```

  설치가 된지 확인하려면 아래 명령어를 사용해 주시면 됩니다. 설치된 버전이 출력되면 설치 된 것입니다.

  ```shell
  expo --version
  ```

  테스트를 위해 폰으로 [안드로이드 플레이스토어](https://play.google.com/store/apps/details?id=host.exp.exponent)나 [iOS 앱스토어](https://itunes.com/apps/exponent) 에서 expo라 검색하셔서 설치하시면 됩니다.  
  [참고한 문서](https://docs.expo.io/get-started/installation/)

  

  * **Expo 로그인**

  빌드를 위해서는 expo에 로그인 해야 합니다.  
  빌드 뿐만 아니라 편의를 위해 아래 명령어로 expo에 미리 로그인 해두는 것을 권장합니다.

  ```shell
  expo login
  ```

   [Expo 공식문서](https://docs.expo.io/)와 인터넷 검색을 통해 더 자세히 알아보실 수 있습니다.



## 2. Expo 개발 가이드

#### **Expo 프로젝트 만들기**

```shell
expo init example-app
```

터미널에서 "expo init [프로젝트 이름]"을 쳐서 새로운 앱을 만들 수 있습니다.  
blank를 선택하셔서 앱 만드는 걸 진행하시면 됩니다.  
새로운 언어인 TypeScript를 사용하여 앱을 개발할 수도 있긴합니다. (따로 공부해야 합니다.)

프로젝트를 만들고 나면 프로젝트명으로 폴더가 생성됩니다.  
"cd [프로젝트 이름]"을 사용해서 프로젝트 폴더로 이동하셔야 만든 expo 앱에 대해 설정하고 사용할 수 있습니다. ("expo init" 명령어를 사용한 곳에 프로젝트 폴더가 있습니다.)

```shell
cd example-app
```

 아래 명령어 "expo start" 를 사용하셔서 앱을 구동할 수 있도록 해주시면 됩니다.

```shell
expo start 
```

터미널에 QR 코드가 띄어지며 작동하는 모습이 보이면 프로젝트 실행에 성공한 것입니다.
보통 앱을 테스트할 때 "**expo start**"를 사용합니다.  
"expo start" 했을때 나오는 **QR 코드를 카메라로 인식**하거나, expo 앱에서 "expo login" 할때 사용한 **계정으로 로그인**하여 **테스트**하시면 됩니다.  
"expo start"를 하면 임시로 앱을 테스트 할 수 있도록 앱 구성물들을 휴대폰에 전달해주는 서버 기능을 실행시킨 것이라고 보면 될 것 같습니다. 그러므로 테스트 중에 "expo start"를 실행시킨 터미널을 닫으면, 테스트 앱에서 오류가 날 수도 있습니다.  



#### **기존 프로젝트 사용하기**

새로운 expo 프로젝트를 만드는 것보다, 기존에 사용하던 프로젝트를 수정하여 사용하는 것이 덜 번거롭고 편할 것입니다.

파일 탐색기에서 복제하거나, github에 업로드 된 프로젝트를 클론하여 사용하시면 됩니다.  
여기서 [GitHub Desktop](#git--github-활용)으로 클론하여 사용하시는 것을 권장합니다. OS와 환경에 따라 각종 라이브러리들을 다시 설치해야 하는 경우가 많기 때문입니다.   
git에는 직접 라이브러리 파일들이 관리되지는 않고, 아마 package.json만 관리되기 때문에 클론하신 프로젝트 폴더로 가셔서 "npm install" 명령어를 사용하시면 package.json 에 있는 패키지들이 설치될 것입니다.

```shell
npm install
```

혹은

```shell
yarn install
```



#### **Expo 패키지(라이브러리) 설치 및 적용하는 법**

리액트 네이티브에서 사용할 수 있는 여러 패키지들은 쓸 수 없고 expo는 expo에서 제공하는 패키지만 사용가능합니다.  
그러므로 expo로는  [Expo 공식문서](https://docs.expo.io/)에 있는 패키지만 사용할 수 있습니다.

```react
import React, { PureComponent } from 'react';
import { StyleSheet, View, Vibration, BackHandler } from 'react-native';
import { WebView } from 'react-native-webview'
import * as Notifications from 'expo-notifications';
import * as Location from 'expo-location';
...
```

App.js 등 리액트 네이티브 코드가 담긴 파일을 보면 보통 맨 위에 Java에서의 앱개발 처럼, 이런 식으로 되어 있습니다. from 뒤에 있는 "expo-notification", "expo-location" 등이 패키지입니다.

"react"와 "react-native"를 제외하고는, 보통 따로 설치하셔야 사용하실 수 있습니다.   
예시로 "expo-location" 패키지를 설치 및 적용해보겠습니다.

```shell
expo install expo-location
```

터미널을 이용해 프로젝트 폴더로 가셔서 명령어로 "expo install [설치할 패키지 이름]"을 쳐서, 패키지를 설치할 수 있습니다.  


[참고한 문서](https://docs.expo.io/workflow/using-libraries/)





#### Expo의 각 파일들에 대한 설명

* ##### App.js

  워크플로우

  

* ##### app.json

  아이콘 및 스플래시 이미지

  

  

  #### 푸시(알림)

  

## 3. Expo앱 기능들 (모듈)

문서가 길어질 것 같아 모듈은 따로 분리해놓았습니다.

[Expo앱 모듈]() 새로 만들어야 함.



## 4. Expo 빌드 및 스토어에 배포하는법







## 5. 각종 오류 해결 방법



## 6. 기타

1. ##### Git & GitHub 활용

   [GitHub Desktop](https://desktop.github.com/) 을 활용해서 버전관리 및 백업하며 개발하시는 것을 추천합니다.  
   버전 관리, 협업, 백업, 공유 등을 할때 유용합니다.   
   기능 전부를 활용할 필요는 없고, commit과 push만 활용해도 좋을 것 같습니다.  
   [GitHub Desktop 및 Git의 원리 및 개념 강의](https://drive.google.com/drive/folders/1pWc9rQtgLMfXFfIPiscqs8bqubTHii_2?usp=sharing) 를 참고하여 알아보시는 것 추천합니다.  
   그리고 보안을 위해 회사 웬만하면 public 말고, private으로 해두시길 권장합니다.  
   i-web 깃허브 : https://github.com/iwebzone (아직 안 만듬.)

   

   

2. ##### 깃허브 마크다운 문서 작성 방법 참고

   (한글) https://gist.github.com/ihoneymon/652be052a0727ad59601  
   (영문) https://guides.github.com/features/mastering-markdown/  
   **typora** 란 프로그램 사용하셔서 마크다운 수정하시면 편합니다.  (이 프로그램 사용할시 띄어쓰기는 shift + Enter)

   

3. ##### Expo 개발 웹 IDE, Snack

   Expo 관련하여 구글링 하다가 보면 

