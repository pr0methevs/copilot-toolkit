# Conventional Commit Message Instructions

The Conventional Commits specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of. This convention dovetails with SemVer, by describing the features, fixes, and breaking changes made in commit messages.

## Format

The commit message MUST be structured as follows:

<type>[optional scope]: <description>

[optional body]

[optional footer(s)]


## Types

MUST analyze the files changed, and using the ordered list below that is sorted by importance write the heading and focus of the commit header:

- feat: Add, adjust, or remove a feature
- bugfix: Bug fix
- build: Build tools, dependencies, CI/CD
- refactor: Code restructure without behavior change
- ops: Infrastructure, deployment, operations
- perf: Performance improvement
- test: Add or correct tests
- docs: Documentation only
- chore: Miscellaneous (e.g., .gitignore)
- style: Code style only

## Scopes

- Optional, project-defined (do not use issue IDs)

## Breaking Changes

- Indicate with `!` before `:`, e.g. `feat(api)!: remove endpoint`
- Describe breaking changes in the footer, starting with `BREAKING CHANGE:`

## Description

- Concise, imperative, present tense
- Do not capitalize first letter or end with a period

## Body

- Motivation and contrast with previous behavior
- Use bullet points or paragraphs for clarity
- Benefits of the change
- Potential drawbacks

## Footer

- Issue references (e.g., Closes #123)
- Breaking changes info (required if breaking change)

## Large Commits

If there are a vast amount of changes the header MUST still accurately reflect the nature of the changes made. The body can then be used to provide further detail on the large number of changes made using a bulleted list or similar format. Grouping changes into categories can help provide clarity.

## Specification 
The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

1. Commits MUST be prefixed with a type, which consists of a noun, feat, fix, etc., followed by the OPTIONAL scope, OPTIONAL !, and REQUIRED terminal colon and space.

2. The type feat MUST be used when a commit adds a new feature to your application or library.

3. The type fix MUST be used when a commit represents a bug fix for your application.

4. A scope MAY be provided after a type. A scope MUST consist of a noun describing a section of the codebase surrounded by parenthesis, e.g., fix(parser):

5. A description MUST immediately follow the colon and space after the type/scope prefix. The description is a short summary of the code changes, e.g., fix: array parsing issue when multiple spaces were contained in string.

6. A longer commit body MAY be provided after the short description, providing additional contextual information about the code changes. The body MUST begin one blank line after the description.

7. A commit body is free-form and MAY consist of any number of newline separated paragraphs.

8. One or more footers MAY be provided one blank line after the body. Each footer MUST consist of a word token, followed by either a :<space> or <space># separator, followed by a string value (this is inspired by the git trailer convention).

9. A footer’s token MUST use - in place of whitespace characters, e.g., Acked-by (this helps differentiate the footer section from a multi-paragraph body). An exception is made for BREAKING CHANGE, which MAY also be used as a token.

10. A footer’s value MAY contain spaces and newlines, and parsing MUST terminate when the next valid footer token/separator pair is observed.

11. Breaking changes MUST be indicated in the type/scope prefix of a commit, or as an entry in the footer.

12. If included as a footer, a breaking change MUST consist of the uppercase text BREAKING CHANGE, followed by a colon, space, and description, e.g., BREAKING CHANGE: environment variables now take precedence over config files.
13. If included in the type/scope prefix, breaking changes MUST be indicated by a ! immediately before the :. If ! is used, BREAKING CHANGE: MAY be omitted from the footer section, and the commit description SHALL be used to describe the breaking change.

14. Types other than feat and fix MAY be used in your commit messages, e.g., docs: update ref docs.

15. The units of information that make up Conventional Commits MUST NOT be treated as case sensitive by implementors, with the exception of BREAKING CHANGE which MUST be uppercase.

16. BREAKING-CHANGE MUST be synonymous with BREAKING CHANGE, when used as a token in a footer.

## Examples

#### Scope
- A scope may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis:
```
feat(cart): add checkout button

Implements checkout for shopping cart.

Closes #123
```

```
feat(parser): add ability to parse arrays.
```

#### Commit message with description and breaking change footer

```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

#### Commit message with ! to draw attention to breaking change
```
feat!: send an email to the customer when a product is shipped
```

#### Commit message with scope and ! to draw attention to breaking change
```
feat(api)!: send an email to the customer when a product is shipped
```

#### Commit message with both ! and BREAKING CHANGE footer
```
chore!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

#### Commit message with no body
```
docs: correct spelling of CHANGELOG
```

#### Commit message with multi-paragraph body and multiple footers
```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
```

## References

- https://www.conventionalcommits.org/
- https://github.com/angular/angular/blob/master/CONTRIBUTING.md

