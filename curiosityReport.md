# Curiosity Report

> "One that I haven't tried, but that looks interesting is upptime. Upptime makes extensive use of GitHub. A scheduled GitHub Actions workflow monitors the website and updates GitHub Pages to display the status. GitHub Issues are used to track an incident and the results are automatically integrated into the status page.
>
> 💡 If you are looking for a curiosity project, this might be a good one to try. I would love to hear about your experience."
>
> > Lee Jensen _(Presumed)_

### Summary

Upptime is easy to use and set-up, it works great, the base instructions are pretty good, but the set up for the custom domain is lacking; there is nothing to ping on the factory, or atleast it seems that they expect a 200 response code, as such the factory by default is marked as unresponsive. I tried varaious ways to properly report the uptime of the factory. I also experimented with some styling for the status page, which is viewable [here](https://pizza-status.evankchase.click).

I also investigated some alternatives based off of [this list](https://github.com/ivbeg/awesome-status-pages), but despite there being several good options, the clairty of Upptime, along with my familiarity with github actions made Upptime the most attracting option.

### Process

1. First I visited the Upptime [repo](https://github.com/upptime/upptime) which lead me to their website.
2. Following the instructions provided with the [Getting Started](https://upptime.js.org/docs/get-started) page I was able to set-up the basic status page.
3. I set-up the custom domain for the github page following the instructions provided in [Deliverable 2](https://github.com/devops329/devops/blob/main/instruction/deliverable2AutomatedDeploy/deliverable2AutomatedDeploy.md#assigning-a-custom-domain).
4. Modified the provided `upptimerc.yml` file to add my staging site, the service and the factory page.
5. Because the factory was considered down, I was able to observe what an incident report looks like when submitted to the repo about a site being down, a happy accident.
6. I dug through the code of the jwt-pizza-factory repo to identify possible endpoints that I could ping to detect if a page was up, I determined to visit the `/api/docs` page, but a user could visit any of the other pages, or mark `404` as the expected page using the options provided in the [configuration docs](https://upptime.js.org/docs/configuration) from Upptime, however as the factory actually being down could yeild `404` responses, I felt using `/api/docs` was the best method.
7. Intrestingly once the url was adjusted the opened issue was auto-magically closed once it detected the site was back up.
8. I played around with customization of the appearance of the page based on the instructions in the [configuration docs](https://upptime.js.org/docs/configuration).
9. Finally I looked at some alternatives to Upptime, found via Google and [this list](https://github.com/ivbeg/awesome-status-pages), but they all seemed at best equivelent, and many required additional set-up or accounts.

### Instructions

##### Create the Repository

1. Visit the [Upptime Repo](https://github.com/upptime/upptime)
2. Click the green `Use this template` > `Create a new repository`
3. Check the `Include all branches` box
4. Name the repository `jwt-pizza-status`
5. Give it a description like: `Status page for the JWT Pizza service`
6. Click `Create repository`

##### Add Access Token to the Repo

1. Click on your profile and go to Settings
2. Goto Developer settings.
3. Personal access tokens > Fine-grained tokens
4. Click `Generate new token`
5. Name the token `jwt-pizza-status` and give it a description such as `Token for the Upptime repository for the JWT Pizza Status page`
6. Set the expiration for sometime after the semester ends
7. Change Repository Access to `Only select repositories` and select your `jwt-pizza-status` repo.
8. Under `Permissions` > `Repository permissions` enable read-write access for Actions, Contents, Issues and Workflows
9. Hit Generate token, then once more.
10. > [!IMPORTANT]
   > Copy the token, do not lose this
11. Return the `jwt-pizza-status` repo
12. Goto Settings > Secrets and variables
13. Add a new Repository secret, the name of the secret is `GH_PAT` the value is the token you copyied.
14. Hit `Add secret`

##### Configure the remained of the repository

15. Follow the instructions found in Deleverable 2 under Assigning a custom domain [here](https://github.com/devops329/devops/blob/main/instruction/deliverable2AutomatedDeploy/deliverable2AutomatedDeploy.md#assigning-a-custom-domain) except the record name should be for `pizza-status` rather than just `pizza`.
    > [!NOTE] Be sure the value for the CNAME is just `youraccounthere.github.io` and not the full path to the status page.
16. Return the main page for the `jwt-pizza-status` repo and click on the `.upptimerc.yml`
17. Hit the Edit this file pencil.
18. Replace the contents of the file with:

```yml
owner: YOURACCOUNTHERE # Your GitHub organization or username, where this repository lives
repo: jwt-pizza-status # The name of this repository

sites:
  - name: JWT-Pizza
    url: https://pizza.byucsstudent.click/
  # - name: JWT-Pizza (DEV)
  #   url: https://stage-pizza.byucsstudent.click/
  - name: JWT-Pizza Service
    url: https://pizza-service.byucsstudent.click/
  - name: JWT-Pizza Factory
    url: https://pizza-factory.cs329.click/api/docs

status-website:
  cname: pizza-status.byucsstudent.click
  favicon: https://raw.githubusercontent.com/devops329/jwt-pizza/main/public/jwt-pizza-icon.png
  logoUrl: https://raw.githubusercontent.com/devops329/jwt-pizza/main/public/jwt-pizza-logo.png
  name: JWT Pizza Status
  theme: light
  introTitle: "**JWT Pizza** is a pizza buying service made by the BYU CS329 team."
  introMessage: This is a simple satus page displaying the up time of the JWT-Pizza service, made using [upptime](https://github.com/upptime/upptime).
  navbar:
    - title: Status
      href: /
    # - title: Class Repo
    #   href: https://github.com/devops329/devops
    - title: Website
      href: https://github.com/$OWNER/jwt-pizza
    - title: Service
      href: https://github.com/$OWNER/jwt-pizza-service
    # - title: GitHub
    #   href: https://github.com/$OWNER/$REPO
# Upptime also supports notifications, assigning issues, and more
# See https://upptime.js.org/docs/configuration
```

19. Replace `YOURACCOUNTHERE` with your github account name
20. Replace all references to `byucsstudent` with your domain name.
21. Commit the changes
22. Navigate to the Actions tab, once all the actions have run you can visit your status page
23. Feel free to customize your status page following the instructions [here](https://upptime.js.org/docs/configuration)
