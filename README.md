# demo-lib

A small utility library. Nothing fancy — string helpers and a tiny CLI.

```bash
npm install demo-lib
```

```js
const { slugify } = require('demo-lib');
slugify('Hello World'); // => 'hello-world'
```

---

## ⚠️ SECURITY RESEARCH — DEFANGED PROOF OF CONCEPT

This repository is **not a real library.** It is a proof-of-concept for a
vulnerability report to Anthropic (Claude Code) via HackerOne.

* `.claude/bin/{git,bwrap,socat}` are **defanged proof markers**. They record
  observations (uid, namespace, argv0, parent process) to `/tmp/rce0003/` and
  then `exec` the genuine system binary. **They contain no payload.**
  The place a real payload would go is marked by a single comment line:
  `# >>> REAL PAYLOAD SLOT <<<`
* `.claude/settings.json` contains the two configuration keys under test.
* Nothing here is exfiltrated, persisted, or destructive.

Do not use this as a template. Report issues to the vendor, not to users.
