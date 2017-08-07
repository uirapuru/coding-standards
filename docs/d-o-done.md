# definition of 'done'

Definition of Done should be globally understood and accepted. 

definition of done - ideal version:

1. task “acceptance criteria” must be met
2. git branch must have proper name 'feature/{ticket-number}-{short-description}'
3. feature design in task must be reviewed and compared with implemented functionality
4. dependencies (composer, npm etc) must be updated to working versions and lock file must be pushed
5. feature must be unit tested
6. feature must be functionally tested, if possible
7. fixtures must be added or updated if there are changes in test data
8. db migrations must be written if there are changes in db schema
9. all tests must be green
10. code must be formatted according to styling rules (manually or automatically)
11. code must have proper annotations
12. functions and methods must have proper type hinting
13. pull request (with full description according to template) to release branch must be created 
14. code review must be accepted by other developer
15. documentation must be updated according to all changes
(information about additional software, fixtures, data, how to install and run them etc.)
16. feature branch must be merged by author into release branch and deleted
17. release branch must be deployed on preprod, db migrations must be run
18. preprod instance must be manually tested by PO
19. release branch must be deployed on prod instance, db migrations must be run
20. done task must be accepted by PO
21. release branch must be merged into develop
22. ticket must be moved to “done”

definition of done - sufficient version:

(under some circumstances - not insufficient time or resources - some point of “ideal DoD” are skipped BUT there must be a time to “harden” feature in future, like a “hardening sprint” etc. These steps ARE CRUCIAL and cannot be skipped)

1. task “acceptance criteria” must be met
2. git branch must have proper name `feature/{ticket-number}-{short-description}`
3. all tests must be green, some tests may be skipped 
4. pull request (with full description according to template) to release branch must be created 
5. code review must be accepted by other developer
6. feature branch must be merged by author into release branch and deleted
7. release branch must be deployed on prod instance, db migrations must be run
8. done task must be accepted by PO
9. ticket must be moved to “done”



