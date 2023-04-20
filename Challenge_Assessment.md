# Challenge Assessment

Microservices Blogging Platform v1.3.1 (18-04-2023)

## Non-Goals

- Hiring status will not be impacted by this assessment, you are already hired.

- Deploying a production system, or the use of any paid resources.

- Completing 100% of the project. You won't be given enough time or resources to meet all the requirements.

## Goals

- Rapidly onboard with languages, frameworks, and tooling we use and love; free from the opinions and design decisions of our previous projects.

- Provide an opportunity for us to observe a novel solution to some well known problems.

- Embed unsolved problems we have discovered and are actively looking for a solution to.

- Discover your strengths and weaknesses, and how they apply to working on a complex project.

- Inform Personal and professional growth paths, and how future work options might enable these.

- Learn something new and have fun!

## Evaluation Criteria

- Ability to follow written instructions with little to no oversight

- Ability to prioritize work requirements while time and resource constrained

- Ability to rapidly learn new tools and frameworks enough to integrate with

- Innovation and critical thinking skills

- Demonstration of knowledge, skills, and abilities as outlined in the [Programmers Competency Matrix](https://sijinjoseph.netlify.app/programmer-competency-matrix/)

## Notes

- You are allowed to negotiate to change or remove any of the requirements in this document. Any changes will be reflected in an updated copy of this document with the changes.

---

## Project Summary

You have been tasked to build a blogging platform using microservices built from a monorepo. Each component will be individually built and packaged into containers and deployed into a local Kubernetes cluster using a published helm chart.

This blogging platform **MUST** support authentication and authorization for user actions. Users **MUST** be able post new articles containing at least a title, description, and collection of keywords. Users **SHOULD** be able to leave comments on the articles, and **SHOULD** be able to up-vote or down-vote articles.

The cluster you will deploy into will be using the [KNative Quick-start](https://knative.dev/docs/getting-started/quickstart-install) and is expected to be run entirely on your laptop with no external services other than hosting services mentioned in the requirements.

Quality of the delivered components is mandatory, using modern engineering practices and capabilities.

## Requirements

- All code **MUST** be stored in version control system and **SHOULD** meet [SLSA Level 3 requirements](https://slsa.dev/spec/v0.1/). This assessment **MUST** use Github and shared with your assessor (repository may be public and made a part of your resume).

- All components **MUST** be contained within this same [Monorepo](https://monorepo.tools/), though each component **SHOULD** be able to be built, tested, delivered, and deployed independently.

- Development **MUST** adhere to [Trust Based Development](https://trunkbaseddevelopment.com/) and **SHOULD** utilize [Continuous Integration and Delivery](https://minimumcd.org/minimumcd/) if possible.

- All commits **MUST** conform to [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) and all components **MUST** be versioned using [Semantic Versioning](https://semver.org/).

- Public APIs **MUST** fully comply with the [EADS](https://dodcio.github.io/eads/) and other [best practice standards](https://standards.rest/) where applicable.

- Documentation **MUST** conform with the [Grand Unified Theory of Documentation](https://documentation.divio.com/) where applicable. The repository and each component **MUST** have a well written [README](https://www.makeareadme.com/
) that **SHOULD** contain:

    - Project Overview
    - Quality Control Badges
    - Build instructions
    - Test instructions
    - API documentation

- Each build artifact **MUST** meet the following criteria during the CI pipeline:

    - Full end-to-end type-safety
    - [Code quality](https://connascence.io/) and linting to [avoid code-smells](https://luzkan.github.io/smells/)
    - [Automated Unit testing](https://kentbeck.github.io/TestDesiderata/)

- Each build artifact **SHOULD** meet the follow criteria during the CI pipeline:

    - Provide a build-time and run-time [Software Bill of Materials](https://ntia.gov/page/software-bill-materials)
    - Provide an automated [CVE vulnerability](https://nvd.nist.gov/vuln/search) check
    - Extended code quality and linting using SonarQube

- All architectural design decisions **SHOULD** be documented as an [ADR](https://adr.github.io/) and stored in the repo. Any (subjectively) significant advice or consultation from non-participants that is used as part of this **MUST** be captured in ADR format and stored accordingly.

- System **MUST** contain at least 3 [microservices](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/ddd-oriented-microservice) each written in different languages. The languages **MUST** be TypeScript, Python, and GoLang. The web client UI may be designed in such a way that a dedicated microservice isn't needed or used, if this applies, the 3rd microservice can be replaced with another [bounded context](https://github.com/ddd-crew/bounded-context-canvas) or eliminated entirely.

- All server to server communication **MUST** utilize [asynchronous communication](https://www.reactivemanifesto.org/) patterns and technology.

- Each service **MUST** [maintain its own database](https://microservices.io/patterns/data/database-per-service.html), and **MUST** never directly access the database of another service. Each database used must be of a different technology from ones already used in this project. The use of databases is optional in case a service is designed that doesn't need one.

- Any client UI to server communications **SHOULD** utilize synchronous communication patterns and technology.

- Design of the system **SHOULD** utilize the [Event Modeling](https://eventmodeling.org/) framework.

- The system as a whole and each component **SHOULD** implement any or all of the observability stack: Logs, Metrics, and Traces.

- The project **SHOULD** contain a User Acceptance Test using browser automation to demonstrate the use of the system end-to-end.

---

## Project Timeline

- Day 1
    - Initial on-brief
    - Q/A

- Day 2
    - Sanity check
    - Tips and tricks

- Day 3
    - General Q/A 
    - Wrap-up prep

- Day 4
    - Out-brief
    - Project discussion

## Evaluation Steps and Day 4 Agenda

- Assessee presentation (optional), quick local demo, and conclusion

- Initialize a new local cluster and install helm chart

```shell
kn quickstart kind -k 1.24.3 -n kind

helm install assessment ...
```

- Run User Acceptance Tests against cluster:

```shell
npm run ...
```

- Review version control contents and commits

```shell
git clone ...

git log
```

- Audience Q/A