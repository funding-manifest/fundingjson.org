+++
+++

funding.json is a manifest that enables Free and Open Source Software (FOSS) projects to declare their financial needs in a machine-readable format. The self-contained JSON file can be easily published in repositories or websites, functioning similarly to robots.txt or Progressive Web App manifests.

By making funding requirements publicly crawlable and indexable, funding.json makes aims to bring discoverablity to FOSS projects, helping connect those seeking financial support with potential backers.


## Schema

The current version is v1.0.0. A human readable version with comments is shown below. The JSON schema (json-schema.org) is [available here](/schema/v1.0.0/funding.schema.json).

```json
{{ read_file(path="static/static/annotated-funding.json") }}
```
<a href="#" data-copy-clipboard>Copy</a>

-----------

## Example

Assuming that the manifest is located at `https://example.com/funding.json`
```json
{{ read_file(path="static/static/example-funding.json") }}
```
<a href="#" data-copy-clipboard>Copy</a>

<br />

For repository hosting platforms like GitHub, the manifest can be checked into the project repository directly, eg: `https://github.com/example/coolapp/blob/main/funding.json`

-----------

### wellKnown

If a `funding.json` manifest lists URLs (such as webpage or repository) that are hosted on a different hostname than the manifest itself, those URLs are considered **unverified**. For example, if `example.com/funding.json` includes a project with the URL `project.net/repository`, that project URL is unverified because ther is no way to know whether `example.com` is authorized to solicit funding on behalf of `project.net`.

To verify URLs that do not share the same hostname, a `wellKnown` URL can be provided that points to a `/.well-known/funding-manifest-urls` file.

This file must contain the URL of the `funding.json` manifest URLs that reference it. For instance, `project.net/.well-known/funding-manifest-urls` can contain a reference to `example.com/funding.json` proving that they are associated.

The file can contain multiple URLs, one per line. This establishes provenance and verifies that that the publisher of the manifest is authorised to solicit funding on behalf of the URLs (entity, projects) described in the manifest. This follows the [.well-known](https://en.wikipedia.org/wiki/Well-known_URI) convention. An example scenario is described below.

|                                                 |                                                              |
| ------------------------------------------------|--------------------------------------------------------------|
| Manifest location                               | https://example.com/funding.json                             |
| Project URL referenced in the manifest          | https://project.net                                  |
| Expected `wellKnown` along with the project URL | https://project.net/.well-known/funding-manifest-urls |
| Contents of the `wellKnown` file                | `https://example.com/funding.json`                           |

### tags

While the `tags[]` field under projects is meant for arbitrary lowercase-alphanumeric-dash strings to describe the projects, [project-tags.txt](/static/project-tags.txt) can be used as a reference list for uniformity.

-----------

## Tools

- [FLOSS/fund open directory](https://dir.floss.fund)
- [Live manifest validator](https://dir.floss.fund/validate)
- [Manifest builder UI](https://vishnukvmd.github.io/funding.json/)

-----------

## Examples

#### Large projects and institutions
- [python.org/funding.json](https://python.org/funding.json) ([Render](https://dir.floss.fund/view/@www.python.org))
- [openstreetmap.org/funding.json](https://openstreetmap.org/funding.json) ([Render](https://dir.floss.fund/view/@www.openstreetmap.org))
- [ffmpeg.org/funding.json](https://ffmpeg.org/funding.json) ([Render](https://dir.floss.fund/view/@ffmpeg.org))
- [ziglang.org/funding.json](https://ziglang.org/funding.json) ([Render](https://dir.floss.fund/view/@ziglang.org))
- [f-droid.org/funding.json](https://f-droid.org/funding.json) ([Render](https://dir.floss.fund/view/@f-droid.org))
- [matrix.org/funding.json](https://matrix.org/funding.json) ([Render](https://dir.floss.fund/view/@matrix.org))
- [github.com/openssl/openssl/blob/master/funding.json](https://github.com/openssl/openssl/blob/master/funding.json) ([Render](https://dir.floss.fund/view/@github.com/openssl))
- [github.com/WorldHealthOrganization/godata/blob/master/funding/funding.json](https://github.com/WorldHealthOrganization/godata/blob/master/funding/funding.json) ([Render](https://dir.floss.fund/view/@github.com/WorldHealthOrganization))

### Individuals

- [sniffnet.net/funding.json](https://sniffnet.net/funding.json) ([Render](https://dir.floss.fund/view/@sniffnet.net))
- [orhun.dev/funding.json](https://orhun.dev/funding.json) ([Render](https://dir.floss.fund/view/@orhun.dev))
- [robyn.tech/funding.json](https://robyn.tech/funding.json) ([Render](https://dir.floss.fund/view/@robyn.tech))
- [rdmp.org/dmbcs/mcron/funding.json](https://rdmp.org/dmbcs/mcron/funding.json) ([Render](https://dir.floss.fund/view/@rdmp.org/dmbcs/mcron))
- [github.com/dlemstra/dlemstra/blob/main/funding.json](https://github.com/dlemstra/dlemstra/blob/main/funding.json) ([Render](https://dir.floss.fund/view/@github.com/dlemstra))
- [github.com/GuillaumeGomez/sysinfo/blob/master/funding.json](https://github.com/GuillaumeGomez/sysinfo/blob/master/funding.json) ([Render](https://github.com/GuillaumeGomez/sysinfo/blob/master/funding.json))
