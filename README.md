# Shimmering Bee: Z-Stack

[![license](https://img.shields.io/github/license/shimmeringbee/shimmeringbee.io.svg)](https://github.com/shimmeringbee/shimmeringbee.io/blob/master/LICENSE)
[![standard-readme compliant](https://img.shields.io/badge/standard--readme-OK-green.svg)](https://github.com/RichardLitt/standard-readme)
[![Actions Status](https://github.com/shimmeringbee/shimmeringbee.io/workflows/publish/badge.svg)](https://github.com/shimmeringbee/shimmeringbee.io/actions)

> Website for shimmeringbee.io.

## Table of Contents

- [Background](#background)
- [Install](#install)
- [Usage](#usage)
- [Maintainers](#maintainers)
- [Contributing](#contributing)
- [License](#license)

## Background

Shimmering Bee needs a cohesive website to explain the project, rather than it being split amongst different repositories.

## Build

Commits to this repository are automatically built and uploaded to Amazon Web Services for hosting. Please see `.github/workflows/publish.yaml` for the publication process, or `cloudformation/live/website.json` for AWS CloudFormation.

Building locally can be done through Docker, or by installing hugo locally.

```
docker run --rm -it -p 1313:1313 -v $(pwd):/src lakegg/hugo:ext-alpine server --bind 0.0.0.0
```

## Maintainers

[@pwood](https://github.com/pwood)

## Contributing

Feel free to dive in! [Open an issue](https://github.com/shimmeringbee/shimmeringbee.io/issues/new) or submit PRs.

All Shimmering Bee projects follow the [Contributor Covenant](http://contributor-covenant.org/version/1/3/0/) Code of Conduct.

## License

   Copyright 2019 Peter Wood

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.