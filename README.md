# Crownpeak Demo Experience - Front End Development

This application is developed using [Patternlab](http://patternlab.io/). Initial code reposiroty is created by cloning the latest stable version of [parrenlab node & gulp edition](https://github.com/pattern-lab/edition-node-gulp/releases/tag/v1.3.4). This provides us necessary configurations and tasks for development using `node` and `mustache` templates. On top of this, [`starterkit-mustache-demo`](https://github.com/pattern-lab/starterkit-mustache-demo) is added to source files which include demo Atoms, Molecules, Organisms, templates and Pages. Front End development references the demo code and creates necessary patterns. **Demo code is to be used only for development reference, Final deliverable shouldn't include any demo code included by starterkit**.

# Initial Local Environment Setup

### Clone Repo

Clone the repo locally:

    git clone https://github.com/epsilondigital/CrownPeak-Demo-Experience.git

### Install Project-Specific Dependencies

> Note: Pattern compilation is done with [Node](https://nodejs.org/), uses [npm](https://www.npmjs.com/) to manage project dependencies, and [gulp.js](http://gulpjs.com/) to run tasks and interface with the core library. If you don't have these installed on your machine, you will need to install them before attempting to run the commands below.

Go to root folder (`/CrownPeak-Demo-Experience`) in terminal and install all Node modules needed for development:

    npm install

# Local Development

### Building from Source

All source code is present in `./source` folder. Navigate to root (`/CrownPeak-Demo-Experience`) folder in terminal and use following command to build `./source` code and generate files for public view.

        gulp patternlab:build

This command compiles all patterns and generates static assets (HTML, CSS, JS) in `./public` directory. Contents of this folder will be the files deliverable to CMS development team.

**Note: It is important to ensure not to edit contents in `./public` directory. This directory contains latest compiled resources and any changes made in this folder will be lost when the patterns are built next time.**

### Viewing

Use the following command to view static files generated:

        gulp patternlab:serve

This serves compiles pages on [http://127.0.0.1:3000](http://127.0.0.1:3000). This also watches for changes in files and reloads compiled files.

Optionally, we can run the following command to watch for changes and build the code automatically whenever there are some changes without having to manually run the build command again.

        gulp patternlab:watch

# Deployment
Follow the steps below for deployment to QA and UAT instances -
* Commint all `source` folder contents to develop branch.
* Run build command `gulp patternlab:build`.
* Commit build output folder `public` to develop branch.
* Raise a PR to merge `develop` branch to `qa` branch.
* Merge this PR and it would automatically deploy the changes to QA instance [http://cpde-qa.d.epsilon.com/](http://cpde-qa.d.epsilon.com/).
* Once QA verifies the changes, raise another PR to merge `qa` branch to `uat`.
* Merge this PR and then go to [https://jenkins-master.d.epsilon.com/job/CP%20-%20cpde-uat.d.epsilon.com%20-%20S3/](https://jenkins-master.d.epsilon.com/job/CP%20-%20cpde-uat.d.epsilon.com%20-%20S3/).
* Run Build from here and it would deploy changes to UAT instance [http://cpde-uat.d.epsilon.com/](http://cpde-uat.d.epsilon.com/).

# Additional Notes
Note that there are multiple versions released for Patternlab node & gulp edition after the stable version release. However, there is some [issue](https://github.com/pattern-lab/edition-node-gulp/issues/117) which apparently is fixed, but still happens in many versions. So, we use most recent stable version released. We need to ensure this issue doesn't happen if we're upgrading to any later version.

# Useful Links
Some links for references related to Atomic development -
1.  Atomic Design - [http://bradfrost.com/blog/post/atomic-web-design/](http://bradfrost.com/blog/post/atomic-web-design/)
1.  Pattern Lab - [http://patternlab.io/](http://patternlab.io/)
1.  Pattern Lab Docs - [http://patternlab.io/docs/index.html](http://patternlab.io/docs/index.html)
1.  Pattern Lab Node version repo - [https://github.com/pattern-lab/patternlab-node](https://github.com/pattern-lab/patternlab-node)
1.  Pattern Lab Starterkits - [https://github.com/pattern-lab?utf8=%E2%9C%93&q=starterkit&type=&language=](https://github.com/pattern-lab?utf8=%E2%9C%93&q=starterkit&type=&language=)
1.  Mustache Template system - [https://mustache.github.io/](https://mustache.github.io/)
