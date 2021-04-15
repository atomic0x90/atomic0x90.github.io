---
layout: post
title:  "VMware 우분투 설치"
date:   2021-04-10 10:00:00
author: atomic0x90 (Yujun Han)
categories: ubuntu
tags:  ubuntu
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

## VMware 우분투 18.04, 20.04 설치

---

VMware에 Ubuntu를 설치하는 방법입니다.

1. Ubuntu ISO 파일을 준비하고, VMware Workstation를 켭니다.
![Ubuntu Install img 1][10]

2. Create a New Virtual Machine 버튼을 누릅니다.
![Ubuntu Install img 2][11]

3. Typical (recommended) 을 선택합니다.
![Ubuntu Install img 3][12]

4. I will install the operating system later 을 선택합니다.
![Ubuntu Install img 4][13]

5. Ubuntu 를 설치하기 때문에 Linux 를 선택하고 자신의 컴퓨터 bit에 맞게 선택합니다.
![Ubuntu Install img 5][14]

6. 자신이 사용할 가상머신의 이름을 지정하고 가상머신을 저장할 위치를 지정해 줍니다.
![Ubuntu Install img 6][15]

7. 가상머신의 저장공간을 지정하고 Split virtual disk into multiple files 를 선택합니다.
![Ubuntu Install img 7][16]

8. 지금까지 설정한 설정을 보여주는 화면입니다. 추가적으로 바꾸고 싶은 설정이 있을 경우 Customize Hardware에 들어갑니다.
![Ubuntu Install img 8][17]

9. 이제 초기 설정은 끝났습니다. 
![Ubuntu Install img 9][18]

10. 왼쪽 상단에 Edit virtual machine settings 버튼을 누르고 Hardware의 CD/DVD (SATA) 의 Connection 설정을 처음 받았던 ISO 파일 경로로 바꿔줍니다. 그리고 Power on 버튼을 눌러서 시작합니다.
![Ubuntu Install img 10][19]

11. 가상머신을 시작하면 한국어 설정을 하고 Ubuntu 설치를 누릅니다.
![Ubuntu Install img 11][20]

12. 키보드 레이아웃을 한국어로 설정합니다.
![Ubuntu Install img 12][21]

13. Ubuntu를 처음 접하는 사람이라면 일반 설치로 설치하는걸 권장합니다.
![Ubuntu Install img 13][22]

14. 가상머신이기 때문에 디스크를 지우고 Ubuntu 설치를 선택하여 설치합니다.
![Ubuntu Install img 14][23]

15. 현재 자신의 위치 설정을 합니다.
![Ubuntu Install img 15][24]

16. 가상머신에서 사용할 사용자 이름과 비밀번호를 설정합니다.
![Ubuntu Install img 16][25]

17. 이제 자동으로 Ubuntu가 설치됩니다.
![Ubuntu Install img 17][26]

18. 설치가 완료되면 다시시작을 진행합니다.
![Ubuntu Install img 18][27]

19. ENTER 버튼을 눌러줍니다.
![Ubuntu Install img 19][28]

20. 재부팅이 완료된 후 비밀번호 입력을 하여 가상머신에 로그인 합니다.
![Ubuntu Install img 20][29]

21. VMware에 Ubuntu를 설치 완료 했습니다.
![Ubuntu Install img 21][30]

**감사합니다.**


---


[홈으로 가기][01]       |[더 많은 ubuntu post 보기][03]         |[post 목록 보기][02]
:------:                |:------:                               |:------:
                        |                                       |

[10]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall1.png "Ubuntu Install img 2"
[11]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall2.png "Ubuntu Install img 3"
[12]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall3.png "Ubuntu Install img 4"
[13]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall4.png "Ubuntu Install img 5"
[14]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall5.png "Ubuntu Install img 6"
[15]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall6.png "Ubuntu Install img 7"
[16]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall7.png "Ubuntu Install img 8"
[17]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall8.png "Ubuntu Install img 9"
[18]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall9.png "Ubuntu Install img 10"
[19]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall10.png "Ubuntu Install img 11"
[20]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall11.png "Ubuntu Install img 12"
[21]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall12.png "Ubuntu Install img 13"
[22]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall13.png "Ubuntu Install img 14"
[23]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall14.png "Ubuntu Install img 15"
[24]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall15.png "Ubuntu Install img 16"
[25]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall16.png "Ubuntu Install img 17"
[26]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall17.png "Ubuntu Install img 18"
[27]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall18.png "Ubuntu Install img 19"
[28]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall19.png "Ubuntu Install img 20"
[29]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall20.png "Ubuntu Install img 21"
[30]: {{site.baseurl}}/assets/ubuntuInstallIMG/vmUbuntuInstall21.png "Ubuntu Install img 22"


[01]: https://atomic0x90.github.io/ "home"
[02]: https://atomic0x90.github.io/posts/ "posts"
[03]: https://atomic0x90.github.io/posts/#ubuntu "ubuntu posts"

{% if site.disqus-shortname %}{% include disqus_comments.html %}{% endif %}

