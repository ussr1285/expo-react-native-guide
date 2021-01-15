# Expo(리액트 네이티브) 가이드
깃허브 마크다운 문서 작성 방법 참고:   
(한글) https://gist.github.com/ihoneymon/652be052a0727ad59601  
(영문) https://guides.github.com/features/mastering-markdown/



## 1. 개발환경 세팅
* **Node.js**  
react-native는 Javascript를 사용하기 때문에 먼저 Node.js를 설치해야 합니다. [Node.js 설치하기](https://nodejs.org/ko/)  
제대로 설치 되어 환경변수까지 적용된 것을 확인하려면 터미널에서 아래 명렁어를 쳐서 버전이 제대로 나오는지 확인하시면 됩니다.   
```shell
npm -v
```
​	만약 작동하지 않는다면, Node.js를 설치하지 않으셨거나 Node.js에 대한 환경변수가 등록되지 않은 것 입니다.  

​	작동 안하신다면 재설치 해보시고 그래도 안되시면 구글에 각 운영체제에 맞는 검색어로 찾아보시면 될 것 같습니다.  

​	ex. "윈도우 npm 환경변수", "macOS npm 환경변수"  

​	앞으로 macOS 관련하여 권한 문제가 발생할 경우, macOS 환경설정의 보안 및 개인 정보 보호로 가셔서, 전체 디스크 접근 권한 등의 탭에서 오류와 관련된 프로그램 (ex. watchman)의 권한에 체크를 해주시면 됩니다.

​	구글에 관련 오류를 검색하셔서, 시도해보시는 것도 좋습니다.


* **Visual Studio Code**  
react-native(+expo)의 코드 작성은 Visual Studio Code로 하는 것이 일반적이고 효율적이므로 이것으로 사용해주시기 바랍니다. 참고로 MIT 라이센스이므로 걱정없이 사용하셔도 됩니다. [Visual Studio Code 설치하기](https://code.visualstudio.com/)

* **Expo 설치**  

  기본적인 환경은 전부 갖춰져 있으니, 앞으로 [Expo 공식문서](https://docs.expo.io/)를 참고하여 환경을 세팅하시고 개발을 진행하시면 됩니다.  

  ```
  df
  ```

  

  

  

  

  공식문서와 인터넷 검색을 통해 더 자세히 알아보실 수 있습니다.





## 2. Expo 개발 가이드
* **1-1. Expo 개발 관련 참고 사이트**  
expo는 expo에서 제공하는 패키지만 사용가능합니다.
리액트 네이티브에서 사용할 수 있는 여러 패키지들은 expo에서는 사용할 수 없다고 보면 됩니다.
그러므로 expo에서 제공한 공식문서에 없는 패키지는 쓸 수 없다고 보시면 됩니다.

expo 공식 문서 : https://docs.expo.io/


## 3. Expo 빌드 및 스토어에 배포







## 4. 각종 오류 해결 방법

