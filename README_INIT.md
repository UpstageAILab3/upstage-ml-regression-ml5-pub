apt-get update
apt install -y git
git --version
git config --global user.email "helpotcreator@gmail.com"
git config --global user.name "helpotcreator"
mkdir /kkh
cd /kkh
git clone https://{개인 토큰}@github.com/UpstageAILab3/upstage-ml-regression-ml5.git
mv upstage-ml-regression-ml5 helpotcreator
cd helpotcreator
git remote -v
git checkout -b kimkihong origin/kimkihong
git branch -a
init 파일들 작성



pip install --upgrade pip
pip install poetry
poetry -V
poetry init
pyproject.toml 파일 수정
poetry install
poetry add jupyter nbconvert
jupyter_to_python.sh 파일을 아래와 같이 생성


############################################
#!/bin/bash

# 주피터 노트북 파일명을 인자로 받음
NOTEBOOK_FILE="$1"

# 파일명이 주어지지 않으면 에러 메시지를 출력하고 종료
if [ -z "$NOTEBOOK_FILE" ]; then
    echo "Usage: $0 <notebook-file>"
    exit 1
fi

# 주어진 파일이 .ipynb 확장자를 가지고 있는지 확인
if [[ "$NOTEBOOK_FILE" != *.ipynb ]]; then
    echo "Error: The input file must have a .ipynb extension"
    exit 1
fi

# jupyter nbconvert 명령어를 사용하여 노트북 파일을 Python 스크립트로 변환
python -m jupyter nbconvert --to script "$NOTEBOOK_FILE"

# 변환 결과 확인
if [ $? -eq 0 ]; then
    echo "Conversion successful: ${NOTEBOOK_FILE%.ipynb}.py"
else
    echo "Conversion failed"
    exit 1
fi
############################################


chmod +x jupyter_to_python.sh
poetry run ./jupyter_to_python.sh {주피터 파일명}.ipynb
poetry run python {만들어진 파이썬 파일}.py



