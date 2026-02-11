pipeline {
    agent any

    tools {
        // Ces noms doivent correspondre à ta configuration dans "Administrer Jenkins > Tools"
        jdk 'Java21' 
        maven 'Maven3'
    }

    stages {
        stage('Recuperation du Code') {
            steps {
                // Cette commande récupère le code de ton repo personnel
                checkout scm
                echo "Code récupéré avec succès depuis GitHub"
            }
        }

        stage('Compilation du Code') {
            steps {
                // Cette commande compile ton code source (Spring Boot / Java)
                sh 'mvn clean compile'
                echo "Compilation terminée sans erreur"
            }
        }
    }

    post {
        success {
            echo 'L\'exercice est réussi : Code récupéré et compilé !'
        }
    }
}
