# JARVIS - webOS OSE 기반 커넥티드 카 공유 모빌리티 서비스

## JARVIS 설치 방법

### 1. 앱 소스코드 다운로드
```
$ git clone https://github.com/skhu-rora/com.app.rora.git && git clone https://github.com/skhu-rora/com.app.rora.service.biometrics.git && git clone https://github.com/skhu-rora/com.app.rora.service.carcontrol.git && git clone https://github.com/skhu-rora/com.app.rora.service.webcontrol.git
```
### 2. 앱 및 서비스 패키징
```
$ ares-package com.app.rora com.app.rora.service.webcontrol/ com.app.rora.service.biometrics/pkg_arm/ com.app.rora.service.carcontrol/pkg_arm/
```

### 3. webOS에 앱 설치
```
$ ares-install -d [webOS ID] com.app.rora_[version]_all.ipk     // ex) ares-install -d target com.app.rora_1.0.2_all.ipk
```