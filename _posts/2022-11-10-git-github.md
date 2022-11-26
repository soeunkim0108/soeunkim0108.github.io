---
layout: post
title: "Git & Github"
categories: jekyll update
comments: true
---

## Git

> 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 **분산 버전 관리 시스템**.

<br>

### 버전 관리 시스템

- **변경점 관리**: 어떤 내용을 누가 작성해서 어느 시점에 들어갔는지 확인할 수 있게 해준다.
- **버전 관리**: 특정 시점에 꼬리표(tag)를 달아 버전을 표시해주고, 브랜치(branch) 등으로 동시에 여러 버전을 개발 할 수 있게 해준다.
- **백업&복구**: 무언가가 잘못되었을 때 다시 특정 시점으로 돌아가게 해주고, 사고로 내용이 날아간 경우에도 복구할 수 있게 해준다.
- **협업**: 같이 일하는 사람들과 수정사항을 쉽게 공유할 수 있게 해준다.

<br>

### Git 장점

- 병렬 개발 가능.
- 소스코드의 수정 내용은 커밋이라는 단위로 관리, 패치라는 형식으로 배포 
→ 프로그램의 변동 과정을 체계적으로 관리 가능.
- 분산 버전 관리이기 때문에 인터넷이 연결되지 않은 곳에서도 개발 진행 가능.
- 중앙 저장소가 날라가 버려도 원상복구 가능.

<br>

### Git Process Flow 
![git process flow](/assets/gitbook/images/git-process-flow.png)  

`git init`이나 `git clone`으로 프로젝트를 생성하면, 해당 프로젝트는 로컬저장소가 되며, 3가지의 상태로 흐름이 생긴다.  

`working directory`상태는 새로 생성된 파일이나 기존에 추적 중이던 파일을 나타낸다. `git add` 명령어를 통해 `staging area` 상태로 변경이 가능하다.  

`staging area` 상태는 로컬저장소에 변경된 내용을 확정짓기 전에 임시적으로 대상을 넣어놓은 상태를 말한다. `git commit` 명령어를 통해 `local repo` 상태로 변경할 수 있다.  

`local repo` 상태는 변경된 내용을 로컬저장소에 저장하고, 스냅샷을 만들어 파일들의 변화를 관리할 수 있게 해주는 상태를 말한다. `git push`를 통해 원격저장소에 로컬저장소 내용을 반영하거나, `git pull`을 통해 원격저장소의 내용을 로컬저장소에 반영할 수 있다.  

<br>

### File Life Cycle
![file life cycle](/assets/gitbook/images/file-life-cycle.png)  

`working directory` 상태와 `staing area` 상태를 좀 더 상세하게 표시하면 위의 사진처럼 표현할 수 있다.  

`untracked` 상태는 파일을 새로 생성했지만, 아직 관리 대상이 아님을 나타낸다. `git add` 명령어와 `git commit` 명령어로 로컬저장소에 저장을 확정지어야 `unmodified` 상태로 변경되며 파일 추적의 대상이 된다.  

`unmodified` 상태는 로컬저장소에 저장되어 파일 추적의 대상이 된 상태를 말한다. 파일을 수정하면 `modified` 상태로 변경된다.  

`modified` 상태는 추적 중인 파일의 변화가 감지될 때 대상이 변경된 상태임을 알려주는 상태이다. `git add` 명령어를 통해 `staged` 상태로 변경시킬 수 있다.  

`staged` 상태는 로컬저장소에 변경된 내용을 확정짓기 전에 임시적으로 대상을 넣어놓은 상태를 말하며 상단 그림의 `staging area` 와 같다. `git commit` 명령어를 통해 로컬저장소에 저장하면 모든 대상 파일이 `unmodified` 상태로 변경된다.

<br>

### Git 기본 용어

- **Repository**: 저장소를 의미. 저장소는 히스토리, 태그, 소스의 가지치기 혹은 branch에 따라 버전을 저장. 저장소를 통해 작업자가 변경한 모든 히스토리 확인 가능.
- **Working Directory** : 현재 작업 중인 Git 프로젝트 파일들이 있는 내 PC의 디렉터리.
- **Staging Area**: 커밋할 변경 내역들의 대기 장소.
- **Local Repository**: 커밋들이 스냅샷으로 기록된 곳.
- **Remote Repository**: 로컬 PC를 넘어 원격 서버에서 관리되는 저장소.
- **Origin**: 원격 저장소에 있는 코드.
- **Head**: 현재 작업중인 Branch.
- **Branch**: 가지 또는 분기점을 의미. 작업을 할때에 현재 상태를 복사하여 Branch에서 작업을 한 후에 완전하다 싶을때 Merge를 하여 작업.
- **Add**: Working Directory에서 Staging Area로 등록.
- **Commit**: 다른 Branch의 내용을 현재 Branch로 가져와 합치는 작업.
- **Commit message**: commit시 함께 작성해 저장하는 메시지.
- **Push**: Local Storage에서 변경된 파일들을 Remote Repository로 등록.
- **Merge**: Branch의 내용을 현재 Branch로 가져와 합치는 작업.

<br>


### Git 주요 명령어

- **저장소 생성**
```cmd
git init
```
- **원격 저장소 복제**
```cmd
git clone <원격 저장소 주소> <내가 사용할 디렉터리 이름>
```
- **현재 상태 확인**
```cmd
git status
```
- **현재 상태 추적**  
새로 생성되거나 수정한 파일을 추적하도록 명령  
```cmd
git add <파일명 or . or *>
```
- **현재 상태 저장**
```cmd
git commit -m "메시지"
```

- **원격 저장소에 업로드**
```cmd
git push origin <브랜치 이름>
```

- **이력 확인**
```cmd
git log
```

- **브랜치 관리**
```cmd
# 로컬 branch 목록 확인
git branch
# <브랜치 명>이라는 branch 생성
git branch <브랜치 명>
```

- **브랜치 변경 및 워킹 트리에서 변경점 복원**
```cmd
# <브랜칭 명>으로 branch 변경
git checkout <브랜치 명>  
# Unstaged 상태의 파일을 원래대로 되돌림
git checkout -- [파일 명]
```

<br>
<br>

## Github
> 분산 버전 관리 툴인 Git을 사용하는 프로젝트를 지원하는 **웹호스팅 서비스(클라우드)** 

<br>

### Github 장점

- 원격 저장소에서 Git 사용 가능.
- 지역 저장소 백업 가능.
- 협업 프로젝트에서 사용 가능.
- 자신의 개발 이력을 남길 수 있음.
- 다른 사람의 소스를 살펴볼 수 있고, 오픈 소스 참여 가능.

<br>

### Github 사용법

1. Github 계정 등록
→ [github.com](https://github.com/)  

2. Github 저장소 생성
![github repository 생성](/assets/gitbook/images/github-repository.png)  
![github repository 생성](/assets/gitbook/images/create-repository.PNG)  

3. GitBash 혹은 터미널 접속하여 로컬-원격 저장소 연결
![github repository 주소](/assets/gitbook/images/repository-address.PNG)  

```cmd
git init
git remote add origin <저장소 주소>
```

