# definition of 'ready'

Task will be taken into a sprint if all the points in the list are fulfilled:

1. Task should be named in user story format
2. Task must be I.N.V.E.S.T. that means:
   * INDEPENDENT - it’s not coupled with other task and it does not inherit any dependency from other tasks
   * NEGOTIABLE - task can be discussed and rewritten
   * VALUABLE  - task adds real value to product and stakeholders
   * ESTIMABLE - it must be possible to estimate a task
   * SMALL - task should be small enough to be finished in one sprint
   * TESTABLE - there must be a way to test a task, only then it’s done
3. Task must define ‘Acceptance criteria’ and is done, when they’re met
4. Task must be estimated by development team
5. Task must have name and contact to expert at subject of the task.
6. Task must provide all the files and needed information for developers to use them or reproduce an error

**Comment:**

 * Ad.1 User story format informs about real value added to project and not an technical stuff. We write it in format:

    As <persona>, I want <what?> so that <why?>.
    
    Example:
    
    As an administrative user
    I want to deactivate another user’s account
    So that they can no longer log in or receive email notifications


 * Ad3. Task has acceptance criteria, that means there’s a list of functionalities, non-functional attributes and performace criteria or other cases that it should provide, 

    Example:
          
    If I am an Administrator, I can create User Accounts.
    I can create a User Account by entering the following information about the User: a. Name, b. Email address, c. Phone Number d. License Number (Power/Basic/None), e. Account Status (Active/Inactive), f. Reports to (from a list of “Active” Users)
    I cannot assign a new User to report to an “Inactive” User
    I cannot assign a new User to report to a User if it creates a cyclical relationship 
    I am able to verify with the intended recipient of the email that it was received.

 * Ad.6 Task that require changes of design should have the link to the psd file, but in ticket must be attached the jpg/png file of the design (developers don’t have tools to open psd format).

   Also, when describing a bug, put all steps and circumstances about the bug, attach screenshots and browser report (from: http://supportdetails.com/ for example)
   
   Example:
    
   I log in as a administrator user (user: my@account.com)
   I enter the /stats page using top menu and a Stats Link
   I should see stats for current month, but I actually see stats for previous month
