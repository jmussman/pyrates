![Pyrates](.common/joels-private-stock-pyrates.png?raw=true)

# Pyrates

## Introduction

This is a project in identity management and application development
with Okta that demonstrates both configuring the Okta organization and
the development side of integrating and OpenID Connect application.
The linked sections follow the introduction:

### Administration

* [Multiple site branding with custom domains in a single Okta organization](#multiple-site-branding-with-custom-domains-in-a-single-Okt-organization)
* [Salesforce integration and provisioning](#salesforce-integration-and-provisioning)
* [Manual SAML configuration between two Okta organizations](#manual-saml-configuration-between-two-okta-organizations)

### Development

* [OIDC application integrations for three live applications](#oidc-application-integrations-for-three-live-applications)
* [OAuth API security](#oauth-api-security)

Even if you are not that familiar with Okta, SSO, application integrations, or provisioning
I will take you through the basics here!
If you are experienced you can dig into these organizations as a template.
If you are interested in the development side, you can set up your own copies of the
applications locally from the repo here and drive the identity off of the two
existing Okta organizations.
Or make your own for the experience!


### Project Overview

The Pyrates project consists of two Okta organizations and three applications:

* Pyrates - the pirate portal and Okta org
* Port Royal - the portal for the city of Port Royal and Okta org, linked to Pyrates
* The Black Dogg - a tavern that uses Port Royal for identities

The cool thing is anybody can enter the organizations and review the entire configuration:

| custom domain | okta domain | username | password |
| ------------- | ----------- | -------- | -------- |
| https://pid.pyrates.live | https://dev-86618250.okta.com | jackrackham@pyrates.live | P!rates17 |
| https://pid.portroyal.live | https://dev-43633848.okta.com | henrymorgan@portroyal.live | PortR0yal17 |
| https://pid.theblackdogg.live | https://dev-43633848.okta.com | "" | "" |

The applications are all live and running, click the link and then the login button to sign on!

| application domain | username | password |
| ------------- | -------- | -------- |
| https://pyrates.live | annebonny@pyrates.live | P!rates17 (all pirates password)|
| https://portroyal.live | thomasbarret@portroyal.live | PortR0yal17 (all citizens password) |
| https://theblackdogg.live | janecostley@theblackdogg.live | PortR0yal17 |

You can sign on at Port Royal or The Black Dogg with any pirate login!

## Multiple site branding with custom domains in a single Okta Organization

Once in a while I run into an organization that has multiple applications facing different groups
of users, but all of the identity is in a single organization.
Okta has always supported multiple-branding, it just had to be turned on by support.
Since it is really the same thing for each brand, I tackled two here to show it in action!

Click here to [learn more about branding](./Branding.md)

## Salesforce integration and provisioning

Salesforce Dot Com (SFDC) integration is addressed in some of the Okta classes, and it
is just as easy to do with your own developer tenant to play around with SSO and provisioning.
If you took a class, the only differences are none of the pre-provisioned users are there,
you have to remember is the free tenant is a "production" tenant, and SFDC user names have
to be unique across ALL Salesforce tenants (even other companies) so make up something that
will not conflict!

Click here to [learn more about SFDC integrations](./SFDCIntegrations.md)

## Manual SAML Configuration between to Okta Organizations

There are two ways to set up a SAML integration between two Okta organizations: the pre-defined
integration in the Okta Integration Network and doing it manually.
The OIN integration does the heavy lifting for you.
This project goes through a manual integration, which requires more configuration and
exposes a few things the the pre-defined integration does not offer.

Click here to [learn more about SAML configurations](./SAMLConfigurations.md)

## OIDC application integrations for three live applications

This is the development side of the three custom domains configured up above.
They are all straightforward OpenID Connect (OIDC) integrations and they are all almost identical.
We will focus on the Pyrates application to start and then look at the other two for some of
the additions to the security configurations.

Click here to [learn more about OIDC integrations](./OIDCIntegrations.md)

## OAuth API security

In a layered architecture separating the user interface from the business rules (logic) has
a number of advantages: multiple interfaces can share the same rules without repeating them
(the don't repeat yourself or DRY principle), and the separation of concerns supports SOLID
software design principles.

To share the business rules they need to be put somewhere the UIs can reach them, which
goes by the names "web service", "API" (for application programming interface),
and "resource server" in the Open Authentication documentation.

While OIDE is focused on informing an application about a user identity,
Open Authentication (OAuth) is focused on assuring an API that the application is
allowed to make a call, and what the application is allowed to do!

Click here to [learn more about OAuth API security](./OAuthSecurity.md)

# License

The code is licensed under the MIT license. You may use and modify all or part of it as you choose, as long as attribution to the source is provided per the license. See the details in the [license file](./LICENSE.md) or at the [Open Source Initiative](https://opensource.org/licenses/MIT)

<hr>
Copyright © 2020 Joel Mussman. All rights reserved.

## Support

Since I give stuff away for free, and if you would like to keep seeing more stuff like this, then please consider
a contribution to *Joel's Coffee Fund* at **Smallrock** to help keep the good stuff coming :)<br />

[![Donate](.common/Donate-Paypal.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=XPUGVGZZ8RUAA)