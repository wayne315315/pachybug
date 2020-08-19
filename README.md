# pachybug
Pachyderm 1.11.0 bug : Cron job can not be ad hoc triggered with Build Pipeline<br/> 

Reproduce Error with following steps<br/> 
`cd dockerfile`<br/> 
`docker build -t bug .`<br/> 
`pachctl create pipeline -f bug.json`<br/> 

Cron job works as expected, as you can see from this command. Print "I am bug" every minute<br/>
`pachctl logs -p bug`<br/>

Error message `pipeline must have a cron input` shows while ad-hoc triggering the pipeline<br/>
`pachctl run cron bug`<br/>
