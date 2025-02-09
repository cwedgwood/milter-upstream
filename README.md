[![GoDoc](https://godoc.org/github.com/mschneider82/milter?status.svg)](https://godoc.org/github.com/mschneider82/milter)

# milter

This is a fork of github.com/phalaaxx/milter, added the following pull requests:

* https://github.com/phalaaxx/milter/pull/16
* https://github.com/phalaaxx/milter/pull/14
* https://github.com/phalaaxx/milter/pull/11

and also _test cases using my [milterclient](https://github.com/mschneider82/milterclient) library.


### Added the functions in the interface:

* Init() is called on begin of a new Mail, before Connect() and before MailFrom() and also on RSET (abort command), so you can cleanup and init.
* Init now has a sessionID and a mailID
* Disconnect() which is called when the client disconnects (if you have a concurrent session counter you can decrease the counter there, this was not possible before)
* Logger interface to inject a custom logger
* Errors exported
* Changed: EnvFrom and RcptTo addresses are now always converted to lowercase
* Added all Protocol Options and Actions from libmilter (session.go)
