# mhchem-katex

This package simply contains the mhchem plugin for KaTeX, but slightly modified to make it significantly easier to use!

The way of referencing the original file means that though it may work in the browser, in Node it sometimes works and sometimes doesn't, with no obvious reason why, and seems to be subject to random breakages through changes to apparently unrelated code. The way that it references the KaTeX module seems unreliable in Node, and offers no control whatsoever for trying to sort it out. My modified file requires more lines of code to include, but at least works in applications in which I never got the original to work. Import and use it thus:

```typescript
import { macros as mhchemMacros } from '@cwm/mhchem-katex/mhchem';

const katexOptions: KatexOptions = {
  macros: {
    ...mhchemMacros,
  },
  throwOnError: true,
  errorColor: '#cc0000',
};
md.use(mdKatex, katexOptions);
```

Original source url for the included `mhchem.js` file: https://cdn.jsdelivr.net/npm/katex@0.10.1/dist/contrib/mhchem.js

Documentation: https://mhchem.github.io/MathJax-mhchem/

I am in no way attempting to claim any credit for the brilliant work, just packaging it up so I can use it.
