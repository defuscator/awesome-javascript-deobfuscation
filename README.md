# Awesome JavaScript Deobfuscation [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Tools, techniques and references for reading obfuscated, packed and minified JavaScript, from
> malware triage to understanding a third-party bundle.

The most important property of any tool here is **whether it runs the code it analyses**. Running a
skimmer or loader to recover its strings is sometimes the only way through, but it is a decision you
should make on purpose, not discover afterwards. Entries that execute sample code are marked ⚠️.

Maintained by [Defuscator](https://defuscator.com), whose own tools are listed alongside everyone
else's. Entries are grouped, not ranked. Corrections and additions are welcome, see
[CONTRIBUTING](CONTRIBUTING.md).

## Contents

- [Deobfuscators](#deobfuscators)
- [Decompilers and unbundlers](#decompilers-and-unbundlers)
- [AI-assisted](#ai-assisted)
- [Malware sandboxes](#malware-sandboxes)
- [Beautifiers and formatters](#beautifiers-and-formatters)
- [Name recovery](#name-recovery)
- [Parsers and AST toolkits](#parsers-and-ast-toolkits)
- [Obfuscators](#obfuscators)
- [Benchmarks](#benchmarks)
- [Techniques](#techniques)

## Deobfuscators

- [Defuscator](https://defuscator.com) - Static deobfuscation and risk triage for obfuscator.io string arrays, P.A.C.K.E.R., encoded strings and source maps, with IOC extraction and SARIF output. Web app, API, [CLI](https://github.com/defuscator/defuscator-cli), [GitHub Action](https://github.com/defuscator/defuscator-action) and [VS Code extension](https://github.com/defuscator/defuscator-vscode). Never executes the sample.
- [webcrack](https://github.com/j4k0xb/webcrack) - Deobfuscates obfuscator.io output, unminifies, and unpacks webpack/browserify bundles. ⚠️ Evaluates string-array decoders in an isolated VM.
- [synchrony](https://github.com/relative/synchrony) - Cleaner and deobfuscator focused on javascript-obfuscator output.
- [REstringer](https://github.com/HumanSecurity/restringer) - Modular deobfuscator with safe AST transforms plus ⚠️ optional modules that evaluate code in an isolated VM.
- [javascript-deobfuscator](https://github.com/ben-sb/javascript-deobfuscator) - General-purpose deobfuscator covering common array, proxy and string transforms.
- [js-deobfuscator](https://github.com/kuizuo/js-deobfuscator) - Automated deobfuscation built on the Babel AST, with an online playground.
- [JStillery](https://github.com/mindedsecurity/JStillery) - Deobfuscation through partial evaluation. Unmaintained since 2019.
- [de4js](https://github.com/lelinhtinh/de4js) - Browser-based unpacker for legacy packers, JSFuck, JJEncode and AAEncode. Archived.

## Decompilers and unbundlers

- [wakaru](https://github.com/pionxzh/wakaru) - Decompiler for modern frontend output: unpacks bundles and reverses transpiler and minifier transforms.

## AI-assisted

- [humanify](https://github.com/jehna/humanify) - Uses a language model to rename identifiers and make deobfuscated code readable. Check its output against the input; names are suggestions, not recovered facts.

## Malware sandboxes

Use these when static analysis runs out, in a disposable environment.

- [box-js](https://github.com/CapacitorSet/box-js) - ⚠️ Emulated environment for studying JavaScript malware, logging URLs, files and payloads it touches.
- [malware-jail](https://github.com/HynekPetrak/malware-jail) - ⚠️ Sandbox for semi-automatic JavaScript malware analysis, deobfuscation and payload extraction.

## Beautifiers and formatters

Formatting is not deobfuscation, but it is usually the first step.

- [js-beautify](https://github.com/beautifier/js-beautify) - Long-standing beautifier with a P.A.C.K.E.R. unpacker option.
- [Prettier](https://github.com/prettier/prettier) - Opinionated formatter; reliable for reformatting code that already parses.

## Name recovery

- [UnuglifyJS](https://github.com/eth-sri/UnuglifyJS) - Open-source version of JSNice, predicting identifier names from a statistical model.

## Parsers and AST toolkits

For writing your own transforms.

- [Babel](https://github.com/babel/babel) - Parser, traversal and generator; the base of most AST-based deobfuscators.
- [Acorn](https://github.com/acornjs/acorn) - Small, fast, spec-compliant JavaScript parser.

## Obfuscators

Knowing the transforms is most of reversing them.

- [javascript-obfuscator](https://github.com/javascript-obfuscator/javascript-obfuscator) - The engine behind obfuscator.io: string arrays with rotation and encoding, control-flow flattening, self-defending code.
- [JSFuck](https://github.com/aemkei/jsfuck) - Encodes any program using six characters: `[]()!+`.
- [JS-Confuser](https://github.com/MichaelXF/js-confuser) - Obfuscator with control-flow, string and lock transforms.
- [JavaScript Obfuscator](https://javascriptobfuscator.com/) - Commercial obfuscator from the team behind Defuscator.

## Benchmarks

- [deobfuscation-benchmark](https://github.com/defuscator/deobfuscation-benchmark) - Scores a deobfuscator against samples generated by the real obfuscators, checking correctness by executing the decoded output. Tool-agnostic: point it at any CLI that emits JSON.

## Techniques

Guides that explain a technique rather than sell a tool.

- [Unpacking Dean Edwards P.A.C.K.E.R. without eval](https://defuscator.com/Deobfuscate/Packer.aspx) - How the packer's base62 dictionary works and how to regenerate the source statically.
- [obfuscator.io string arrays](https://defuscator.com/Deobfuscate/ObfuscatorIo.aspx) - Rotation, encoding and offset decoders, and why a table one position out still looks correct.
- [Hex and unicode escapes](https://defuscator.com/Deobfuscate/HexEscapes.aspx) - Decoding escape layers without changing what the code means.
- [Recovering sources from source maps](https://defuscator.com/Deobfuscate/SourceMaps.aspx) - Inline and external maps, and when `sourcesContent` gives you the original.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to
this list.
