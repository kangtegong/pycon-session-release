# Pycon Korea 2020 발표자료

## 제목

파이썬 대패키지시대, requirements.txt 텍스트파일 하나만 믿어도 정말 괜찮은 걸까

## 목차

1. [발표 자료 (pdf ver.)](https://github.com/kangtegong/pycon-session-release/blob/master/pycon-kr-release-kmc.pdf)
2. [발표 대본](https://github.com/kangtegong/pycon-session-release/blob/master/script.md)
3. benchmark
    - [src/ : 테스트에 사용된 tools](https://github.com/kangtegong/pycon-session-release/tree/master/benchmark/src)
        - pipenv / Pipfile, Pipfile.lock
        - poetry / poetry.lock, pyproject.toml
    - [README.md : Test 결과 요약](https://github.com/kangtegong/pycon-session-release/blob/master/benchmark/README.md)
    - [result/ : 각각의 테스트 출력 모음](https://github.com/kangtegong/pycon-session-release/tree/master/benchmark/result)
        - MacOS.md
        - Windows.md
        - Linux.md

## 성능 테스트

[poetry vs pipenv 상황별 성능 테스트](https://github.com/kangtegong/pycon-session-release/blob/master/benchmark/README.md)

---

성능 테스트 할 수 있게 맥북 빌려주신 [박슬아님](https://github.com/cristina-cloud) 감사합니다..
