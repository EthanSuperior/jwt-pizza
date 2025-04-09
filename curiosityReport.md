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
