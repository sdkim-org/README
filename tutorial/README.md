## 1. Github Repository Setting

<img width="1280" alt="sdk-typora01" src="https://user-images.githubusercontent.com/13485924/73136119-56db4b00-408d-11ea-9f87-ca652e385e1e.png">

- 본인의 Github Repository 에 방문 후 우측 상단의 **+** 버튼 클릭 후 **New repository** 클릭을 하면 위의 화면으로 이동합니다.
- Repository name 을 입력 후 하단의 **Create repository** 버튼을 클릭

<br>

<img width="806" alt="sdk-typora02" src="https://user-images.githubusercontent.com/13485924/73136150-d6691a00-408d-11ea-9f4c-0808df1838db.png">

- **Create repository** 버튼 클릭시 위와 같은 화면으로 이동을 합니다. 
- 위의 화면에서 보이는 `https://github.com/sdkim-org/README.git` 주소를 복사해둡니다.

<br>

Mac 의 경우 터미널을, Windows 의 경우 git-bash 를 open 합니다.

임의의 workspace 를 생성 후 위의 Repository 를 clone 합니다.

```
$ mkdir workspace
$ cd workspace
$ git clone https://github.com/sdkim-org/README.git
```

- 위에서 복사해 둔 Repository 주소를 clone 합니다.
- clone 을 하게 되면, Repository name 으로 폴더가 생성이 되어 있습니다. 여기서는  **README** 란 이름 Repository name 에 해당합니다.

```
$ cd README
```

- 해당 폴더로 이동 합니다. 

<br>

**Git 초기설정**

```
$ git config --global user.name "<사용자명>"
$ git config --global user.email "<메일 주소>"
```

- 나중에 commit 을 할 때 위에서 설정한 사용자 이름과 이메일이 기록됩니다.

<br>

## 2. Markdown 문서 Push

위에서 clone 한 Repository 내에서 원하는 디렉토리를 생성 후 Typora 로 작업한 markdown 파일을 `README.md` 파일명으로 생성한 디렉토리에 저장합니다.

```
$ pwd
/Users/Username/workspace/README
$ mkdir tutorial
$ cd tutorial
$ ls
```

- 여기서는 `tutorial` 라는 디렉토리를 생성 후 해당 디렉토리에 markdown 파일을 생성하겠습니다.
- 파일명은 README.md 입니다.

```
$ pwd
/Users/Username/workspace/README/tutorial
$ ls
README.md
```

<br>

#### Remote Repository 에 push 하기

```
$ git add README.md
$ git commit -m "commit message"
$ git push origin master
Username: <사용자명>
Password: <비밀번호>
```

- `git push -u origin master` 는 origin 이라는 이름의 원격 저장소에 master 브랜치를 push 하겠다는 의미이며, origin 은 최초 클론을 하면서 자동으로 붙여진 이름입니다. (`git remove -v` 를 통해 확인 가능합니다.)
- 최초 push 진행시 Gitgub 의 Username 과 Password 입력을 해주시면 됩니다.

<br>

이제 브라우저에서 위에서 생성한 Github 레파지토리의 해당 디렉토리로 이동하면 markdown 문서로 작성한 내용이 렌더링되어 있는 것을 확인할 수 있습니다.

<br>

## 3. Markdown 문서 작성시 image 삽입 Tip.

<img width="870" alt="sdk-typora03" src="https://user-images.githubusercontent.com/13485924/73137804-74b1ab80-409f-11ea-8e3a-6bee0a876e4f.png">

- 임의의 Repository 에서 **Issues 탭**을 선택합니다. 
- 그 다음 **New Issue** 버튼을 클릭합니다.

<br>

<img width="797" alt="sdk-typora04" src="https://user-images.githubusercontent.com/13485924/73137840-ceb27100-409f-11ea-844e-71a20c6b82e2.png">

- 위의 화면으로 이동이 되는데, 이 때, image 파일을 **Leave a comment** 란에 Drag & Drop 을 합니다.

<br>

<img width="748" alt="sdk-typora05" src="https://user-images.githubusercontent.com/13485924/73137877-16d19380-40a0-11ea-9ba6-cf6c04ac3d1b.png">

- 이미지 파일을 가져다 올려놓고 나면, 위와 같은 메세지를 확인할 수 있습니다. (그리고 기다립니다.)

<br>

<img width="772" alt="sdk-typora06" src="https://user-images.githubusercontent.com/13485924/73137876-16d19380-40a0-11ea-8456-30d1b0c272be.png">

- 어느정도 기다리고 나면, 위와 같이 image 가 업로드된 주소가 포함된 img 태그를 얻게 됩니다.

- 위의 태그를 통채로 복사 후 이곳에 붙여 넣으면 됩니다.

- image 가 업로드 된 주소는 절대경로이기 때문에, 원본 이미지를 따로 업로드 할 필요가 없습니다.

- 이미지 사이즈는 width 속성의 값을 변경하여 조절 가능합니다.

- 이 md 파일을 raw 문서로 확인하면, 이미지 위치에 위와 같은 태그들을 확인하실 수 있습니다.

- 그 외 html 태그가 호환이 되기 때문에, 이미지를 가로로 배치하고 싶은 경우, 아래와 같이 입력하시고 사이즈를 조정하면 가능합니다.

  ```html
  <table>
  	<tr>
  		<td><img width="374" alt="sdk-typora05" src="https://user-images.githubusercontent.com/13485924/73137877-16d19380-40a0-11ea-9ba6-cf6c04ac3d1b.png"></td>
      <td><img width="374" alt="sdk-typora06" src="https://user-images.githubusercontent.com/13485924/73137876-16d19380-40a0-11ea-8456-30d1b0c272be.png"></td>
  	</tr>
  </table>
  ```

  <table>
  	<tr>
  		<td><img width="374" alt="sdk-typora05" src="https://user-images.githubusercontent.com/13485924/73137877-16d19380-40a0-11ea-9ba6-cf6c04ac3d1b.png"></td>
      <td><img width="374" alt="sdk-typora06" src="https://user-images.githubusercontent.com/13485924/73137876-16d19380-40a0-11ea-8456-30d1b0c272be.png"></td>
  	</tr>
  </table>

- 위의 코드를 그대로 붙여넣은 결과입니다.

