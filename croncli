#!/usr/bin/env node

const exec = require('child_process').exec;
const CronJob = require('cron').CronJob;
const commander = require('commander');
const program = new commander.Command();

program
  .option('-p, --pattern <pattern>', 'cron pattern ', "*/5 * * * * *" )
  .option('-t, --timezone <timezone>', 'timezone ', 'Asia/Tokyo' )
  .option('-e, --execute <command>', 'command to be executed ', "echo Hi." )
  .option('-l, --log', 'enable console log ')
  .parse(process.argv)
  ; if (! process.argv.slice(2).length) program.help() ;

(new CronJob(program.pattern, async function() {
  if (program.log) console.log(`[${program.pattern}] Job fired:`, new Date().toLocaleTimeString("en-US", {timeZone: program.timezone, year: "numeric", month: '2-digit', day: '2-digit', hour: '2-digit', minute:'2-digit', second:'2-digit', timeZoneName: 'short'}) );
	await exec(program.execute, (error, stdout, stderr) => { if ( error ){ console.log(error) } if ( stdout ){ console.log(stdout) } if ( stderr ){ console.log(stderr) } });
})).start() ;

if (program.log) console.log("Jobs started...") ;
