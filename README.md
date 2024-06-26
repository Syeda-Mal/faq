# faq

Creative Commons FAQ page: https://creativecommons.org/faq/

## Code of conduct

[`CODE_OF_CONDUCT.md`][org-coc]:
> The Creative Commons team is committed to fostering a welcoming community.
> This project and all other Creative Commons open source projects are governed
> by our [Code of Conduct][code_of_conduct]. Please report unacceptable
> behavior to [conduct@creativecommons.org](mailto:conduct@creativecommons.org)
> per our [reporting guidelines][reporting_guide].

[org-coc]: https://github.com/creativecommons/.github/blob/main/CODE_OF_CONDUCT.md
[code_of_conduct]: https://opensource.creativecommons.org/community/code-of-conduct/
[reporting_guide]: https://opensource.creativecommons.org/community/code-of-conduct/enforcement/


## Contributing

See [`CONTRIBUTING.md`][org-contrib].

[org-contrib]: https://github.com/creativecommons/.github/blob/main/CONTRIBUTING.md

# Content Updates

:warning: Do **not** modify the `index.html` files in `faq/`. They are
generated by the build script.

**Only** modify the markdown files (`faq-en.md` and `faq-fr.md`).


# Deployment

1. **On your local computer**:
   1. Ensure that you have `pandoc` installed (it is availble via
      [Homebrew](https://brew.sh/) on macOS)
   2. Generate new `index.html` files:
   ```shell
   ./build.sh
   ```
   3. Review changes:
   ```shell
   git diff
   ```
   4. Commit changes and submit pull request
2. **On the `salt-prime` server**, test highstate
   ```shell
   sudo salt index__prod__us-east-2 state.highstate saltenv=${USER} test=True
   ```
3. **On the `salt-prime` server**, apply highstate
   ```shell
   sudo salt index__prod__us-east-2 state.highstate saltenv=${USER}
   ```


# License


## Code

[![CC0 1.0 Universal (CC0 1.0) Public Domain Dedication
button][cc-zero-png]][cc-zero]

[`bin/COPYING`](bin/COPYING): The code ([`build.sh`](build.sh)) is dedicated to
the public domain under the [CC0 1.0 Universal (CC0 1.0) Public Domain
Dedication][cc-zero].

[cc-zero-png]: https://licensebuttons.net/l/zero/1.0/88x31.png "CC0 1.0 Universal (CC0 1.0) Public Domain Dedication button"
[cc-zero]: https://creativecommons.org/publicdomain/zero/1.0/


## Content

[![CC BY 4.0 license button][cc-by-png]][cc-by]

[`LICENSE`](LICENSE): The content (`.md`, `.html`, and `.png` files) is
licensed under a [Creative Commons Attribution 4.0 International
License][cc-by].

[cc-by-png]: https://licensebuttons.net/l/by/4.0/88x31.png#floatleft "CC BY 4.0 license button"
[cc-by]: https://creativecommons.org/licenses/by/4.0/ "Creative Commons Attribution 4.0 International License"
