
# Group 16 – Frontend
Mahmoud Thabit

# Sprint 4
Goals for Sprint 4

Implement at least Three Call/Visualization and Deploy to a server

API: http://augur.osshealth.io/api_docs/

Webite: http://18.218.250.185/


# Deployment
To deploy this application, any server running apache would work however I used AWS


**Step 1**: Create an AWS instance in EC2 (Amazon Linux AMI (HVM), SSD Volume Type)

**Step 2**: select t2.micro with 1GB Memory

**Step 3**: all the default settings are good

**Step 4**: add storage, a recommended size is 8.00 GB

**Step 5**: Add Tages, no changes are needed

**Step 6**: Configuration Security Group: make sure SSH is added, you will need to add HTTP Port: 80 and HTTPS Port: 443

**Step 7**: Review everything before launching an instance.


you will need to login to the server and configure everything

after logging in you need to run some commands
-: sudo yum update -y

-: sudo yum install -y httpd24 php70 mysql56-server php70-mysqlnd

-: sudo service httpd start


now you need to change file permissions so you can upload the code

navigate to ls "/var/www" using command -: ls -l /var/www

after navigating to the directory, run this command -: sudo chmod 2775 /var/www


after that use the preferred method to upload the code to "/var/www/html/" directory.


[https://medium.com/@oreillyalan88/lamp-linux-apache-mysql-php-web-server-on-an-amazon-ec2-linux-instance-e37eb023e996](https://medium.com/@oreillyalan88/lamp-linux-apache-mysql-php-web-server-on-an-amazon-ec2-linux-instance-e37eb023e996)


# Files
- **index.html** (added): the main landing page and contains the code for Top Committer web page

- **index.css** (added): the CSS styling sheet to make the web page look good

- **issue.html** (added): the second web page which displays the Average Issue Response Time

- **summary.html** (added): the third web page which displays the Aggregate Summary per Group

- **fork.html** (added): the fourth web page which displays the number of forks a repo has

- **bar.css** (added): a CSS styling sheet to make sure that all the bar on the web page are uniform


# Dependencies
Database used for the API calls: http://augur.osshealth.io/api_docs/

CanvasJS used for graphs: https://canvasjs.com/assets/script/canvasjs.min.js


# Navigating the website
The top bar will let you navigate the different web pages

The blue buttons are linked to the different repository groups


# Top Committers by percentage:
Will use a pie chart to show the distribution of commits for groups

Purpose: to show a developer how spread out the work is, if the top committer is very dominated, then it is not as spread out.

API: Top Committers (Repo Group) (/repo-groups/:repo_group_id/top-committers)

http://augur.osshealth.io:5000/api/unstable/repo-groups/24/top-committers



# Get Average Issue Response Time:
Will get the Average Issue Resolution Time and display as a bar char

Purpose: to show a developer how long it takes for a Response time to an issue, helps developers see how active members are in each repo and as a repo group.

API: Evolution - Issue Response Time (Repo Group)( /repo-groups/:repo_group_id/issues-maintainer-response-duration)

http://augur.osshealth.io:5000/api/unstable/repo-groups/24/issues-maintainer-response-duration



# Get Aggregate Summary per Group
Will just display the information that give us a summery of what repo group is like("watcher_count", "star_count", "fork_count", "merged_count", "committer_count", and "commit_count")

Purpose: to show a developer basic information on the repo group, for quick evaluation.

API: Aggregate Summary (Repo Group) (/repo-groups/:repo_group_id/aggregate-summary)

http://augur.osshealth.io:5000/api/unstable/repo-groups/24/aggregate-summary



# Get Fork Count of repos based on repot group
Will get the data based on the repo group id and will display all the reports that are in the data, then let the user select the repo that they want to see and the number of forks will be displayed in a bar graph.

Purpose: to show a developer how many people are working or using a repo.

API: Fork Count (Repo Group) (/repo-groups/:repo_group_id/fork-count)

http://augur.osshealth.io:5000/api/unstable/repo-groups/fork-count





# Augur

branch | status
   --- | ---
master | [![Build Status](https://travis-ci.org/chaoss/augur.svg?branch=master)](https://travis-ci.org/chaoss/augur)
   dev | [![Build Status](https://travis-ci.org/chaoss/augur.svg?branch=dev)](https://travis-ci.org/chaoss/augur)

[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/2788/badge)](https://bestpractices.coreinfrastructure.org/projects/2788)

## About Augur

Augur is focused on prototyping open source software metrics.

Functionally, Augur is a prototyped implementation of the Linux Foundation's [CHAOSS Project](http://chaoss.community) on [open source software metrics](https://github.com/chaoss/metrics). Technically, Augur is a [Flask web application](http://augur.osshealth.io), [Python library](https://oss-augur.readthedocs.io/en/dev/library-documentation/python.html) and [REST server](http://augur.osshealth.io/static/api_docs/) that presents metrics on open source software development project health and sustainability.

## Getting Started

**Please follow the 'Getting Started' guide in our [documentation](https://oss-augur.readthedocs.io/en/master/getting-started/getting-started-toc.html).**

Note: we currently only support (most) UNIX systems. If you would like to use Augur but only have access to a non-Unix system, we recommend setting up an Ubuntu 18.04 VM if you can. 
If this is not feasible for you, please reach out to us at [p9j0r6s0m4a0t8v5@augurlabs.slack.com](mailto:p9j0r6s0m4a0t8v5@augurlabs.slack.com) and we will try to help you come up with a solution. In the meantime, if you have Windows and feel so inclined check out issue [#403](https://github.com/chaoss/augur/issues/403) as a starting point until we can finalize a Windows installation.

## Data Collection

Please [follow the instructions](https://oss-augur.readthedocs.io/en/master/getting-started/usage.html#db) for collecting data about specific repositories of interest. We are also currently working on putting together an easily distributable sample database to enable people to get going faster.

<!-- TODO: link to worker docs once they're done -->
<!-- If you are collecting data of your own, you must [start up the workers](./docs/setup/augur-get-workers-going.md). -->

If you have any issues, please feel free to request to email straight into our slack channel [p9j0r6s0m4a0t8v5@augurlabs.slack.com](mailto:p9j0r6s0m4a0t8v5@augurlabs.slack.com) for new developer support!!

## Contributing
----------------

To contribute to Augur, please follow the guidelines found in our [CONTRIBUTING.md](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md). Augur is a welcoming development community that is open to anyone and everyone of every skill level!

Check out our [documentation](https://oss-augur.readthedocs.io/en/documentation/) for information about our system.

Please note we require all commits to be signed off with a [Developer Certificate of Origin](https://developercertificate.org/) in accordance with the [CHAOSS Project Charter section 8.2.1](https://chaoss.community/about/charter/#user-content-8-intellectual-property-policy). This can be easily done by using the `-s` flag when using `git commit`, e.g. `git commit -s -m "Update README.md"`. **Any pull request containing commits that are not signed off will not be eligible for merge until all commits are signed off.** 

## License, Copyright, and Funding
----------------

Copyright © 2019 University of Nebraska at Omaha, University of Missouri and CHAOSS Project at the Linux Foundation

Augur is free software: you can redistribute it and/or modify it under the terms of the MIT License as published by the Open Source Initiative. See the [LICENSE](LICENSE) file for more details.

This work has been funded through the Alfred P. Sloan Foundation.
