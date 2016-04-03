# 앱 자동 설치 리소스 안내

## 개발시 주의사항

common.conf 등의 nginx 설정 파일은 실행중인 nginx 에 연동되도록 되어 있습니다.

따라서 이미 배포된 common.conf 등의 기존 수정 파일을 수정을 피해야 합니다.

심각한 오류나 보안 위협이 있을 경우에만 수정하며, 기존 사용자에게 공지가 가능해야 합니다.


## 리소스 구조

### install.sh

- 앱 자동 설치 스크립트


### update.sh

- 앱 자동 업데이트 스크립트

- PhpMyAdmin 은 관리용도로만 사용되므로, git 기반 업데이트를 지원합니다.

- 그누보드5, XE1 는 시험적인 목적으로 git 기반의 업데이트를 적용하였으나, 개발사의 정책에 따라 오류가 발생하거나 불가할 수 있습니다.
 - 특히 소스를 수정한 경우에는 git 기반의 업데이트가 어렵습니다.

- Laravel 은 프레임워크이므로 설치후에 반드시 수정을 거치게 되고, 별도 composer 로 관리해야 하므로 업데이트를 지원하지 않습니다.

- WordPress 는 관리자모드에서 업데이트 가능하므로 지원하지 않습니다.


### template-server.conf

- 앱 자동 설치시, nginx 에 추가될 도메인 단위의 설정 템플릿입니다.


### common.conf

- 0.9.8 버전까지 template-server.conf 에서 기본 include 되던 권장 설정입니다.

- 0.9.8 버전에서 추가된 사이트의 하위 호환성 확보를 위해 유지합니다.  변경 사유: #2


