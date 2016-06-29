# **History of Enterprise**
_Michelle Ling_   
_Customer Success Intern_  
_Summer 2016_

## Table of Contents
- [**GHE Release 2.0**](#release-two-zero) (2014)
  - [_AWS Availability_](#AWS)
  - [_Split Diff_](#split-diff)
  - [_Pull Request Revert_](#revert)
  - [_SAML_](#SAML)
  - [_High Availability_](#HA)
- [**GHE Release 2.1**](#release-two-one) (2015)
 - [_LDAP Sync_](#LDAP)
 - [_OpenStack KVM_](#OpenStack)
 - [_Organizational Webhooks_](#org-webhooks)
 - [_Status Checks_](#status-checks)
- [**GHE Release 2.2**](#release-two-two) (2015)
  - [_Banner Announcements_](#announcements)
  - [_Azure_](#azure)
  - [_Virtual Studio_](#VS)
  - [_Net Shard Repository Layout (Internal)_](#net-shard)
- [**GHE Release 2.3**](#release-two-three) (2015)
  - [_Admin API_](#admin-api)
  - [_Outbound HTTP Proxy_](#http-proxy)
  - [_GH-Migrator_](#migrator)
  - [Referer Sanitization](#referer)
- [**GHE Release 2.4**](#release-two-four) (2015)
  - [_Protected Branches_](#protected-branches)
  - [_Direct Orgs_](#direct-orgs)
  - [_LFS_](#lfs)
  - [_U2F_](#u2f)
- [**GHE Release 2.5**](#release-two-five) (2016)
  - [_Clustering_](#clustering)
  - [_Design Improvement_](#design)
- [**GHE Release 2.6**](#release-two-six) (2016)
  - [_Templates_](#templates)
  - [_Pre-Receive Hooks_](#hooks)
  - [_Branch Permissions_](#branch-permissions)
  - [_Custom Messages_](#custom-messages)
  - [_Emojis_ :grin:](#emojis)
  - [_Squash Commits_](#squash-commits)
<style>
.resize {
  height: 200px;
}
  .resizemed {
    height: 400px;
  }
</style>

<a id="release-two-zero"></a>
## GitHub Enterprise 2.0
_November 11, 2014_  
Overall, this new version of Enterprise is a major step up from the previous 1.0 series. One of the biggest changes would be the availability of Enterprise on Amazon Web Services. This release marks a whirlwind of new features, ones that are very popular and in frequent use now. These include split diffs, new branch pages, revert pull requests, and SAML and LDAP support. Not only do these mean improved user experience from the old GitHub 1.0, but it also includes availability and Git performance upgrades. From here on, it became easier to create, test, and release GitHub Enterprise. This release led to the more regular release cycle that we see now.
### New Features: <a id="AWS"></a>
**_Amazon Web Service Availability_** - Don't have to incur additional hardware and can easily integrate GitHub into the existing infrastructure.

#### Code Review <a id="split-diff"></a>
- Diffs that are available in **_split view_** allows easier comparison of pull requests and commits side-by-side.  
<img src="https://cloud.githubusercontent.com/assets/98681/4139311/699ef6da-3399-11e4-8d8e-cf0a9e902867.gif" alt="Split Diffs" height= 400px/>

- GitHub Issues have been remodeled to include improved search and filtering with new Issue and PR listing UI
<img  src="https://cloud.githubusercontent.com/assets/700173/4873421/c973d69c-6211-11e4-9aca-e6f8d15a0ff7.gif" alt="Branches"/>
- A new **_branches page_** allows you to filter branches by ones you've created, review most active ones, clean stale branches, examine failing branches, and open pull request directly.  
<img src="https://cloud.githubusercontent.com/assets/296432/3329568/2230969e-f7c8-11e3-8cc9-70fd67e95ad6.png" alt="Branches"/>

<a id="revert"></a>
- Revert merged commits using the new **_pull request revert button_**!
- After there has been enough discussion, administrators can **_lock conversations_** so other users can no longer comment.  
- New Integrations are also available with [Snap](https://www.snap-ci.com/) and [Code Review Hub](https://www.snap-ci.com/)

#### Project Management
- **_Filter different issues_** by author, label, milestone, open/close state as well as with advanced search terms.  
- Two new **_pages of labels and milestones_** to track issues.  
- Watch **_progress of issues_** such as owner changes, issue title changes, labels, milestones, and task lists.  
<img src="https://enterprise.github.com/assets/releases/2.0.0/screenshot-issue-tracking-8ae591af0801c511df74c4c567a30cbef967a59be2dcccc946d61a9cc4932aed.jpg" alt="Issue Progress" height = 150px/>

- Now, whenever someone else is assigned an issue, they will receive an **_email or web notification_**.  
- New integrations are also available with [TinyPM](http://www.tinypm.com/) and [Bugzilla](https://www.bugzilla.org/releases/4.4.3/).

##### New Software Development Integrations
- With the Deployments API, now there are **_notifications in the conversation timeline for pull requests_** that are in testing, staging, or production environments.  
<img src="https://enterprise.github.com/assets/releases/2.0.0/screenshot-commit-deploy-04c7cab9b1aaffab00e08c4930f539e1e09dc6933643ff24adb41850b58a1786.jpg" alt="Deployment Status" height = 150px/>

- New integrations available with [Heroku](https://www.heroku.com/), [Visual Ops](http://www.visualops.io/), [GO](https://www.go.cd/), and [OpsWorks](http://aws.amazon.com/opsworks/).

<a id="SAML"></a>
##### Enhanced Authentication and Security
- **_SAML (Security Assertion Markup Language) support_** added. Providers that can now be used with GitHub Enterprise include OneLogin, PingIdentity, Okta, and Shibboleth.
- More **_LDAP (Lightweight Directory Access Protocol) support_** includes Active Directory, FreeIPA, Oracle Directory Server Enterprise Edition, OpenLDAP, Open Directory, and 389-ds.
- Now there is **_auditing_** for accounts, teams, and repository access. Team member activity and event location can be traced.  
<img src="https://enterprise.github.com/assets/releases/2.0.0/screenshot-audit-log-filter-ba55ce639f987c22fc41411b1e489c1ef550afa19799c7166a465d27f6038fbf.jpg" alt="Audit Log" height =150px/>

- **_Two-factor authentication improvements_** include a TOTP (time-based one-time password) application as well as reminders for recovery code download in case of a lock out.
- With the use of **_Ubuntu 12.04 LTS_**, GitHub Enterprise can take advantage of updates and security fixes for Ubuntu. Sudo access (users can run programs with security privileges of another user) is now available for the admin which means more direct control.

#### Other features
- Better Pages running with 300+ advanced features.  
- PSD rendering is now added to Github's image viewing and diffing capabilities. This includes three image view modes that allow you to see the images inline and what has changed in a commit.  
<img src="https://enterprise.github.com/assets/releases/2.0.0/screenshot-psd-diffs-3422c8b489fba3c1f0025c6bc834b8fe8a15eb7e09e102140d4e3f4f7dc7811c.jpg" alt="PSD" height= 150px/>

<a id="HA"></a>
- **_High Availability_** allows you to have two separate instances (one primary and one replica) and the replica will automatically replicate any data in the primary instance. If anything happens to the first one, the admin can switch users to the other instance.

[More Details About the 2.0 Release](https://enterprise.github.com/releases/2.0.0)  
[Full release notes](https://enterprise.github.com/releases/2.0.0/notes)  
[GitHub Enterprise Blog on Enterprise 2.0](https://github.com/blog/1918-a-faster-more-flexible-github-enterprise)  
[GitHub on AWS](https://vimeo.com/111525512)  
[Sales Markdown File on 2.0](https://github.com/github/sales/blob/master/resources/ent-2-guide.md)

---
<a id="release-two-one"></a>
## GitHub Enterprise 2.1  
_January 20, 2015_  
This version of Enterprise continues to provide users what they have told us they want. In the 2.1 release, GitHub Enterprise has features like LDAP sync and webhooks to improve organizational efficiency as well as status checks and deployment tooling in order to streamline the development process. Users and admins are provided with more control and functionality.
<a id="LDAP"></a>
### New Features:
**_LDAP Sync_** - GitHub Enterprise integrates with the LDAP Directory even further by automating identity and access management. User sync means more easier provisioning and deprovisioning directly from LDAP. Team sync allows automatic granting of repository access to users. LDAP Sync scales with directory structure and works well with nested groups. Diagnostic tools are included as well to enable auditing of team and user syncing.  
<a id="OpenStack"></a>
**_OpenStack KVM_** - combined flexibility of cloud-based infrastructure with compliance-related benefits of internally managed hardware.
#### Improved Audit Log
- New details such as action that was performed, which repository that occurred, which user performed the action, which organization an action pertained to, which country it happened, date and time of action.
- This will result in better security of users and data.
- New **_monitoring dashboard_** for administrators that gives data around disk usage, CPUs, memory, etc.
- Use the `ghe-btop` command to see which Git operations are currently running.  
<img src="https://enterprise.github.com/assets/releases/2.1.0/screenshot-maintenance-dash-13ce92e4b81062ea5615b8984042ab41cb007cc2b0f52300a9d4e85f56669b45.jpg" alt="New Auditing" />

<a id="org-webhooks"></a>
#### Configure Organization Webhooks
- Save time with **_integrations across multiple repositories_**.
- Send events for all repositories in an organization.
- New events for things like repository creation, team membership, etc.
- Possible configurations: repository push, pull request opened, GitHub Pages site built, new member added to a team, etc.  
<img  src="https://enterprise.github.com/assets/releases/2.1.0/screenshot-webhooks-ced793bca08d148151a6fb8aabc54418a52d79d8503fedc0eed1035a5f407eaf.jpg" alt="Webhooks" height = 200px/>

#### Deployment Tooling
- GitHub Enterprise provides you with the ability to **_automate your software to your end users_**.
- Developers don't need to worry about implementation details of delivering applications if they use the [GitHub's Deployments API](https://developer.github.com/v3/repos/deployments/).

<a id="status-checks"></a>
#### Status Checks
- Improve the quality of your code using [GitHub's Status API](https://developer.github.com/v3/repos/statuses/) which will include the **_status of a pull request_** within the conversation.
- See all status checks at once now from many CI systems that test code against different platforms, as well as security tests and code coverage analyses.
- Commit history is easily accessible.  
<img src="https://enterprise.github.com/assets/releases/2.1.0/screenshot-status-checks-55012772375b58cdee8c80fc41704ba2ba0049f304653df72d8943149f8ffb69.jpg" alt="Status Checks" height =200px/>

#### /Pulls and /Issues pages
- **_New Issues and Pull Requests Dashboards_** allow developers to keep track of everything and manage their work across all repositories with easier
- Custom advanced search filters also let them save their own often-used searches  
<img src="https://enterprise.github.com/assets/releases/2.1.0/screenshot-dashboards-9320b52fcfbd0caebadad6f86ef150836fa3170f9867e59e129b6703e21494fd.jpg" alt="Pulls and Issues Dashboard" height=200px/>

#### SVG Files
- GitHub Enterprise can now render SVG files.
- This means **_direct browsing and viewing of SVG assets_** as rendered images and the ability to compare changes to SVG files over time.  
- GitHub also displays PNG, JPG, GIF, and PSD.

[More Details About the 2.1 Release](https://enterprise.github.com/releases/2.1.0)  
[Full Release Notes](https://enterprise.github.com/releases/2.1.0/notes)  
[Blog Post](https://github.com/blog/1947-announcing-github-enterprise-2-1-0)  
[Sales Markdown File for 2.1](https://github.com/github/sales/blob/master/resources/ent-2.1-guide.md)

---
<a id="release-two-two"></a>
## GitHub Enterprise 2.2
_April 29, 2015_  
GitHub Enterprise 2.2 expands the possible workflows by incorporating new mobile features and better support for Microsoft tools including Azure and Visual Studio. Git LFS is now rolled out first on GitHub Enterprise.

### New Features:
<a id="VS"></a>
**_Visual Studio_** - The new extension allows you to connect your GitHub repositories in Visual Studio. This way, you don't need to leave your IDE (integrated development environment) and you can directly clone, create and publish repositories.   
![Visual Studio](https://enterprise.github.com/assets/releases/2.2.0/screenshot-visual-studio-bb0e735280cbe6e2e4b3b07b4e079b4a556a9a0e0f62059c807258852e24bffa.jpg)
<a id="azure"></a>

**_Azure_** - By enabling deployment onto Azure, you can easily host GitHub Enterprise in the Windows ecosystem with no need to change the environment you've already built.   
<img src="https://enterprise.github.com/assets/releases/2.2.0/screenshot-azure-7b8196ae91c7fa04f3ab771ce3a36fa6e463af211afb676f21374a80ab4e068a.jpg" width= 600px />

New deployment platforms **_Hyper-V_** and **_XenServer_** are now supported as well.

#### Faster changes
- Now you can commit or propose a change to a new branch, then **_immediately open a pull request_** for discussion and review.
- Also, with the commit composer, you can add the commit to the current branch or to a new branch. This keeps the master branch tidy.  
<img src="https://enterprise.github.com/assets/releases/2.2.0/screenshot-branch-pull-request-49d4315d39f80e299e0c37fd24f67663e57507b3cc8c7933bbf7125b0d06ab3b.jpg" alt="Commit Composer" height =200px/>

**_PDFs_** - view PDF files in Enterprise. This way once you click on the link after browsing or uploading a PDF, then you can view it as a rendered image.

#### Phone improvements
- Get GitHub notifications on your phone!  
- Easily navigate branches  
<img src="https://enterprise.github.com/assets/releases/2.2.0/screenshot-mobile-branches-099481d0c983b1e2c104e64df3caca98217806eabfd1a6974d11e1ba461750da.png" alt="Phone Branches" height =300px/>

<a id="announcements"></a>
#### Announcements
- Generate announcement banners about new features, ongoing service issues, etc and answer user concerns without having to respond to reports.
- Run the command `ghe-announce -s` with your own message on the SSH admin console  
<img src="https://enterprise.github.com/assets/releases/2.2.0/screenshot-announcement-0a62faa69e0fc95a09816e0d830ceb74feea1aba0997b9056672d476fb0ae0b7.jpg" alt="Announcements" />

<a id="net-shard"></a>
#### Other
- Net-shard Repository Layout deals with the structure of data within an instance. This impacts those that use forks the most and is predicted to reduce disk usage by about 50%. This opens the door to scale-out architecture.
- Upgrading to 2.2 will involve a data migration, and may present some complications. Important details can be found in the Sales Markdown File listed below.
- Replication (HA) is improved as well with the inclusion of `git-repld` and will place less of a burden on the primary instance.

[More Details About the 2.2 Release](https://enterprise.github.com/releases/2.2.0)  
[Full Release Notes](https://enterprise.github.com/releases/2.2.0/notes)  
[Sales Markdown File for 2.2](https://github.com/github/sales/blob/master/resources/ent-2.2-guide.md)

---
<a id="release-two-three"></a>
## GitHub Enterprise 2.3
_August 4, 2015_  
Enterprise 2.3 offers more control to both users and administrators by expanding monitoring, simplifying migrations, and adding new features and APIs. All of this and more done with even greater security.

### New Features:
<a id="admin-api"></a>
#### Admin Control
- **_New APIs for administrators_** offer flexibility in creating new flows and when provisioning new accounts and listing organization details.
- Possible APIs:
 - [Create a user account](https://developer.github.com/v3/users/administration/#create-a-new-user)
 - [Create impersonation token for users](https://developer.github.com/v3/users/administration/#create-an-impersonation-oauth-token)
 - [Rename a user](https://developer.github.com/v3/users/administration/#rename-an-existing-user)
 - [Create an organization](https://developer.github.com/v3/enterprise/orgs/#create-an-organization)
 - [List all organizations](https://developer.github.com/v3/orgs/#list-all-organizations)
- [Documentation](https://developer.github.com/v3/users/administration/)
<a id="migrator"></a>
- Migrations are made much simpler with `ghe-migrator` which helps you **_move from one GitHub instance_** to another
- It's now simple to move your organization, users, teams, and repositories from GitHub.com to GitHub Enterprise  
<img  src="https://enterprise.github.com/assets/releases/2.3.0/screenshot-migration-afd72b2c5086847b69b6a063cdb3d5e1ec5cdc54d203a664ebe3a1e959921591.jpg" alt="Migrator" />

<a id="http-proxy"></a>
- Outbound HTTP proxies allows you to **_integrate the tools_** you want **_within the security of an enterprise environment_**. This way you can safely use your favorite apps and services with your firewall.
- **_Advanced monitoring_** enables you to see the state of queues for background jobs and emails as well many other metrics and information for MySQL, Redis, and ElasticSearch.
<img src="https://enterprise.github.com/assets/releases/2.3.0/screenshot-monitor-2c64f028fb8ebd435fa036079c4c3e75d517209954859364a6e2c29b56190f4f.jpg" alt="Advanced Monitoring" />

#### Security Updates
- Better **_RSA key validations_** prevent weak and invalid SSH keys from working.
- Referrer headers on requests are no longer sent and ensures that the location of your Enterprise instance is not leaked.

#### Other
- **_Preview comments_** and  comment edits before posting.
- **_Filter_** pull requests by the **_status of commits_** using the Status API and filters such as: `status:success`, `status:failure`, `status:pending`.
- Now, there is greater customization of permissions with read only deploy keys. Deploy keys will now be read-only by default.

[More Details About the 2.3 Release](https://enterprise.github.com/releases/2.3.0)  
[Full Release Notes](https://enterprise.github.com/releases/2.3.0/notes)  
[Blog Post](https://github.com/blog/2043-github-enterprise-2-3-is-now-available)  
[Sales Markdown File for 2.3](https://github.com/github/sales/blob/master/resources/ent-2.3-guide.md)

---
<a id="release-two-four"></a>
## GitHub Enterprise 2.4  
_October 13, 2015_  
GitHub Enterprise 2.4's biggest improvements include protected branches and Git LFS which enables large file storage as well as other smaller feature upgrades like U2FA and GeoJSON. The customer feedback issues tackled here are workflow and permissions.

### New Features:
<a id="protected-branches"></a>
#### Protected Branches and Required Statuses
- Protected branches give administrators the ability to **_disable force pushes_**, prevent deletion, and enforce required status checks.
- **_Required statuses_** ensure that no branches will be merged until these checks have passed.
<a id="direct-orgs"></a>

#### Improved Organization Permissions
- Now there are **_customizable_** member privileges, specific team permissions, managed access, and transparent communication with team mentions now.
- This is also known as **_Direct Orgs_** and is meant to increase transparency and control while easing Ownership burden and making Teams more self-manageable. Fine-grained team permissions will reduce Site Admin efforts.
- Now Direct Orgs members can mention teams they don't belong to.
<a id="LFS"></a>

#### Git Large File Storage
- With Git LFS you can **_integrate large binary files_** into your workflow.
- Large files are **_stored on your server_** and you can easily transfer any number of files easily.

#### GitHub Pages Improvements
- The GitHub Pages can be accessible to the public even if the instance is private.
- With the [jekyll-feed](https://github.com/jekyll/jekyll-feed) plugin, one can right away generate an Atom feed of most recent posts.

#### GeoJSON
- Any GeoJSON file will be automatically rendered as an **_interactive map_**.
- The display of these files are also easily customizable
<a id="U2F"></a>

#### U2F
- Use physical key placed in your USB port to authenticate.
- GitHub Enterprise now supports FIDO [Universal 2 Factor Authentication](https://www.yubico.com/about/background/fido/)

#### Merge Button Updated Design
- Generate situational awareness regarding the status of a PR. Created visualization of all possible situations.
- Update branch before merging.  
<img  src="https://cloud.githubusercontent.com/assets/1852630/10234191/fe6fdf34-6860-11e5-8f40-9856b54a2eba.jpg" alt="Update" />

- Failed statuses  
<img  src="https://cloud.githubusercontent.com/assets/1852630/10233998/d6727ab0-685f-11e5-8c93-89650a9bfaae.jpg" alt="Failed Status" />

- Merge conflicts.  
<img  src="https://cloud.githubusercontent.com/assets/1852630/10234115/8a2323de-6860-11e5-8eb3-47086068e55d.jpg" alt="Merge Conflicts" />

[Release Notes](https://enterprise.github.com/releases/2.4.0/notes)  
[Blog Post](https://github.com/blog/2076-github-enterprise-2-4-is-now-available)  
[Sales Markdown File on 2.4](https://github.com/github/sales/blob/master/resources/ent-2.4-guide.md)

---
<a id="release-two-five"></a>
## GitHub Enterprise 2.5
_February 9, 2016_  
Version 2.5 continues to deliver improvements on GitHub Enterprise by focusing on helping growing teams scale and use the same features on a larger level all enhanced by a new, simplified design.

### New Features:
<a id="clustering"></a>
#### Clustering
- GitHub now uses clustering and **_spreads the workload across multiple instances_** to help administrators add users to larger installations.
- This is mainly targeted towards teams with **_10,000+ developers_**.
- This does require some additional administrative support and resources.
<img src="https://enterprise.github.com/images/releases/2.5.0/diagram-clustering.png" alt="Clustering"/>

#### Protected Branch Improvements
- By implementing **_protected branches that scale_**, you can safely maintain a project's conventions and collaborate safely in large teams.
- Protected Branches API
- **_Advanced settings_** now available in Admin center with an improved UI.
- Previous 2.4 version  
<img  src="https://cloud.githubusercontent.com/assets/1852630/12331442/8839459a-bab7-11e5-9406-a0b449db5654.jpg" alt="Old Advanced" width = 500px/>
- New 2.5 version  
<img  src="https://cloud.githubusercontent.com/assets/1852630/12330741/9c7da2b0-bab4-11e5-86d4-53027684d7b0.png" alt="New Advanced" height= 400px/>

<a id="design"></a>
#### Design improvements
- **_New, simplified designs_** for the repository and sign-in screens.
- The repository screen has been redone to improve navigation and simplify the page layout while improving code performance under the hood. Now there is more space to see what is actually in the repository with the repository navigation moved to the top.
- Old 2.4 version  
<img src="https://cloud.githubusercontent.com/assets/1852630/12264871/8d06cf40-b907-11e5-98ff-ed33db734624.jpg" alt="Old Repo" height =350px/>

- New 2.5 version  
<img  src="https://cloud.githubusercontent.com/assets/1852630/12264901/c6a407a4-b907-11e5-929a-fd10d5c501c0.jpg" alt="Repository Screen" height= 350px />

- The new sign-in screen is much simpler with an obvious sign-up link.

#### Extended Subversion support as well to versions 1.8 and 1.9  
##### Increased Resilience to many users fetching the same data at the same time or a "thundering herd" with `lariat`
##### Deprecation of version 2.0 and 2.1

[More details about the 2.5 Release](https://enterprise.github.com/releases/2.5.0)  
[Full Release Notes](https://enterprise.github.com/releases/2.5.0)  
[Blog Post](https://github.com/blog/2108-github-enterprise-2-5-is-now-available)  
[Sales Markdown File on 2.5](https://github.com/github/sales/blob/master/resources/ent-2.5-guide.md)

---
<a id="release-two-six"></a>
## GitHub Enterprise 2.6  
_April 26, 2016_  
The 2.6 release focuses on introducing new tools and updates to enable more efficient, flexible and friendly processes for development teamwork. These tools, such as Issue templates and pre-receive hooks, will save time, and 2.6 seeks to also stimulate productive conversation that allows for efficient code review.


### New Features:
<a id="templates"></a>
#### Templates for Issues and Pull Requests
- Administrators can help their team add details at the beginning of a thread.  
<img src="https://enterprise.github.com/assets/releases/2.6.0/issue-screenshot-3460801ed475eb32d55b00e87c2268e39c3e9786626c9b8cd047d04a8584f900.png" alt="Templates"/>

<a id="hooks"></a>
#### Pre-receive Hooks
- Use hooks to enforce **_organization-wide push policies_** and optimize code before it even gets to GitHub. Set conditions upon which commits can be allowed. Should be used with caution.
- Use [this documentation](https://help.github.com/enterprise/2.6/admin/guides/developer-workflow/creating-a-pre-receive-hook-environment) for details on pre-receive hooks.

<a id="branch-permissions"></a>
#### Flexible Protected Branches
- Merge out-of-date pull requests and set restrictions on the users and teams that can merge.
- This includes **_branch permissions_**. Now you can restrict push access to a branch. This way you can authorize only specific individuals and teams to have push access to a branch.

<a id="custom-messages"></a>
#### Communication at scale
- Set up **_custom messages_** to share on the GitHub Enterprise sign-up page.
- Write messages for suspended users.
- Share across teams without affecting GitHub's user experience.

#### New File-sharing
- You **_no longer have to use the command line_** to share files.
- This makes things easier for those not used to working with the command line to share files directly with developers.  
<img src="https://enterprise.github.com/assets/releases/2.6.0/drag-screenshot-ac387851bfb533c3ec605ed2df84ae7662405cb0c60b8b835471d38e84561582.png" alt="Drap and Drop"height = 200px/>

#### Easier Text Formatting
- Style now **_without the use of Markdown_**.
- Will do some work for you while helping you learn.  
<img src="https://enterprise.github.com/assets/releases/2.6.0/markdown-screenshot-6eee30ecbe2f45c34db82044af0188fd9cd5ae2074f57145c62927278b3d3ec4.png" alt="No Markdown" height = 200px/>

<a id="emojis"></a>
#### Conversation Add-ons
- Instead of simply "+1's", now there are a **_range of emojis_** for reactions in any conversation. :tada:  
<img  src="https://enterprise.github.com/assets/releases/2.6.0/emoji-screenshot-993a3430163b0f111d260e9e406e19fc1f5d9ab275588c0392e0d130260b1edd.png" alt="Emoji" height = 200px/>

#### Saved Replies
- Save time by saving your most frequently used replies to easily reuse.  
<img  src="https://enterprise.github.com/assets/releases/2.6.0/saved-reply-screenshot-85be81d409e7b1e1ca7ba30930e1baef13e9d7f28a2fc64cbb9027a869e3c5d4.gif" alt="Saved Replies" height= 200px/>

#### Code Review Tools
- Find things faster by using the files list to search by extensions and filter by filename.  
<img src="https://cloud.githubusercontent.com/assets/143418/13788233/3f8073cc-ea9c-11e5-8e49-28ac89a46cce.png" alt="Search Filters" height = 200px/>

- Have the option to be able to use a **_commit-by-commit workflow_** where each commit is isolated for review. The new commits list makes it easy to review these commits. This includes keyboard shortcuts for ease of navigation.
- **_More context comes with comments_** now with the option to view a full outdated diff.
- View the changes that have occurred since you last left off. This is done by a **_timeline indicator_**.  
<img src="https://cloud.githubusercontent.com/assets/143418/13412752/5bdcc3c0-defa-11e5-97cb-75a92b544d94.png" alt="Timeline" />

<a id="squash-commits"></a>
#### Squash Commits
- Squash merging allows for a **_tidier history_** that can be much easier to read. This is when a number of commits are combined into a single commit. It still contains all of the pull request changes, but omits the individual commits from Git History.
<img src="https://github-images.s3.amazonaws.com/enterprise/2.6/assets/images/help/pull_requests/squash-and-merge.png" alt="Squash Merging" />

#### HA Replication Live Synchronization
- With 2.6, the settings, license data, and keys are updated in real time. `ghe-repl-sync-settings` can also be used to force synchronization.
- `ghe-repl-status` is also useful in checking the status of replication and only allows replication between identical GHE versions and will identify what the current replica is.

[More details about the 2.6 Release](https://enterprise.github.com/releases/2.6.0)  
[Full Release Notes](https://enterprise.github.com/releases/series/2.6)  
[Blog post](https://github.com/blog/2157-github-enterprise-2-6-is-here-with-faster-more-approachable-workflows)
