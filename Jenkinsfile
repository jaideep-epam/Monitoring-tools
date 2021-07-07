properties([parameters([choice(choices: ['nagios', 'grafana', 'zabbbix'], description: 'Automation', name: 'Tool')])])
pipeline {
    agent any
  stages {
    stage ('1 choice') {
      when {
                expression { Tool == 'nagios'}
            }
            steps {
                sh '''  '''
            }
    }
    stage ('2 choice') {
      when {
                expression {  Tool == 'grafana'}
            }
            steps {
                sh ''' 
echo "FROM jasonrivers/nagios
EXPOSE 3000" > dockerfile3
                       docker build -f /var/lib/jenkins/workspace/Monitoring-tools-deployment/dockerfile3 -t nagios-image
                       docker run -i -d -p 3000:3000 nagios-image '''
            }
    }

   stage ('3 choice') {
      when {
                expression {  Tool == 'zabbix'}
            }
            steps {
                sh ''' ./zabbix.sh '''
            }
        }
     stage ('4 choice') {
      when {
                expression {  Tool == 'prometheus'}
            }
            steps {
                sh ''' ./prometheus.sh '''
            }
     } 
  }
}
