# State of TypeScript, May 2022

TypeScript is an open source, cross-platform, superset of JavaScript that
is sponsored by Microsoft. 69% of surveyed JavaScript users use
TypeScript, and 94% of surveyed TypeScript users would use it again. It
is the 7th most used, 3rd most loved, and 2nd most wanted language in
the 2021 StackOverflow Developer Survey.

## What's New?

- Performance is better, as always.
- Realpath improvements.
- Improved structural checks.
- @typescript/analyze-trace

## A Proposal for Type Syntax in JavaScript

[A Proposal for Type Syntax in
JavaScript](https://devblogs.microsoft.com/typescript/a-proposal-for-type-syntax-in-javascript/)

Today TypeScript is compiled to JavaScript, which runs in the browser
and on runtimes such as Node. TypeScript has been proposed to become
*JavaScript with types*, in that, there will be tools to understand the
type annotations and TypeScript syntax during development, but the browser
will discard and ignore any typing (and other TS syntax). This would allow
TypeScript to run natively in browsers, skipping the troublesome and
painful compilation and bundling steps.

I would personally like to see this change come to modern browsers, and
I'm eager to see where it goes in the future.
