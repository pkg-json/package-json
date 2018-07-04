This project is a spec for `package.json`, which is a file commonly used by tools in the JavaScript ecosystem to provide metadata about modules. It is written as a spec for tool authors, but should also be described simply enough to be used as documentation for users. Changes and proposals for new fields should be submitted through the RFC process as pull requests, which will allow implementors and the community to provide feedback on proposals.

## History

Historically, `package.json` has been documented by various tools such as [npm](https://docs.npmjs.com/files/package.json), [yarn](https://yarnpkg.com/lang/en/docs/package-json/), and [elsewhere](https://github.com/stereobooster/package.json) but never all in one place and in a detailed enough way that a tool implementer could have a single source of truth about how each field should work. This document aims to change that.

## Goals

The goal of this document is not to list every possible field, but to spec existing commonly implemented fields across multiple tools, and provide a home for consensus building around future extensions to the `package.json` format. It is not expected that every tool implement every feature described in this document as different tools have different needs, however, it is expected that tools implement individual features according to this spec in order to be compliant.

For existing fields, the goal is mostly to document how each field that is already implemented by existing tools should be used by package authors. This should be done in a detailed enough way that a tool author could also implement support for an existing package.json field in a new tool without reading the source code of another tool. The goal is not to change how existing tools work, just to document the informal defacto standard already agreed on in other forums and commonly used throughout the ecosystem.

For new fields, the goal of this spec is not to prevent tools from experimenting and creating their own tool-specific fields as many have today. However, if those tools are interested in coming to a consensus with other tool makers around a feature that could benefit the entire ecosystem, the RFC process on this repo would be a good place to do that and document the result.

## RFC Process

Substantial changes to the spec will follow an RFC (request for comments) process through pull requests. The process is as follows:

1. Fork this repo and make changes to the spec.
2. Make a pull request, and fill in all details of the pull request template. This helps us understand why you are proposing the change, how the change benefits users, what types of tools the change will benefit, etc.
3. The pull request will receive feedback from other tool authors that are contributing to this spec, along with the wider JavaScript community.
4. Eventually, a consensus will be made about whether an RFC is a candidate for inclusion in the spec. If an RFC is rejected by the team or withdrawn by the author, the PR will be closed.
5. Once an RFC is approved, it will enter a final comment period lasting 7 days. This will be signaled by a label on the PR.
6. After the final comment period, an accepted RFC will be merged into the spec.
7. Once an RFC is approved and merged, it is up to individual tool authors to implement the changes. Conformant implementations will be tracked as part of the spec.

This RFC process is inspired by the [Yarn](https://github.com/yarnpkg/rfcs#what-the-process-is) RFC process.
