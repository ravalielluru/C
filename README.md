# PAYPAL Code Submission:

This archive contains a simple credit card processing application. It has two components: a Ruby web and application server beelzebub (using the Sinatra framework, and running under Unicorn), and a requester which simulates making requests against the server. The server receives the requests and writes them to its data directory. The server also logs each transaction’s start time and completion time via syslog.
