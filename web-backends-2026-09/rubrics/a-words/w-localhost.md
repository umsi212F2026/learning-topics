# Rubric: localhost

### q-define-localhost

- **type:** free
- **goal:** w-localhost
- **move:** DEFINE
- **answer:** localhost is the name a machine has for itself. An address that starts
  http://localhost reaches whatever is running on the computer the address was typed on, and nothing
  anywhere else, so while the app is at one of those addresses it is running on your own laptop and
  you are the only one who can open it.
- **credit:** full credit for saying localhost means this computer, the one you are on, so the
  address reaches only your own machine. Full credit for "it means the app is running on my laptop
  and is not on the internet". Full credit for "127.0.0.1", the address every machine uses for
  itself. Do not accept "the port the app is running on", which is the number after the colon, and do
  not accept "the address of a local server" with nothing about whose machine it is.

### q-localhost-sent-to-sister

- **type:** free
- **goal:** w-localhost
- **move:** CATCH
- **answer:** localhost means the machine the address is opened on, so their sister's browser asked
  her own laptop, which is probably not running a server. The request never reached the classmate's
  machine at all.
- **credit:** full credit for saying the address points at whoever opens it, so she reached her own
  machine rather than theirs, and it therefore tells them nothing about their own server. Full
  credit for "you would have to deploy it first", which only makes sense if the address reaches no
  one else's machine. Do not accept a different quibble as the error: that they sent the wrong port,
  that she needs to be on the same wifi, or that her firewall blocked it.

### q-localhost-tests-passed

- **type:** mcq
- **goal:** w-localhost
- **move:** INTERPRET
- **answer:** 1
- **credit:** 2 and 3 both have the app reachable from somewhere other than your own laptop, which is
  the thing an address at localhost rules out. 4 turns "the tests pass" into "it works only under
  test", which the message does not say.
