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
EXPOSE 9292" > dockerfile3
                       docker build -t grafana-image dockerfile3
                       docker run -i -d -p 3000:3000 grafana-image '''
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
