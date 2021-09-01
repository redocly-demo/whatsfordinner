# About this site...

This website was created for the Virtual Write the Docs - [West Coast Quorum event](https://www.meetup.com/virtual-write-the-docs-west-coast-quorum/events/278612979/).

The API is not real.
If you like the idea, you're free to take it and make it your own.

## How I used my time?

- 1-hour: Google slides outline (text deck first)
- 1-hour: Correspond with designer about design vision (thanks, Vlad!)
- 1-hour: Refining slides
- 30-minutes: Write draft Quickstart guide
- 2-hours: Rough design and rework of APIs
- 30-minutes: Minor developer portal setup and customization
- 3-minutes: Add to API registry
- 10-minutes: Add portal
- 10-minutes: Set up custom domain
- 30-minutes: Practice run
- 30-minutes: Write this page

## Steps

### Understand the problem

Every API should solve a problem.

Taking time to understand the breadth and depth of the problem, alternatives, and possible solutions is very important.
I did not invest enough time to complete this step.

### Move to the quickstart

The quickstart is important and helps communicate the problem and solution.
It also tackles the developer experience.
A quickstart guide with 25 steps is not so quick and quite slow.

Documentation is very powerful from this perspective.
It helps create empathy for the user.

### Design the API

I start with our [openapi-starter template repo](https://github.com/Redocly/openapi-starter).

I prefer to use a pencil and paper (or ipad and concepts app) to sketch our the various API operations (endpoints and http verbs).

Then, I start by adding a file for each path.
Then, I add a schema for each operation (unless there is already a schema I can reuse).
Finally, I may add the finishing touches -- security, headers, and an "info description".

Along the way I use our `openapi-cli` tool to `lint` and `preview-docs`.

I like seeing the visual docs as feedback.

I like it so much, we're building a VS Code plugin so that I can preview them as I write in a split panel.

Explore the API design repo: https://github.com/redocly-demo/whatsfordinner-api

### Set up the developer portal

I cloned our [developer portal starter](https://github.com/Redocly/developer-portal-starter).
I updated to our latest beta version because I wanted to preview the new reference docs we'll be releasing in the near future.

I did this by editing the `package.json` file:

```json
  "dependencies": {
    "@redocly/developer-portal": "1.1.0-beta.40"
  }
```
And then installed the dependencies:

```sh
yarn install
```

Then, I started adjusting content:

- added a logo
- changed the primary theme color
- added the `quickstart.md` file
- updated the `sidebars.yaml`
- removed the "tutorial" content that is part of the starter
- changed the `index.mdx` content
- changed the `siteConfig.yaml`

Explore the developer portal repo: https://github.com/redocly-demo/whatsfordinner

### Add the API to the API registry

Next, I [added the API to the Redocly API registry](https://redoc.ly/docs/workflows/api-registry-quickstart/).

I copy the registry URL for the next step.

### Add the API to the developer portal

I edit the `siteConfig.yaml` to add the [oasDefinitions](https://redoc.ly/docs/developer-portal/configuration/siteconfig/oasdefinitions/) pointing to my registry URL.

I added a `dinner.page.yaml` file, and enabled some generated code samples within there.

I updated the `sidebars.yaml` to include that `dinner.page.yaml` file.

I committed, pushed to GitHub and added the developer portal to Redocly.

### Set up a custom domain

I purchased a domain name and pointed the DNS to AWS.
I configured AWS route 53 to make a CNAME record for docs.whatsfordinner.dev to point to ssl.redocly.com.
