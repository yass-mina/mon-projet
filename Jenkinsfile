pipeline {
    agent any
    options { timestamps() }

    stages {
        stage('Cloner le dépôt') {
            steps {
                checkout scm
            }
        }

        stage('Étape 1 : Vérification du dépôt') {
            steps {
                bat 'echo === Etape 1 : Verification du depot ==='
                bat 'git status'
            }
        }

        stage('Étape 2 : Afficher le contenu du projet') {
            steps {
                bat 'echo === Etape 2 : Afficher le contenu du projet ==='
                bat 'dir'
            }
        }

        stage('Étape 3 : Simuler un déploiement local') {
            steps {
                bat 'echo === Etape 3 : Simuler un deploiement local ==='
                bat 'echo Le fichier index.html est pret a etre affiche'
            }
        }

        stage('Étape 4 : Fin du build') {
            steps {
                bat 'echo === Etape 4 : Fin du build ==='
                bat 'echo SUCCESS'
                archiveArtifacts artifacts: '*.html, *.css', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Build OK'
        }
        failure {
            echo 'Build KO'
        }
    }
}