# pachybug
Pachyderm 1.11.0 bug : Cron job can not be ad hoc triggered with Build Pipeline

Reproduce Error with following steps
`cd dockerfile`
`docker build -t bug .`
`pachctl create pipeline -f bug.json`

Cron job works as expected, as you can see from this command. Print "I am bug" every minute
`pachctl logs -p bug`

Error message `pipeline must have a cron input` shows while ad-hoc triggering the pipeline
`pachctl run cron bug`

