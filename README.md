# projeto-testes-automatizados
def test_soma_simples():
    assert 2 + 2 == 4

def test_string():
    assert "qa".upper() == "QA"
# Projeto de Testes Automatizados

Projeto simples de testes automatizados utilizando Python e Pytest.

## Como executar os testes localmente
1. Instalar Python 3
2. Instalar dependências:
   pip install -r requirements.txt
3. Executar os testes:
   pytest
__pycache__/
.pytest_cache/
venv/
pipeline {
    agent any

    stages {

        stage('Preparação do ambiente') {
            steps {
                echo 'Iniciando pipeline'
                checkout scm
            }
        }

        stage('Instalação das dependências') {
            steps {
                echo 'Instalando dependências'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Execução de testes automatizados') {
            steps {
                echo 'Executando testes automatizados'
                sh 'pytest --junitxml=report.xml'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finalizado'
        }
    }
}

Devido às limitações do ambiente local (tablet), o Jenkins não foi instalado localmente. O pipeline foi configurado via Jenkinsfile e versionado no repositório GitHub, seguindo as boas práticas de CI/CD, permitindo execução em qualquer ambiente Jenkins compatível.
