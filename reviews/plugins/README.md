# Plugin reviews
Using WordPress comes with an inevitability; using third-party plug-ins. These plug-ins become an integral part of the way a website works and influence overal security and performance. These aspects make it vitally important to review any plug-in that is proposed to be deployed by a developer.

History has taught that even the most popular plug-ins can have security issues (see: [thehackernews.com](http://thehackernews.com/2015/03/wordpress-seo-by-yoast-plugin.html)) and should not be part of any website, that has been put into production, without a proper code review and/or security audit.

## Selection
The search for a plug-in usually starts at the offical [WordPress plugins archive](https://wordpress.org/plugins/). The selection of a plug-in should take into account the following:
- Documentation
<br />The functionality of the plug-in should have been described clearly

- Ratings
<br />The plug-in has to have a sufficient amount of ratings so that the average rating can be considered reliable. The amount of lowest possible ratings (1 and 2) should be minimal.

- Reviews
<br />Users that downloaded the plug-in should have posted positive reviews.
    
- Downloads
<br />The plug-in should have a regular and consistent download frequency.
    
- Support
<br />Does the maintainer of the plug-in offer enough support by replying to questions of users or does the official plug-in site offer a forum or support section? The support section can also be located in an active public Github or Bitbucket repo. If the plug-in hasn't had active support or maintenance in the past year, using it should be carefully weighed against the benefits of the functionality the plug-in offers.

- Open source
<br />A plug-in's code should be reviewable or, when the plug-in has to be purchased, at least be available beforehand.

- Compatibility
<br />The plug-in must be compatible with the latest (stable) version of WordPress and not interfere with any other plug-in(s) that are used. Compatibility issues with other plug-ins might be documented on the plug-in site itself or could be found during installation.

## Review
Once a plug-in has been selected and this plug-in is not listed in the [collection of approved and already deployed plug-ins](/#todo), the plug-in has to be reviewed by the team's lead or the CTO.

### Approval
If a plug-in is approved, it can be deployed and [the list of approved and already deployed plug-ins](/#todo) has to be updated by the approver.

### Disapproval
If it so happens that a proposed plug-in is disapproved, there are two possibilities:
- Either the approver deems the quality of the code of the plug-in in such a bad state, that the use is rejected. Rejection of a plugin has to be listed and documented in [the rejected plug-ins list](/#todo).
- The approver sees room for improval and the plug-in can still be used after adaptation of the code. Adaptation of the code can be proposed as a pull request if the plug-in has an active public repo on Github or Bitbucket or the plug-in can be altered by the approver or an appropriate team member. If the plug-in is altered and ownership is transfered to the development team, changes made to the plug-in shall be recorded in the plug-in's documentation.
