# expo 명령어 및 개발 환경



### node.js 및 npm 설치

윈도우

[공식 사이트](https://nodejs.org/ko/)에서 안정적, 신뢰도 높음 버전 설치. 

맥 os

```
brew install node
```



### expo 설치

```
npm install -g expo-cli
```



- yarn 이 없다면 (macos)

  ```
  brew install yarn
  ```



### package.json 에 있는 라이브러리 다시 설치

```
npm install
expo install
```





### [중요] 앱 출시를 위한 앱 빌드 및 apk & 앱번들(안드로이드), IPA(iOS) 파일 생성.

- 안드로이드 apk 파일 및 app-bundle 빌드

  ```
  expo build:android --release-channel 채널명(영어로) 
  ```

- iOS ipa 파일 빌드

  ```
  expo build:ios --release-channel 채널명(영어로) 
  ```

  

--release-channel 뒤에 쓴 채널명을 기준으로 OTA(Over The Air) 업데이트를 시행한다. 

채널명이 똑같은 것만 업데이트 되기 때문에, 테스트용 앱과 마켓 출시용 앱의 **채널을 따로 분리해서 빌드해야 한다**.





예를 들면, 

- 안드로이드 테스트용 apk 파일 빌드

  ```
  expo build:android --release-channel test
  ```

- 안드로이드 플레이 스토어용 apk 파일 빌드

  ```
  expo build:android --release-channel play-store
  ```

- iOS도 이와 동일한 방식으로 업데이트 채널을 변경하면 된다 (앱스토어용 채널명)

  ```
  expo build:ios --release-channel app-store
  ```



**테스트**용 앱을 설치하기 위해서는, 안드로이드의 경우 [expo 사이트](https://expo.io/)에 로그인하여 빌드된 apk 파일을 다운받아 그냥 설치하면 되고, iOS의 경우 App Store에 IPA 파일을 [Transporter](https://apps.apple.com/kr/app/transporter/id1450874784?mt=12)를 사용하여 올려 테스트 플라이트[(TestFlight)](https://developer.apple.com/kr/testflight/) 를 활용하면 된다. 





### [중요] 키 관리





