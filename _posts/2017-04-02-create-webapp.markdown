---
layout: post
title: "쉽게 배우는 Web App 2 : Web Application를 만들어 보자!"
date: "2017-04-02 04:02:38"
categories: Azure Web Applcation
---

# Web App 만들기
1. 먼저 [Azure Potal](https://portal.azure.com)에 접속해 로그인을 진행합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/login.png)
2. 로그인이 성공하면 다음과 같은 화면이 나오게 됩니다. 이제 왼쪽 윗 부분에 있는 새로만들기를 클릭합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/login_success.png)
3. 다음과 같은 화면에서 `웹 + 모바일 -> 웹앱`을 클릭합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_menu.png)
4. 그러면 다음과 같이 나오게 됩니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/create_webapp.png)
	* 앱 이름은 사이트 주소에 해당합니다.(개인적인 도메인이 있으면 연동이 가능합니다.)
	* 구독은 Azure Credit에 해당합니다.
	* 리소스 그룹은 Azure에서 만든 웹앱이나 VM이나 데이터베이스등을 편하게 관리하기 위해 만든 그룹입니다.(자세한 내용 [Azure Resource Group](https://docs.microsoft.com/ko-kr/azure/azure-resource-manager/resource-group-overview))
	* App Service는 지금 만드는 리소스를 어느 지역에 할당할지와 가격을 고를 수 있습니다.(최근 선택할 수 있는 지역에 한국이 생겼습니다.)
	* 다음 사진은 빈칸을 모두 채운 사진입니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/create_webapp_success.png)
5. 확인을 선택하면 다음과 같이 배포 중인걸 확인할 수 있습니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_creating.png)
6. 배포가 완료되면 다음과 같은 화면을 볼 수 있습니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_success.png)
7. 이제 Visual Studio Professional 2017을 사용하여 웹앱을 배포해보겠습니다. Visual Studio Professional 2017를 실행시키고 `파일 -> 새로 만들기 -> 프로젝트`를 선택합니다.
8. 다음창에서 `기본 Azure Node.js Express 4 응용 프로그램`을 선택합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/create_project.PNG)
9. 프로젝트가 만들어지면 프로젝트에서 마우스 오른쪽 클릭 `게시`를 선택합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_publish.png)
10. 다음과 같이 나오면 `Microsoft Azure 앱 서비스`를 선택합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/publish_option.PNG)
11. 계정을 연동하면 다음과 같이 Azure에 만들어둔 웹 앱을 검색할 수 있고, 적당한것을 선택하여 웹 앱을 게시합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_account.PNG)
12. 다음과 같이 나오면 바로 게시를 눌러주면 쉽게 Azure 서버에 올릴 수 있습니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_complate.PNG)
13. 게시가 완료되면 서버가 자동으로 실행되면서 결과를 확인할 수 있습니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp.png)

# 알고있으면 좋은 팁
## Github 연동
1. 앱 배포 메뉴로 가면 배포 옵션이라는 메뉴가 있습니다. 이 메뉴를 사용하면 로컬 Git 레포지토리나 Github에 있는 레포지토리를 연동할 수 있습니다. Github과 같은 경우는 push 메시지가 들어오면 Azure가 자동으로 인식해서 자동으로 배포를 진행하게 됩니다. 그 외에도 Visual Studio Team Service나 Dropbox, Bitbucket 등 다양하게 있습니다. 가장 많이 쓰이는 Git을 이용하겠습니다.
2. 설정하는 방법은 다음과 같습니다.
	* 로컬 Git 레포지토리
	* Github

# 참고
* [https://docs.microsoft.com/ko-kr/azure/app-service-web/app-service-web-nodejs-get-started](https://docs.microsoft.com/ko-kr/azure/app-service-web/app-service-web-nodejs-get-started)
* [https://docs.microsoft.com/ko-kr/azure/app-service-web/web-sites-nodejs-develop-deploy-mac](https://docs.microsoft.com/ko-kr/azure/app-service-web/web-sites-nodejs-develop-deploy-mac)