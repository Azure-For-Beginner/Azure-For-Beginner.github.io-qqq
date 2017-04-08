---
layout: post
title: "쉽게 배우는 Web App 2 : Web Application를 만들어 보자!"
tag: [webapp]
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
	* Node.js
		1. 다음창에서 `기본 Azure Node.js Express 4 응용 프로그램`을 선택합니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/create_project.PNG)
		2. 프로젝트가 만들어지면 프로젝트에서 마우스 오른쪽 클릭 `게시`를 선택합니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_publish.png)
		3. 다음과 같이 나오면 `Microsoft Azure 앱 서비스`를 선택합니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/publish_option.PNG)
		4. 계정을 연동하면 다음과 같이 Azure에 만들어둔 웹 앱을 검색할 수 있고, 적당한것을 선택하여 웹 앱을 게시합니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_account.PNG)
		5. 다음과 같이 나오면 바로 게시를 눌러주면 쉽게 Azure 서버에 올릴 수 있습니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_complate.PNG)
		6. 게시가 완료되면 서버가 자동으로 실행되면서 결과를 확인할 수 있습니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/webapp.png)
	* Python
		1. Python은 Flask를 이용하여 Webapp을 구성해보겠습니다. 그리고 Visual Studio Professional 2017에는 아직 정식으로 Python개발 도구가 등록되지 않아 Visual Studio Code로 진행하겠습니다.
		2. Visual Studio Code를 실행시켜 다음과 같이 구성합니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/visual-studio-code.PNG)
        		* `ptvs_virtualenv_proxy.py`은 Azure서버가 Windows 서버이기 때문에 virtualenv의 설정을 하기위한 파일입니다.
        		* `requirements.txt`은 현재 Flask에서 필요한 모듈들을 다운받기 위해 사용하는 파일입니다. 여기에 모듈이름을 입력하고 `pip install -r requirements.txt`를 입력하면 입력된 모듈이 전부 설치됩니다.
        		* `runtime.txt`는 서버로 사용하고 싶은 python의 version을 입력합니다. `python-2.7`과 `python-3.4`가 있습니다.
        		* `web.x.y.config`는 Windows 서버에 설정을 잡아주기 위한 설정파일입니다. x와 y는 python의 version을 나타냅니다.
		3. 그리고 프로젝트를 Github에 푸쉬합니다.
		4. 다시 Azure Webapp으로 돌아와서 배포 옵션으로 들어갑니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/webapp_github.png)
		5. 설정버튼을 눌러 Github 레포지토리와 연동합니다.
		![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-github.png)
        6. 알맞게 본인 설정을 입력합니다.
        ![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-github-select.PNG)
        7. 설정이 완료되면 확인버튼을 누르고 동기화를 진행합니다.
        ![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-sync.PNG)
        8. 동기화가 완료되면 다음과 같이 서버가 완성됩니다.
        ![그림](https://azureforbeginner.blob.core.windows.net/images/python-server.PNG)

# 참고
* [https://docs.microsoft.com/ko-kr/azure/app-service-web/app-service-web-nodejs-get-started](https://docs.microsoft.com/ko-kr/azure/app-service-web/app-service-web-nodejs-get-started)
* [https://docs.microsoft.com/ko-kr/azure/app-service-web/web-sites-nodejs-develop-deploy-mac](https://docs.microsoft.com/ko-kr/azure/app-service-web/web-sites-nodejs-develop-deploy-mac)
* [https://docs.microsoft.com/ko-kr/azure/app-service-web/web-sites-python-configure](https://docs.microsoft.com/ko-kr/azure/app-service-web/web-sites-python-configure)
* [https://docs.microsoft.com/ko-kr/azure/app-service-web/web-sites-python-create-deploy-flask-app](https://docs.microsoft.com/ko-kr/azure/app-service-web/web-sites-python-create-deploy-flask-app)
