---
layout: post
title: "쉽게 배우는 Web App 3 : Web App에 Stroage를 연결해보자!"
tag: [webapp]
---

1. 새로만들기를 클릭합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/login_success.png)
2. `Storage -> Storage account - blob, file, table, queue`를 클릭합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-srotage.PNG)
3. 다음과 같이 입력하고 확인을 클릭합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/storage-create.PNG)
	* 이름에는 소문자와 숫자만 올 수 있습니다.
	* 배포 모델은 Storage에서 관리될 자원들을 묶어서 관리할 방법을 설정합니다. Resource Manager로 설정합니다.
	* 계정 종류는 어떤 데이터가 저장될지 설정하는 곳입니다. 범용 저장소는 테이블, 큐, 파일, Blob, Azure 가상 컴퓨터 등 서비스에 액세스 할 수 있습니다. Blob는 범용과 다르게 구조화되지 않은 데이터를 저장하기 위한 곳입니다.
	* 복제는 데이터가 없어질 때를 위해 다른 곳에 복제합니다.
	* 저장소 서비스 암호화는 많이 사용되지 않은 파일들을 암호화해서 관리할 것인지 설정하는 곳입니다.
4. 만들고면 다음과 같은 화면이 나오는대 여기서 만들고 싶은것을 클릭합니다. 저는 Blob 저장소를 만들어 보겠습니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-blob.png)
5. 파일을 저장하기위한 컨테이너를 추가합니다
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-create-container.png)
	* 액세스 형식은 이 저장소를 어디까지 접근할 수 있을지 정하는 곳입니다.
6. 확인을 누르면 바로 생성이 되고 파일을 업로드 할 수 있는 공간이 나옵니다. 위쪽 메뉴에 업로드로 파일을 업로드 할 수 있고 여러가지 언어로 파일을 업로드 할 수 있습니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-file-upload.png)
7. 업로드를 완료하면 다음과 같이 URL을 통해 파일에 접근할 수 있습니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-upload-success.png)
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-storage-success.png)
8. 메뉴에 액새스 이름과 키를 메모합니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-storage-key.png)
9. 이제 전에 만들어둔 웹앱을 이용해서 이미지를 띄워보겠습니다. Python 코드에서 runserver.py를 다음과 같이 변경합니다.
	```
	from FlaskWebProject1 import app
	from azure.storage.blob import BlobService
	from flask import redirect
	
	def azureStorageList():
	    urlPath = None
	    block_blob_service = BlobService(account_name='yourstorageaccountname',
	                                     account_key='yourstorageaccountkey')
	
	    generator = block_blob_service.list_blobs('yourstorageaccountname')
	    for blob in generator:
	        urlPath = block_blob_service.make_blob_url('yourstorageaccountname', blob.name)
	
	    return urlPath
	
	@app.route('/')
	def home():
	    """Renders the home page."""
	    return redirect(azureStorageList())
	```
10. 그러면 다음과 같이 볼 수 있습니다.
![그림](https://azureforbeginner.blob.core.windows.net/images/webapp-storage-webapp.png)

# 참고
* [https://docs.microsoft.com/ko-kr/azure/storage/storage-introduction](https://docs.microsoft.com/ko-kr/azure/storage/storage-introduction)
* [https://docs.microsoft.com/ko-kr/azure/azure-resource-manager/resource-manager-deployment-model](https://docs.microsoft.com/ko-kr/azure/azure-resource-manager/resource-manager-deployment-model)
* [https://docs.microsoft.com/ko-kr/azure/storage/storage-service-encryption](https://docs.microsoft.com/ko-kr/azure/storage/storage-service-encryption)
* [https://docs.microsoft.com/ko-kr/azure/storage/storage-python-how-to-use-blob-storage](https://docs.microsoft.com/ko-kr/azure/storage/storage-python-how-to-use-blob-storage)
