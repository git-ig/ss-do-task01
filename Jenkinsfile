pipeline {
    agent any // Запускать на любом доступном агенте Jenkins

    tools {
        // Указываем, что нам нужен Node.js, настроенный в Jenkins под именем 'NodeJS-22'
        nodejs 'NodeJS-22'
    }

    stages {
        stage('Prepare') {
            steps {
                echo 'Этап подготовки: Установка Node.js уже выполнена с помощью секции tools.'
                // Проверим версию Node, чтобы убедиться
                sh 'node --version'
            }
        }
        stage('Build') {
            steps {
                echo 'Этап сборки: Отображаем версию npm...'
                // Команда sh выполняет скрипт оболочки
                sh 'npm --version'
            }
        }
        stage('Test') {
            steps {
                echo 'Этап тестирования: Отображаем переменную окружения JENKINS_URL...'
                // Переменные окружения Jenkins доступны напрямую
                echo "Jenkins URL: ${env.JENKINS_URL}"
            }
        }
    }

    post {
        always {
            echo 'Пайплайн завершен.'
            // Очистка рабочего пространства (хорошая практика)
            cleanWs()
        }
    }
}
