<a href='https://www.learntocodeonline.com/'>![Learn To Code Online By Clicking Here](../Images/learn-to-code-online.png?raw=true "Learn To Code Online")</a>

# How To Link To An Issue On GitHub In Your Commit Message

As per [this response on StackOverflow](https://stackoverflow.com/a/6742691/10474024)...

With new [GitHub issues 2.0](https://github.com/blog/831-issues-2-0-the-next-generation) you can use these synonyms (they are not case sensitive) to reference an issue and close it (in your commit message):

`fix #xxx`
`fixes #xxx`
`fixed #xxx`
`close #xxx`
`closes #xxx`
`closed #xxx`
`resolve #xxx`
`resolves #xxx`
`resolved #xxx`
You can also substitute `#xxx` with `gh-xxx`.

Referencing and [closing issues](https://github.com/blog/1439-closing-issues-across-repositories) across repos also works:

  `fixes user/repo#xxx`

[Check out the documentation](https://help.github.com/articles/closing-issues-via-commit-messages) available in their Help section.

And [as per this](https://stackoverflow.com/a/1689670/10474024)...

# Link And Close Issue In Commit

If you want to link to AND close an issue?

`Closes #1.`
`Closes GH-1.`
`Closes gh-1.`

Learn more[here](http://github.com/blog/411-github-issue-tracker).

You can also cross reference repositories:
`githubuser/repository#xxx`

# Examples

From [here](https://stackoverflow.com/a/40139298/10474024):
```
feat: Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequenses of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here

If you use an issue tracker, put references to them at the bottom,
like this:

Resolves: #123
See also: #456, #789
```
