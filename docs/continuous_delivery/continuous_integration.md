# Continuous Integration

When your organization practices CI, your developers integrate all their work into the main version of the code base (known as [trunk](https://cloud.google.com/architecture/devops/devops-tech-trunk-based-development), main, or mainline) on a regular basis.

> Trunk-based development is a required practice for continuous integration. Continuous integration (CI) is the combination of practicing trunk-based development and maintaining a suite of fast automated tests that run after each commit to trunk to make sure the system is always working.

## Working in Small Batches

Practicing trunk-based development requires in turn that developers understand how to break their work up into small batches.

To achieve higher levels of software delivery and operational performance, follow these practices:

- Have three or fewer active branches in the application's code repository.
- Merge branches to trunk at least once a day.
- Don't have code freezes and don't have integration phases.

The key is to start development at the service or API layer, not at the UI layer. In this way, you can make additions to the API that won't initially be available to users of the app, and check those changes into trunk. You can launch these changes to production without making them visible to users. This approach, called dark launching, allows developers to check in code for small batches that have been completed, but for features that are not yet fully complete. You can then run automated tests against these changes to prove that they behave in the expected way. This way, teams are still working quickly and developing off of trunk and not long-lived feature branches.

