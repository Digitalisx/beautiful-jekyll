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


Digital Forensic 관련으로 [존경하는 고수](https://www.linkedin.com/in/deok9/)님께서 학생들을 위해 과제를 출제하셨다길래 어떤 과제인지 궁금중인지 들어 확인해보았다. 큰 주제는 **"활성 시스템 정보 유출 분석 도구 개발"** 이었다. 최근에 [NIST Data Leakage Case](https://www.cfreds.nist.gov/data_leakage_case/data-leakage-case.html)들을 이용해서 내부 데이터 유출에 관련한 국세청 강의 자료도 만들고.. 실력이 부족하여 수상은 하지 못했지만 [제 5회 디지털 범인을 찾아라 경진대회](https://www.forensickorea.org/board_notice/766)에서도 악성코드와 원격 접속(RDP)을 활용한 내부 정보 유출 Case를 다뤄볼 수 있었다.


내부 정보 유출과 관련하여서 조사하는 Artifact 중에서 외부 저장 장치와 같은 Artifact는 운영체제에 종속적인 경향이 있어서 변화가 적다. 그래서 REGA나 조금 오래된 툴킷들을 통해서도 손쉽게 파싱이 가능하였고 분석에 있어 시간을 많이 단축 할 수 있었다. (하지만 새로운 버전의 운영체제 출시나 파일 포맷을 업데이트 한다면? 망했어요)


하지만 이번 과제에서 제출된 주요 Artifact (Cloud, Email)들은 많이 조사되는 대상이고 중요성이 큰 Artifact임에도 불구하고 소프트웨어에 종속적인 경향이 존재한다. 그래서 소프트웨어 자체의 업데이트에 의해 그 포맷이나 내용이 달라질 수 있어 툴킷이 업데이트 주기적으로 업데이트 되지 않는다면 깔끔한 결과를 얻을 수가 없다. (딱히 도구가 존재하지 않는 것도 한 몫하더라) 그래서 이와 관련된 Artifact는 수동으로 분석을 진행해왔다는 단점을 가지고 있었다. (상용 프로그램이나 개인적으로 소장하고 계신 스크립트나 프로그램들은 개선이 되어있다고 생각된다.)


이러한 점에서 추후 분석시간을 단축시키기 위해서 나만의 라이브러리나 툴킷의 필요성을 느꼈고, 난이도 방면에서도 전혀 어려운 일이 아니었기 때문에 입맛에 맞게 개발을 한 번 해보기로 하였다.


## 시나리오 설정


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
