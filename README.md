# JARVIS - webOS OSE 기반 커넥티드 카 공유 모빌리티 서비스

## JARVIS 설치 방법

## 개발 PC에서 install
### 1. JARVIS App(서비스 포함) 소스코드 다운로드
```
git clone https://github.com/2020ESWContest-webOS-4004/com.app.rora.git && git clone https://github.com/2020ESWContest-webOS-4004/com.app.rora.service.biometrics.git && git clone https://github.com/2020ESWContest-webOS-4004/com.app.rora.service.carcontrol.git && git clone https://github.com/2020ESWContest-webOS-4004/com.app.rora.service.webcontrol.git
```

### 1.2. Node.js 패키지 설치
```
cd com.app.rora.service.webcontrol && npm install && cd ..
```

### 1.3. Native Service 크로스 컴파일 - 차량제어 모듈(com.app.rora.service.carcontrol)
```
cd com.app.rora.service.carcontrol && mkdir BUILD && cd BUILD && cmake .. && make && cd ../../
```

### 1.4 Native Service 크로스 컴파일 - 생체인증 모듈(com.app.rora.service.biometrics)
```
cd com.app.rora.service.biometrics && mkdir BUILD && cd BUILD && cmake .. && make && cd ../../
```

### 2. 앱 및 서비스 패키징
```
ares-package com.app.rora com.app.rora.service.webcontrol/ com.app.rora.service.biometrics/pkg_arm/ com.app.rora.service.carcontrol/pkg_arm/
```

### 3. webOS에 앱 설치
```
ares-install -d [webOS ID] com.app.rora_[version]_all.ipk     // ex) ares-install -d target com.app.rora_1.0.2_all.ipk
```
