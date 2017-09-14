# git-commit-message-convention

Extend git commit message from angular style


# Commit Message Format
All Commit Message Format **MUST** meet this Text Format:

```
[:<Emoji>: ][<Type>[(<Scope>)]: ]<Subject>
[<BLANK LINE>]
[<Message Body>]
[<BLANK LINE>]
[<Message Footer>]
```


# Types

| Type          | Description |
|:-------------:|-------------|
| `new`         | for new feature implementing commit|
| `feature`     | for new feature implementing commit (equal `new`) |
| `bug`         | for bug fix commit |
| `security`    | for security issue fix commit |
| `performance` | for performance issue fix commit |
| `improvement` | for backwards-compatible enhancement commit |
| `breaking`    | for backwards-incompatible enhancement commit |
| `deprecated`  | for deprecated feature commit |
| `refactor`    | for refactoring commit |
| `docs`        | for documentation commit |
| `examples`    | for example code commit |
| `test`        | for testing commit |
| `dependency`  | for dependencies upgrading or downgrading commit |
| `config`      | for configuration commit |
| `build`       | for packaging or bundling commit |
| `release`     | for publishing commit |
| `update`      | for update commit |
| `wip`         | for work in progress commit |
| `chore`       | for other operations commit |


If the prefix is the below types, it will appear in the changelog. 

- `new` (`feature`)
- `bug`
- `performance`
- `security`
- `deprecated`
- `improvement`
- `breaking`


# Scope
The scope could be anything specifying place or category of the commit change. For example $location, $browser, $compile, $rootScope, ngHref, ngClick, ngView, feature1, etc...


# Subject
The subject contains succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize first letter
* no dot (.) at the end


# Message Body
Just as in the **Subject**, use the imperative, present tense: "change" not "changed" nor "changes". The body should include the motivation for the change and contrast this with previous behavior.


# Message Footer
The Message Footer should contain any information about **Notes** and also Message Footer should be **recommended** [GitHub Issue](https://github.com/features#issues) ID Reference, Ex. `Issue #27`, `Fixes #1`, `Closes #2`, `Resolves #3`.

**Notes** should start with the word `NOTE:` with a space or two newlines. The rest of the commit message is then used for this.


# Revert
If the commit reverts a previous commit, it should begin with revert:, followed by the header of the reverted commit. In the body it should say: This reverts commit <hash>., where the hash is the SHA of the commit being reverted.


# Emojis

| Emoji                      | Raw Emoji Code               | Type               | Description |
|:--------------------------:|------------------------------|--------------------|-------------|
| :star:                     | `:star:`                     | `new` or `feature` | add **new feature** |
| :bug:                      | `:bug:`                      | `bug`              | fix **bug** issue |
| :lock:                     | `:lock:`                     | `security`         | fix **security** issue |
| :chart_with_upwards_trend: | `:chart_with_upwards_trend:` | `performance`      | fix **performance** issue |
| :zap:                      | `:zap:`                      | `improvement`      | update **backwards-compatible** feature |
| :boom:                     | `:boom`                      | `breaking`         | update **backwards-incompatible** feature |
| :warning:                  | `:warning:`                  | `deprecated`       | **deprecate** feature |
| :lipstick:                 | `:lipstick:`                 | `update`           | update **UI/Cosmetic** |
| :up:                       | `:up:`                       | `update`           | update **other** |
| :globe_with_meridians:     | `:globe_with_meridians:`     | `update`           | update or fix **internationalization** |
| :shirt:                    | `:shirt:`                    | `refactor`         | remove **linter**/strict/deprecation warnings or **refactoring** or code **layouting** |
| :white_check_mark:         | `:white_check_mark:`         | `test`             | add **tests** |
| :green_heart:              | `:green_heart:`              | `test`             | fix **tests** failur or **CI** building |
| :pencil:                   | `:pencil:`                   | `docs`             | update **documentation** |
| :copyright:                | `:license:`                  | `docs`             | decide or change **license** |
| :lollipop:                 | `:lollipop:`                 | `examples`         | for **example** codes |
| :arrow_up:                 | `:arrow_up:`                 | `dependency`       | upgrade **dependencies** |
| :arrow_down:               | `:arrow_down:`               | `dependency`       | downgrade **dependencies** |
| :pushpin:                  | `:pushpin:`                  | `dependency`       | pin **dependencies** |
| :wrench:                   | `:wrench:`                   | `config`           | update **configration** |
| :package:                  | `:package:`                  | `build`            | **packaging** or **bundling** or **building** |
| :hatching_chick:           | `:hatching_chick:`           | `release`          | **initial** commit |
| :confetti_ball:            | `:confetti_ball:`            | `release`          | release **major** version |
| :tada:                     | `:tada:`                     | `release`          | release **minior** version |
| :sparkles:                 | `:sparkles:`                 | `release`          | release **patch** version |
| :rocket:                   | `:rocket:`                   | `release`          | **deploy** to production enviroment |
| :back:                     | `:back:`                     | `revert`           | **revert** commiting |
| :construction:             | `:construction:`             | `wip`              | **WIP** commiting |
| :twisted_rightwards_arrows:| `:twisted_rightwards_arrows:`| -                  | merge **conflict resolution** |
| :heavy_plus_sign:          | `:heavy_plus_sign:`          | -                  | **add** files, dependencies, ... |
| :heavy_minus_sign:         | `:heavy_minus_sign:`         | -                  | **remove** files, dependencies, ... |
| :on:                       | `:on:`                       | -                  | **enable** feature and something ... |


Ask to Be [Creative](http://www.emoji-cheat-sheet.com/)!


# Examples

new:
```
:star: new(graphite): add 'graphiteWidth' option
```

bug fix:
```
:bug: fix(graphite): stop graphite breaking when width < 0.1

Closes #28
```

improve performance:
```
:chart_with_upwards_trend: performance(graphite): remove graphiteWidth option

The graphiteWidth option has been removed. The default graphite width of 10mm is always used for performance reason.
```

revert:
```
:back: revert: new: add 'graphiteWidth' option

This reverts commit 667ecc1654a317a13331b17617d973392f415f02.
```

# Support tools

## conventional-changelog

You can use with `conventional-changelog-cli` and `conventional-github-releaser`.

e.g. conventional-changelog-cli:

    $ npm i --save-dev git://github.com/kazupon/git-commit-message-convention.git
    $ conventional-changelog -i CHANGELOG.md -s -n ./node_modules/git-commit-message-convention/convention.js -r 0

e.g. conventional-github-releaser:

    $ conventional-github-releaser -n ./node_modules/git-commit-message-convention/convention.js -r 0


# TODO
- [x] support conventional commit tools (e.g. conventional-changelog)
- [ ] lint
- [ ] cli
- [ ] create a conventional commit tools with `golang`


# License

## MIT

[MIT](http://opensource.org/licenses/MIT)
