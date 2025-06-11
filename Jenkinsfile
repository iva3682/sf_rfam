pipeline {
    agent any
    
    stages {
        stage('Run SQL Script') {
            steps {
                script {
                    def result = sh(script: """
                        mysql --host mysql-rfam-public.ebi.ac.uk \
                               --port 4497 \
                               --user rfamro \
                               --database Rfam \
                               < update_data.sql
                    """, returnStdout: true)
                    
                    echo("Результат выполнения SQL-запроса:")
                    echo(result.trim())
                }
            }
        }
    }
}