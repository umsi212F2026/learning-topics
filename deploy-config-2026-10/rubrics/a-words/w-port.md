# Rubric: port

A port is the number after the colon that says which program on a machine a request is for: in
`http://localhost:5173`, the frontend's dev server listens on 5173 and the Express backend on
3000, both on the same machine. The confusable is the host name (`localhost`, or
`tally.quay.app`), which says which machine the request goes to. In this file "address" is not
used for the host name alone.

### q1

- **goal:** `w-port`
- **move:** DISTINGUISH
- **answer:** The host name, `localhost`, says which machine the request goes to (here, your
  own). The port, 5173, says which program on that machine it is for, so one machine can run
  several programs, each on its own port.
- **credit:** full for naming both halves: the host name picks the machine, the port picks the
  program on it. Half for only one half (for example, "the port picks which program" with nothing
  on what the host name picks). None for an incidental difference alone, such as that the port is
  a number, comes after the colon, or is shorter.

### q2

- **goal:** `w-port`
- **move:** CATCH
- **answer:** A machine has many ports, not one. Each program listens on its own, which is how the
  frontend runs on 5173 and the backend on 3000 on the same laptop at once.
- **credit:** full for naming that a machine has many ports and each program takes its own, so two
  programs can run side by side. Half for saying they can both run without saying how ports make
  that possible. None for a different quibble, such as that the laptop needs more memory, or that
  only one can be deployed.

### q3

- **goal:** `w-port`
- **move:** CATCH
- **answer:** Only the port changed. `localhost` is the host name, and it still names the same
  machine; 4000 just says the backend is now the program listening on a different port of it.
- **credit:** full for naming that the host name, which picks the machine, is unchanged, and only
  the port, which picks the program on it, changed. Half for saying it is the same machine
  without saying which part of the URL shows that. None for a different quibble, such as that
  the frontend now needs updating.
- **tutor note:** a learner who says "the frontend now needs the new URL" is right but has
  answered a different question; ask whether the backend moved machines.
