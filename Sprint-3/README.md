#Group 16 – Frontend
Mahmoud Thabit

#Sprint 3
Goals for Sprint 3
Implement at least Three Call/Visualization
API: http://augur.osshealth.io/api_docs/
Webite: http://18.218.250.185/

#Top Committers by percentage:
Will use a pie chart to show the distribution of commits for groups
Purpose: to show a developer how spread out the work is, if the top committer is very dominated, then it is not as spread out.
API: Top Committers (Repo Group) (/repo-groups/:repo_group_id/top-committers)
http://augur.osshealth.io:5000/api/unstable/repo-groups/24/top-committers


#Get Average Issue Response Time:
Will get the Average Issue Resolution Time and display as a bar char
Purpose: to show a developer how long it takes for a Response time to an issue, helps developers see how active members are in each repo and as a repo group.
API: Evolution - Issue Response Time (Repo Group)( /repo-groups/:repo_group_id/issues-maintainer-response-duration)
http://augur.osshealth.io:5000/api/unstable/repo-groups/24/issues-maintainer-response-duration


#Get Aggregate Summary per Group
Will just display the information that give us a summery of what repo group is like("watcher_count", "star_count", "fork_count", "merged_count", "committer_count", and "commit_count")
Purpose: to show a developer basic information on the repo group, for quick evaluation.
API: Aggregate Summary (Repo Group) (/repo-groups/:repo_group_id/aggregate-summary)
http://augur.osshealth.io:5000/api/unstable/repo-groups/24/aggregate-summary


#Get Fork Count of repos based on repot group
Will get the data based on the repo group id and will display all the reports that are in the data, then let the user select the repo that they want to see and the number of forks will be displayed in a bar graph.
Purpose: to show a developer how many people are working or using a repo.
API: Fork Count (Repo Group) (/repo-groups/:repo_group_id/fork-count)
http://augur.osshealth.io:5000/api/unstable/repo-groups/fork-count
