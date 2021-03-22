# PAYPAL Code Submission:

This archive contains a simple credit card processing application. It has two components: a Ruby web and application server beelzebub (using the Sinatra framework, and running under Unicorn), and a requester which simulates making requests against the server. The server receives the requests and writes them to its data directory. The server also logs each transaction’s start time and completion time via syslog.


1.	Any necessary runtime or compile dependencies
Vagrent installtion
Virtual box 
Install and run beelzebub + unicorn
Setup Nagios
Siege


2.	Instructions for compiling and running your checks

This program accepts --warning and --critical thresholds for the number of open transaction files.
 Cd ../check_beelzebub --warning 10 --critical 20
 Example: ./check_beelzebub_open_files_1 -w 10 -c 20
 
 OUTPUT: Transaction file count 0
 
 
 7ffe8c31a000-7ffe8c31c000 r-xp 00000000 00:00 0                          [vdso]
ffffffffff600000-ffffffffff601000 r-xp 00000000 00:00 0                  [vsyscall]
Response Time 0.01

./check_beelzebub_tx_response_time -w 5 -c 10 -t 5

Output: ffffffffff600000-ffffffffff601000 r-xp 00000000 00:00 0                  [vsyscall]
CRITICAL : Response Time time is greater than thresold value 10 sec


3.	Any assumptions you made

Install siege
after installation check the siege -g http://localhost:8080
siege -q -c 5 -t 5s -v "http://localhost:8080" | grep "Response time"

Siege is an HTTP regression testing and benchmarking utility. It was designed to let web developers measure the performance of their code under duress, to see how it will stand up to load on the internet. Siege supports basic authentication, cookies, HTTP and HTTPS protocols. It allows the user hit a web server with a configurable number of concurrent simulated users. Those users place the web-server "under siege."

4.	Why you picked the programming language you used

Shell has easy interactive debugging and i have good real time experience on shell














My replications log:
  157  ./check_beelzebub_tx_response_timeee -w 5 -c 10 -t 10
  158  ./check_beelzebub_tx_response_timeee -w 5 -c 10 -t 300
  159  ./check_beelzebub_tx_response_timeee -w 2 -c 3 -t 300
  160  ./check_beelzebub_tx_response_timeee -w 2 -c 3 -t 10
  161  ./check_beelzebub_tx_response_timeee -w 2 -c 3 -t 300


siege -q -c 5 -t 5s -v http://localhost:8080
   85  siege -q -c 5 -t 5s -v "http://localhost:8080"
   86  siege -q -c 5 -t 5s -v "http://localhost:8080" | grep "Response time"
   91  siege -q -c 5 -t 5s -v "http://localhost:8080" | grep "Response time"
   92  siege -g http://localhost:8080
   93  siege -g http://www.facebook.com
   94  siege -g http://localhost:8080
