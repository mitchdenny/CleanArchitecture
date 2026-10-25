[![.NET Core](https://github.com/ardalis/CleanArchitecture/workflows/.NET%20Core/badge.svg)](https://github.com/ardalis/CleanArchitecture/actions)
[![publish Ardalis.CleanArchitecture Template to nuget](https://github.com/ardalis/CleanArchitecture/actions/workflows/publish.yml/badge.svg)](https://github.com/ardalis/CleanArchitecture/actions/workflows/publish.yml)
[![Ardalis.CleanArchitecture.Template on NuGet](https://img.shields.io/nuget/v/Ardalis.CleanArchitecture.Template?label=Ardalis.CleanArchitecture.Template)](https://www.nuget.org/packages/Ardalis.CleanArchitecture.Template/)

<a href="https://twitter.com/intent/follow?screen_name=ardalis">
    <img src="https://img.shields.io/twitter/follow/ardalis.svg?label=Follow%20@ardalis" alt="Follow @ardalis" />
</a> &nbsp; <a href="https://twitter.com/intent/follow?screen_name=nimblepros">
    <img src="https://img.shields.io/twitter/follow/nimblepros.svg?label=Follow%20@nimblepros" alt="Follow @nimblepros" />
</a>

<p>

![Alt](https://repobeats.axiom.co/api/embed/be5094dd306ba53b8f4fc0b43c9de5d8ca23a608.svg "Repobeats analytics image")

</p>

# Clean Architecture

A starting point for Clean Architecture with ASP.NET Core. [Clean Architecture](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html) is just the latest in a series of names for the same loosely-coupled, dependency-inverted architecture. You will also find it named [hexagonal](https://alistair.cockburn.us/hexagonal-architecture), [ports-and-adapters](http://www.dossier-andreas.net/software_architecture/ports_and_adapters.html), or [onion architecture](http://jeffreypalermo.com/blog/the-onion-architecture-part-1/).

Learn more about Clean Architecture and this template in [NimblePros' Introducing Clean Architecture course](https://academy.nimblepros.com/p/learn-clean-architecture). Use code ARDALIS to save 20%.

This architecture is used in the [DDD Fundamentals course](https://www.pluralsight.com/courses/fundamentals-domain-driven-design) by [Steve Smith](https://ardalis.com) and [Julie Lerman](https://thedatafarm.com/).

:school: Contact Steve's company, [NimblePros](https://nimblepros.com/), for Clean Architecture or DDD training and/or implementation assistance for your team.

## Take the Course!

[Learn about how to implement Clean Architecture](https://academy.nimblepros.com/p/intro-to-clean-architecture) from [NimblePros](https://nimblepros.com) trainers [Sarah "sadukie" Dutkiewicz](https://blog.nimblepros.com/author/sadukie/) and [Steve "ardalis" Smith](https://blog.nimblepros.com/author/ardalis/).

## Table Of Contents

- [Clean Architecture](#clean-architecture)
  - [Take the Course!](#take-the-course)
  - [Table Of Contents](#table-of-contents)
  - [Give a Star! :star:](#give-a-star-star)
  - [Sponsors](#sponsors)
  - [Troubleshooting Chrome Errors](#troubleshooting-chrome-errors)
  - [Versions](#versions)
  - [Learn More](#learn-more)
- [Getting Started](#getting-started)
  - [Template Installation](#template-installation)
  - [Using the dotnet CLI template](#using-the-dotnet-cli-template)
    - [Full Clean Architecture (`clean-arch`)](#full-clean-architecture-clean-arch)
    - [Minimal Clean Architecture (`min-clean`)](#minimal-clean-architecture-min-clean)
  - [Template Comparison](#template-comparison)
    - [Which Template Should I Use?](#which-template-should-i-use)
  - [What about Controllers and Razor Pages?](#what-about-controllers-and-razor-pages)
    - [Add Ardalis.ApiEndpoints](#add-ardalisapiendpoints)
    - [Add Controllers](#add-controllers)
    - [Add Razor Pages](#add-razor-pages)
  - [Using the GitHub Repository](#using-the-github-repository)
  - [Running Migrations](#running-migrations)
- [Goals](#goals)
  - [History and Shameless Plug Section](#history-and-shameless-plug-section)
- [Design Decisions and Dependencies](#design-decisions-and-dependencies)
  - [Where To Validate](#where-to-validate)
  - [The Core Project](#the-core-project)
  - [The Use Cases Project](#the-use-cases-project)
  - [The Infrastructure Project](#the-infrastructure-project)
  - [The Web Project](#the-web-project)
  - [The SharedKernel Package](#the-sharedkernel-package)
  - [The Test Projects](#the-test-projects)
- [Patterns Used](#patterns-used)
  - [Domain Events](#domain-events)
  - [Related Projects](#related-projects)
  - [Presentations and Videos on Clean Architecture](#presentations-and-videos-on-clean-architecture)

## Give a Star! :star:

If you like or are using this project to learn or start your solution, please give it a star. Thanks!

Or if you're feeling really generous, we now support GitHub sponsorships - see the button above.

## Sponsors

I'm please to announce that [Amazon AWS's FOSS fund](https://github.com/aws/dotnet-foss) has chosen to award a 12-month sponsorship to this project. Thank you, and thanks to all of my other past and current sponsors!

## Troubleshooting Chrome Errors

By default the site uses HTTPS and expects you to have a self-signed developer certificate for localhost use. If you get an error with Chrome [see this answer](https://stackoverflow.com/a/31900210/13729) for mitigation instructions.

## Versions

The main branch is now using **.NET 9**. This corresponds with NuGet package version 10.x. Previous versions are available - see our [Releases](https://github.com/ardalis/CleanArchitecture/releases).

## Learn More

- [Live Stream Recordings Working on Clean Architecture](https://www.youtube.com/c/Ardalis/search?query=clean%20architecture)
- [DotNetRocks Podcast Discussion with Steve "ardalis" Smith](https://player.fm/series/net-rocks/clean-architecture-with-steve-smith)
- [Fritz and Friends Streaming Discussion with Steve "ardalis" Smith](https://www.youtube.com/watch?v=k8cZUW4MS3I)

## Aspire CLI template proof of concept

This fork adapts the full `clean-arch` template for the directory/Git template
mechanism in [microsoft/aspire#21263](https://github.com/microsoft/aspire/pull/21263).
Use a CLI built from that change; released CLIs without these source options
cannot run the commands below. The separate `MinimalClean` template is unchanged.

From an unpacked checkout:

```bash
/path/to/feature/aspire new --template-path . \
  --name CleanPoc --output ../CleanPoc --suppress-agent-init
```

From this fork:

```bash
/path/to/feature/aspire new \
  --template-repository https://github.com/mitchdenny/CleanArchitecture.git \
  --template-repository-ref mitchdenny-cleanarchitecture-template-poc \
  --template-path . \
  --name CleanPoc --output ./CleanPoc --suppress-agent-init
```

Select **ASP.NET Clean Architecture Solution** when prompted. The repository
contains two templates, so the current mechanism requires interactive selection
at its root; `--non-interactive` cannot select the full template. A full commit SHA
can replace the branch ref for reproducible generation.

The authored SDK, SQL Server integration, and testing defaults are
[Aspire 13.6.4](https://github.com/microsoft/aspire/releases/tag/v13.6.4), the
latest stable release when this proof of concept was updated. Ordinary .NET
template usage still works and retains the template's NuGet configuration:

```bash
dotnet new install .
dotnet new clean-arch --name CleanPoc --output ../CleanPoc
```

`AspireVersion` is a string parameter that Aspire CLI replaces with its SDK
identity, including a PR suffix. `AspireHostingSqlServerVersion` and
`AspireHostingTestingVersion` are separate string parameters. Under Aspire CLI,
the host resolves each package independently to the highest version available
on its mapping-eligible feeds (`*-*`, including prereleases); under `dotnet new`,
they use their stable defaults or explicit command-line overrides. Context-scoped
replacements keep these three versions independent even when defaults match.

For a PR CLI with downloaded matching build packages, set the existing identity
override before either Aspire command:

```bash
export ASPIRE_CLI_PACKAGES=/absolute/path/to/pr-nupkg-feed
```

The directory must include the matching SDK and integration packages, plus any
required RID-specific packages. This is an identity-source override, not the
`--source` template-package option, which cannot be combined with custom template
sources. No PR number or package build version is hardcoded in the template.

When Aspire supplies `AspireNuGetSource`, generation excludes the template-owned
`nuget.config`. The host's `createNuGetConfig` opt-in then lets the CLI generate
the source-aware package mappings without a template-owned config blocking them.
Stable nuget.org-only policy may need no generated file. The generated policy
inherits normal NuGet sources for non-Aspire dependencies; it does not globally
replace user/machine settings. For isolated validation, provide an ancestor
NuGet configuration containing only nuget.org and use a fresh home/package cache.
The old Windows-only `LocalNuget` entry remains available to ordinary `dotnet new`
users, but is not copied into Aspire-generated output.

Generation does not run restore or template post-actions. Build the generated
AppHost explicitly:

```bash
dotnet build CleanPoc/src/CleanPoc.AspireHost/CleanPoc.AspireHost.csproj
dotnet build CleanPoc/tests/CleanPoc.AspireTests/CleanPoc.AspireTests.csproj
```

The original AppHost restore failed on audited MessagePack and transitive
`System.Security.Cryptography.Pkcs` vulnerabilities, promoted to errors by
`TreatWarningsAsErrors`. Their minimum patched versions are pinned without
disabling audit. The Microsoft.Extensions and OpenTelemetry versions consumed by
the updated Aspire SDK/integrations are aligned to avoid central transitive-pin
downgrades; other dependency versions are unchanged.

AppHost and Aspire testing-project builds work with both stable defaults and
PR-injected versions. Full-solution restore still encounters the existing
SSH.NET 2025.1.0 vulnerability warnings in Testcontainers-backed tests; those
unrelated dependencies are outside this proof of concept. Stable builds retain
ASPIRE010 (CLI bundle opt-in), and the tested PR SDK retains ASPIRE012 (legacy
AppHost SDK migration); neither diagnostic is suppressed.

# Documentation

The official documentation for this template, including Getting Started steps, Migration Guides, and Architectural Decisions, can be found at [Ardalis Clean Architecture Docs](https://ardalis.github.io/CleanArchitecture).

If you are upgrading from an older version, please be sure to review our [Migration Guides](https://ardalis.github.io/CleanArchitecture/migration-guides/) on the new documentation site!
