---
layout: post
published: true
title: Fenrir Development Review
tag: digital_forensic
subtitle: Live System Forensic Library
date: '2018-02-15'
bigimg: /img/fenrir.PNG
header-img: /img/fenrir.PNG
---
## Overview


Digital Forensic 관련으로 [존경하는 고수](https://www.linkedin.com/in/deok9/)님께서 학생들을 위해 과제를 출제하셨다길래 어떤 과제인지 궁금중인지 들어 확인해보았다. 큰 주제는 "활성 시스템 정보 유출 분석 도구 개발"이었다.


최근에 NIST Data Leakage Data들을 이용해서 내부 데이터 유출에 관련한 국세청 강의 자료도 만들고.. 수상은 하지 못했지만 제 5회 디지털 범인을 찾아라 경진대회에서도 악성코드와 원격 접속을 활용한 내부 정보 유출 Case를 다뤄볼 수 있었다. 해당 Case들을 다뤄보면서 느낀 점은 아래와 같다.

1. 눈에 띄는 악성행위가 존재하지 않는다.
2. 유출 수단 및 Vector가 너무 다양하다.
3. 

`Live System` 상에서 Digital Forensic을 진행할 수 있게 해주는 도구를 개인적으로 개발하고 있던 와중, 이와 관련된 자료로 Mattia Epifani이라는 분께서 SANS Forensics Prague Summit & Training 2013에서 발표한 [Cloud Storage Forensics](hhttps://digital-forensics.sans.org/community/summits)라는 자료에 대부분나와있기는 하지만, 꽤나 업데이트가 진행된 상황이라 다른 부분이 어느정도 존재한다. 그래서 

## Artifact 수집 방안


- 파일을 구글 드라이브에 업로드하였을 때 `snapshot.db`  


- 구글 드라이브에서 파일을 삭제하였을 때 `snapshot_sync.log`  


- 로컬 폴더에서 파일을 삭제하였을 때 (  


- 구글 드라이브에 새로운 파일이 추가되었을 때  
- 구글 드라이브를 설치하였을 때  
- 구글 드라이브를 삭제하였을 때  
- 외장하드에 대하여 드라이브를 개설하였을 때 (Drive 정보 확인해야함)  

## 실험 및 수행 환경


## 기본 정보

- 계정 정보, 설치 일시, 설치 경로, 프로필 갯수 등

## 사용자 정보



## 저장된 파일

- 로컬 파일 서칭

## 삭제되었다?

- 파일이 삭제되었는가?
- 드라이브 클라이언트 자체를 제거하였는가?

## 시나리오 구성


## 파일 카빙

- 해당 mft로 들어간다
- 해당 mft로 들어간다

## SQLite 카빙

## USB Information

Prefetch, Windows Event Log, Registry

## Email

Windows 10, Outlook, Thunderbird

## Visualization Method

PyQt5 or Web (Flask)

Enter text in [Markdown](http://daringfireball.net/projects/markdown/). Use the toolbar above, or click the **?** button for formatting help.
