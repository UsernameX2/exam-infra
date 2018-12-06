### Dette er oppgaven min for DevOps eksamen høst 2018

* Du er nødt til å lage forks av disse 2 repositoriene
`https://github.com/UsernameX2/exam-infra`
`https://github.com/UsernameX2/exam-app`
* Lag deploy keys
* Endre pipeline.yml i infra til de repoene som du nettop forka
* Lage en credentials.yml fil i rooten av infra katalogen hvor du har med følgende punkter
    * deploy_key_app
    * deploy_key_infra
    * heroku_email
    * heroku_api_key
    * github_token
    * heroku_app_name
    * logziotoken
    * statuscake_api_key
* Endrer variables.tf, endrer username i statuscake.tf og email i provider_heroku.tf
* Gå inn i app katalogen og kjør `docker-compose up -d`
* Gå inn i infra katalogen og kjør `fly -t (min target) set-pipeline -c concourse/pipeline.yml -l credentials.yml -p student_name`
Kan hende du blir nødt til å logge deg inn, følg intstrukser på terminalen
* Etter at du har fått opp pipelinen blir du nødt til å unpause den før du starter infra. Du starter infra ved å trykke på den, deretter pluss tegnet oppe i høye hjørnet


Jeg fikk opp denne feilmelding
```
Backend error: Exit status: 500, message: {"Type":"","Message":"runc exec: exit status 1: exec failed: container_linux.go:348: starting container process caused \"exec: \\\"monitoring-infra/concourse/java/task.sh\\\": permission denied\"\n","Handle":"","ProcessID":"","Binary":""}
```
Og jeg greide ikke å gjøre noe med den. Jeg prøvde å legge til applikasjonslogger men fikk ikke testet det ut, siden jeg fikk ikke kjørt infra. 