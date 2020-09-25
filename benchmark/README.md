# pipenv vs peotry 성능 테스트 요약

- poetry와 pipenv가 특정 상황에서 운영체제별로 수행 시간이 얼마나 차이가 나는지 알아보는 성능테스트(실험)입니다.
- 측정하고자 하는 상황은 installation, add package, lock, remove package 네 가지입니다.
- 최대한 동일한 환경에서 진행하려 노력했습니다. (하단 <테스트 환경> 항목 참조)
- MacOS, Linux(Ubuntu), Windows 모두 동일한 cpu/ram/disk 에서 진행했습니다.
- 성능 평가 시 실행되는 다른 프로세스가 없도록 하였습니다.
- 사용된 pipenv, poetry의 버전은 각각 `2020.08.13`과 `1.0.10` 입니다.
- 명령어 소요 시간은 처음에는 직접 측정(...)했으나, 이후에는 time(linux, macos)과 Measure-Command (windows)를 이용하였습니다.
- 운영체제의 각 상황별로 4회 반복측정 후 평균을 냈습니다.
- command output이 궁금하신 분들을 위해 `result/` 폴더에 output을 그대로 남겨 두었습니다. 

> 이런 성능 테스트를 제대로(?) 해 본건 이번이 처음이었습니다. 이렇게 하는게 맞는지 확실치 않아 최대한 많이 찾아보고 꼼꼼하게 한다고 했지만, 그럼에도 부족한 점이 있거나, 제가 염두하지 못한 변수가 있었다면 (일단 이쁘게 봐 주시고) issue나 pull request 남겨주세요..헿

> 맨 밑에 <끝나니까 생긴 추가 의문> 에 대해서도 아시는 분들은 pr이나 issue 남겨주시면 너무 감사드릴 것 같습니다..

## 테스트 환경

### Linux
 - Thinkpad T490
 - Ubuntu 18.04 LTS
 - Processor 2.8GHz  Quad-Core Intel Core i7
 - Memory 16GB 
 - Disk 150GB (Available)

### Windows

 - Thinkpad T490
 - Microsoft Windows 10 Pro
 - Processor 2.8GHz  Quad-Core Intel Core i7
 - Memory 16GB 
 - Disk 150GB (Available)

> Linux 성능평가 끝내고 운영체제 밀어버리고 새로 깔아서 하드웨어는 동일하다.

### MacOS

 - MacBook Pro (15 inch, 2017)
 - MacOS Catalina (Ver. 10.15.6)
 - Processor 2.8GHz  Quad-Core Intel Core i7
 - Memory 16GB 2133 MHz LPDDR3
 - Disk 150GB (Available)

## 결과 정리

time: pipenv/poetry

|                |   Installation  |   add package   |      lock      | remove package |
|:--------------:|:---------------:|:---------------:|:--------------:|:--------------:|
|     windows    | **7.184s**/73.574s | 21.145s/**19.358s** | 21.906s/**5.626s** | 16.064s/**8.435s** |
| Linux (Ubuntu) |  **9.384s**/27.476s | 30.232s/**22.835s** | 23.854s/**5.091s** | 20.819s/**3.091s** |
|      MacOS     | **15.993s**/39.619s | 26.962s/**14.468s** | 16.373s/**0.622s** | 12.188s/**4.814s** |


## 결론

- **Installation을 제외한 모든 항목에서 poetry가 우세하다.**
- [pipenv의 저장소](https://github.com/pypa/pipenv)에서는 *Windows is a first-class citizen, in our world.* 라고 쓰여 있어서 Windows에서 pipenv 의 성능이 눈에 띄게 좋을 줄 알았고, 이전 버전의 pipenv를 이용해 실험했을 적에는 실제로도 그런 성능을 보였다. 
- 하지만 최근 릴리즈된 pipenv(`2020.08.13`)로 테스트를 (반복하여) 진행해본 결과, Windows에서의 성능이 대체적으로 더 좋기는 하나, 눈에 띌 정도는 아닌 듯하다.
- 위 결론과 비슷한 말이기는 하지만, 발표에서는 **"pipenv의 Linux에서의 성능 차이가 Windows 성능차이보다 크다. 따라서 Windows에서 pipenv를 사용하기에 더 적합한 것 같다"** 라고 말했었는데, 그 차이가 사용에 영향을 받을 정도의 성능 차이가 있는 건 아니다.

## 끝나니까 생긴 추가 의문

발표 끝나고 숙원 사업처럼 남겨두기로.

- [ ] (git) bash, powershell 터미널에 따라서도 성능이 다를까?

    아마 아닐듯하다... 거기서 거기 일 것 같긴 한데.. 궁금은 하다.

- [ ] Linux 배포판에 따라서도 측정해보고 싶다.

    많이는 못해도 RHEL(CentOS), Gentoo는 궁금하다.

- [x] 버전 별로도 크게 다를까?

    이건 직접 해봤다! 물론 운영체제별로 다 해보진 못했지만
    Linux (Ubuntu) / Windows에서는 pipenv의 성능이 눈에 띄게 증가했다.
