# CRUD
<>는 변수를 넣는곳 입니다

1.프로제트 폴더 생성
2.프로젝트 폴더로 이동 /vscode 실행
    2.1 '.gitignire' 'REAdME.md' 생성
3.django 프로젝트 생성
```bash
django-admin startproject <pjt-name> .
```

4. 가상환경 설정
```bash
python -m venv venv
```

5. 가상환경 활성화
```bash
source venv/Scripts?activate
```
6. 가사완경에 django설치
```bash
pip install django
```

7. 서버 실행 확인
```bash 
python manage.py runserver
```

8. 앱 생성
```bash
django-admin startapp posts
```




# Model
1, 'models.py'
    -모델의 이름은 기본적으로 단수형태
```python
from django.db import models
class Post(models.Model):
    title=models.CharField()
    content=models/TextField()
```

2.번역본 생성
```bash
python manage.py makemigrations
```

3.DB에 반영 
```bash
python manage.py migrate
```

4.SQL 스키마 확인
```bash
python manage.py sqlmigrate posts 0001

5.생성한 모델 admin 등록

```bash
from django.contrib import admin
from .models import Post
# Register your models here.

admin.site.register(Post)
```
6.관리자 계정 생성

```bash
python manage.py createsuperuser
```

## CRUD 로직 작성

### 1.Read

-전체 게시물 출력
```python
def index(request):
    posts = Post.objects.all()

    context= {
        'posts':posts,
              }



    return render(request, 'index.html', context)
```
### 2. Create
### 3. Delete
### 4. Update