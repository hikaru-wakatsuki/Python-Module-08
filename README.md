*This project has been created as part of the 42 curriculum by hwakatsu.*

# The Matrix

## Description / 説明

### English
The Matrix is a Python project about the practical foundations of data engineering. Its goal is to learn how to work with virtual environments, dependency management, and environment-based configuration while building small command-line programs.

This repository is organized into three exercises:

- `ex0/construct.py`: detects whether Python is running inside a virtual environment and prints environment details
- `ex01/loading.py`: checks external dependencies, runs a small data analysis task, and generates a visualization
- `ex02/oracle.py`: loads application configuration from environment variables and `.env` files

The project introduces the tools that are commonly used before building real data pipelines: isolated Python environments, package installation strategies, and secure configuration handling.

### 日本語
The Matrix は、データエンジニアリングの実務的な基礎を学ぶ Python プロジェクトです。目的は、仮想環境、依存関係管理、環境変数ベースの設定管理を、小さなコマンドラインプログラムを通して理解することです。

このリポジトリは 3 つの exercise で構成されています。

- `ex0/construct.py`: Python が仮想環境内で動いているかを判定し、環境情報を表示する
- `ex01/loading.py`: 外部依存関係を確認し、簡単なデータ分析を行い、可視化ファイルを生成する
- `ex02/oracle.py`: 環境変数と `.env` ファイルから設定を読み込む

実際のデータパイプライン構築の前提となる、隔離された Python 環境、パッケージ管理、セキュアな設定管理を学ぶための課題です。

## Instructions / 実行方法

### English

Requirements:

- Python 3.10 or later
- `pip`
- Optional: Poetry
- For `ex01`: `pandas`, `numpy`, `matplotlib`, `requests`
- For `ex02`: `python-dotenv`

Recommended virtual environment setup:

```bash
python3 -m venv matrix_env
source matrix_env/bin/activate
```

Run exercise 0:

```bash
python3 ex0/construct.py
```

Install dependencies for exercise 1 with `pip`:

```bash
pip install -r ex01/requirements.txt
python3 ex01/loading.py
```

Or with Poetry:

```bash
cd ex01
poetry install
poetry run python loading.py
```

Install dependency for exercise 2:

```bash
pip install python-dotenv
```

Then prepare a local `.env` file and run:

```bash
cd ex02
cp .env.example .env
python3 oracle.py
```

Optional lint check:

```bash
flake8 ex0 ex01 ex02
```

### 日本語

必要環境:

- Python 3.10 以上
- `pip`
- 任意: Poetry
- `ex01` 用: `pandas`, `numpy`, `matplotlib`, `requests`
- `ex02` 用: `python-dotenv`

推奨される仮想環境セットアップ:

```bash
python3 -m venv matrix_env
source matrix_env/bin/activate
```

exercise 0 の実行:

```bash
python3 ex0/construct.py
```

exercise 1 の依存関係を `pip` で入れる場合:

```bash
pip install -r ex01/requirements.txt
python3 ex01/loading.py
```

Poetry を使う場合:

```bash
cd ex01
poetry install
poetry run python loading.py
```

exercise 2 に必要な依存関係:

```bash
pip install python-dotenv
```

その後、ローカル用の `.env` を用意して実行します。

```bash
cd ex02
cp .env.example .env
python3 oracle.py
```

任意の lint チェック:

```bash
flake8 ex0 ex01 ex02
```

## Features / 主な内容

### English

- Virtual environment detection with `sys`, `os`, and `site`
- Dependency checking through dynamic imports
- Sample data analysis with `pandas` and `numpy`
- Chart generation with `matplotlib`
- Secure configuration loading with environment variables and `python-dotenv`

### 日本語

- `sys`、`os`、`site` を使った仮想環境の検出
- 動的 import による依存関係チェック
- `pandas` と `numpy` を使ったサンプルデータ分析
- `matplotlib` によるグラフ生成
- 環境変数と `python-dotenv` を使った安全な設定読み込み

## Usage Overview / 使い方の概要

### English

- `construct.py` behaves differently inside and outside a virtual environment.
- `loading.py` exits with installation guidance if required packages are missing.
- `oracle.py` reads configuration from `.env` and environment variables, then prints a simple status summary.

### 日本語

- `construct.py` は仮想環境の内外で出力が変わります。
- `loading.py` は必要なパッケージが足りない場合、インストール方法を表示して終了します。
- `oracle.py` は `.env` と環境変数から設定を読み込み、状態を表示します。

## Resources / 参考資料

### English

Classic references related to the topic:

- [Python Documentation: venv](https://docs.python.org/3/library/venv.html)
- [Python Packaging User Guide](https://packaging.python.org/)
- [Poetry Documentation](https://python-poetry.org/docs/)
- [pandas Documentation](https://pandas.pydata.org/docs/)
- [NumPy Documentation](https://numpy.org/doc/)
- [Matplotlib Documentation](https://matplotlib.org/stable/users/index.html)
- [python-dotenv Documentation](https://bbc2.github.io/python-dotenv/)
- [flake8 Documentation](https://flake8.pycqa.org/)

AI usage in this project:

- AI was used for documentation support and README drafting.
- It was used to summarize the project subject, structure the README, and provide bilingual English/Japanese wording.
- The implementation, dependency setup, and configuration behavior should still be checked manually before submission and peer review.

### 日本語

この課題に関連する代表的な参考資料:

- [Python Documentation: venv](https://docs.python.org/3/library/venv.html)
- [Python Packaging User Guide](https://packaging.python.org/)
- [Poetry Documentation](https://python-poetry.org/docs/)
- [pandas Documentation](https://pandas.pydata.org/docs/)
- [NumPy Documentation](https://numpy.org/doc/)
- [Matplotlib Documentation](https://matplotlib.org/stable/users/index.html)
- [python-dotenv Documentation](https://bbc2.github.io/python-dotenv/)
- [flake8 Documentation](https://flake8.pycqa.org/)

このプロジェクトにおける AI の利用:

- AI はドキュメント補助と README 作成支援に使用しました。
- 課題内容の要約、README の構成整理、英語と日本語の文章調整に利用しました。
- 実装内容、依存関係の導入手順、設定ファイルの挙動については、提出前と peer review 前に手動で確認する前提です。

## Notes / 補足

### English
Some exercises depend on local environment setup. For example, `ex01` requires third-party packages, and `ex02` expects a valid `.env` file with the required keys.

### 日本語
いくつかの exercise はローカル環境の準備に依存します。たとえば `ex01` では外部パッケージが必要で、`ex02` では必要なキーを持つ `.env` ファイルが必要です。
