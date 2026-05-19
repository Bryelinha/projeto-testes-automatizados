describe('Login Hub de Leitura', () => {

    beforeEach(() => {
        cy.visit('http://localhost:3000')
    })

    it('Deve realizar login com sucesso', () => {

        cy.get('#email')
            .type('teste@teste.com')

        cy.get('#password')
            .type('123456')

        cy.get('button')
            .click()

        cy.contains('Login realizado com sucesso')
    })
}){
  "name": "jenkins-automation-project",
  "version": "1.0.0",
  "scripts": {
    "test": "cypress run",
    "cypress:open": "cypress open"
  },
  "devDependencies": {
    "cypress": "^13.0.0"
  }
}pipeline {

    agent any

    stages {

        stage('Preparar Ambiente') {
            steps {
                echo 'Preparando ambiente...'
            }
        }

        stage('Instalar Dependências') {
            steps {
                bat 'npm install'
            }
        }

        stage('Executar Testes') {
            steps {
                bat 'npx cypress run'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finalizado'
        }

        success {
            echo 'Testes executados com sucesso'
        }

        failure {
            echo 'Falha na execução dos testes'
        }
    }# Projeto Jenkins + Cypress

3. Execução dos testes automatizados}
