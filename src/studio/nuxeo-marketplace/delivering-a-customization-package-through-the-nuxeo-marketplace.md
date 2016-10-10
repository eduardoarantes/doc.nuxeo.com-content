---
title: Delivering a Customization Package through the Nuxeo Marketplace
review:
    comment: ''
    date: ''
    status: ok
labels:
    - marketplace
toc: true
confluence:
    ajs-parent-page-id: '4687019'
    ajs-parent-page-title: Nuxeo Marketplace
    ajs-space-key: Studio
    ajs-space-name: Nuxeo Online Services
    canonical: Delivering+a+Customization+Package+through+the+Nuxeo+Marketplace
    canonical_source: >-
        https://doc.nuxeo.com/display/Studio/Delivering+a+Customization+Package+through+the+Nuxeo+Marketplace
    page_id: '18450856'
    shortlink: qIkZAQ
    shortlink_source: 'https://doc.nuxeo.com/x/qIkZAQ'
    source_link: >-
        /display/Studio/Delivering+a+Customization+Package+through+the+Nuxeo+Marketplace
history:
    - 
        author: Solen Guitter
        date: '2016-09-01 15:28'
        message: ''
        version: '16'
    - 
        author: Julien Carsique
        date: '2016-02-08 15:11'
        message: ''
        version: '15'
    - 
        author: Solen Guitter
        date: '2015-11-30 10:03'
        message: 'NXDOC-658: Marketplace packages are now called Nuxeo Packages'
        version: '14'
    - 
        author: Julien Carsique
        date: '2015-11-19 14:00'
        message: ''
        version: '13'
    - 
        author: Julien Carsique
        date: '2015-10-21 09:29'
        message: MP version policy
        version: '12'
    - 
        author: Julien Carsique
        date: '2015-09-08 13:42'
        message: Versioning Policy
        version: '11'
    - 
        author: Solen Guitter
        date: '2015-09-07 08:58'
        message: Fix TOC
        version: '10'
    - 
        author: Solen Guitter
        date: '2014-07-16 17:40'
        message: ''
        version: '9'
    - 
        author: Julien Carsique
        date: '2014-02-27 13:21'
        message: ''
        version: '8'
    - 
        author: Solen Guitter
        date: '2014-02-27 10:19'
        message: Added links and fixed typos
        version: '7'
    - 
        author: Alain Escaffre
        date: '2014-02-26 17:56'
        message: ''
        version: '6'
    - 
        author: Julien Carsique
        date: '2014-02-26 17:51'
        message: ''
        version: '5'
    - 
        author: Alain Escaffre
        date: '2014-02-26 11:23'
        message: ''
        version: '4'
    - 
        author: Solen Guitter
        date: '2014-02-25 17:42'
        message: ''
        version: '3'
    - 
        author: Solen Guitter
        date: '2014-02-25 17:35'
        message: ''
        version: '2'
    - 
        author: Solen Guitter
        date: '2014-02-25 17:06'
        message: ''
        version: '1'

---
The Nuxeo Marketplace is the channel provided by Nuxeo to distribute addons and patches to the Nuxeo Platform. The [Admin Center]({{page space='nxdoc' page='admin-tab-overview'}}) and the [Control Panel (nuxeoctl)]({{page space='nxdoc' page='nuxeoctl-and-control-panel-usage'}}) provide an integrated way to browse this catalog of add-ons and install them directly from the Nuxeo Platform interface or the server command line. This catalog of packages is public, although some addons require to be a Nuxeo Connect customer to be able to install them.

The Nuxeo Marketplace also provides a private channel to distribute packages to a specific audience. Nuxeo Connect users can thus provide their own users with the same trustful, integrated way to browse and install private packages, which are available from the Private packages tab of the Update Center.

## Example Use Cases

The purpose of the private channel is to enable Nuxeo Platform users who do some customization on the Platform to easily distribute their customization. Here are some examples of how this private channel can be helpful.

For instance, if you do some customization using Nuxeo Studio and some Java customization using Nuxeo IDE, you can create your Nuxeo Package and let other people (ex: sysadmin) easily install the whole customization through the Admin Center using a single package, instead of installing the Nuxeo Studio customization and the Nuxeo IDE customization. Worth to mention the benefits of using a Nuxeo Package such as target platform validation, various checks, rollback, dependencies or conflicts between packages, ...

As an other example, if you created your own application on top of the Nuxeo Platform and distribute to your own clients (that may do Studio customization themselves), you can use this private channel to provide hot fixes of your base application.

## Who Can Use the Private Marketplace Channel

The Nuxeo Marketplace private channel is available to any Nuxeo Connect user. Nuxeo Connect trial users can also use it.

## Requirements

The Marketplace private channel can be used to provide any type of customization: simple XML configuration, Java code, configuration templates, libraries, etc. The only requirement is that the customization must be provided [as a Nuxeo Package]({{page space='nxdoc' page='creating-nuxeo-packages'}}).

The target instance(s) can get the package from [Nuxeo Connect](http://connect.nuxeo.com/) (via Internet). Otherwise, you can upload the package via the Local packages tab in the Admin Center or from the server command line with [NuxeoCtl]({{page space='nxdoc' page='nuxeoctl-and-control-panel-usage'}}).

## Uploading a Nuxeo Package

### Using the Marketplace Interface

**To provide customers with a private package:**

1.  After logging in, browse to [Nuxeo Marketplace upload page](https://connect.nuxeo.com/nuxeo/site/marketplace/upload) or click on the button **Add a package**.
2.  Fill in the form "Upload a Marketplace package" (see below for details).
3.  Click on the **Submit** button.
    The package is uploaded. It is now available in the **Private packages** tab of the **Update Center** for the instances that match your package's client(s) and project(s).
    ![]({{file name='Admin-Center-private-packages-tab.png'}} ?w=650,border=true)

<div class="table-scroll"><table class="hover"><tbody><tr><th colspan="1">Field</th><th colspan="1">Description</th></tr><tr><td colspan="1">

Package data

</td><td colspan="1">

Select your Nuxeo package. Expected format is ZIP.

See the documentation for [Creating Nuxeo Packages]({{page space='nxdoc' page='creating-nuxeo-packages'}}) and [the Nuxeo Package code samples](https://github.com/nuxeo/nuxeo-marketplace-sample/).

</td></tr><tr><td colspan="1">

Owner client

</td><td colspan="1">

Select the Nuxeo Connect client who will own the package.

{{#> callout type='tip' }}

In most cases, the owner is your company. But typically, system integrators can act in the name of several clients.

Once a given package name is used, the name is reserved to the owner of that initial package.

{{/callout}}</td></tr><tr><td colspan="1">

Associated clients or projects

</td><td colspan="1">

Select the clients and projects for which the package must be available.

{{#> callout type='tip' }}

You can select a client to make the package available for all that client's projects.

{{/callout}}</td></tr></tbody></table></div>

### Using the REST API

A REST API is available for automation (such as integrating the upload of the Nuxeo Package from a release script or from the Continuous Integration).

{{#> panel type='code' heading='Sample calls from command-line with curl'}}

```bash
# Upload a package (owner parameter is required, one of client or project parameter is required)
curl -i -u login:password -F package=@/path/to/MP.zip "https://connect.nuxeo.com/nuxeo/site/marketplace/upload?batch=true&client=CLIENT_ID&project=PROJECT_ID&owner=OWNER_ID"

# Delete a package
curl -i -u login:password -X DELETE "https://connect.nuxeo.com/nuxeo/site/marketplace/delete/PACKAGE_ID"

# List package IDs (not yet available; owner, client or project parameter will be required)
curl -i -u login:password "https://connect.nuxeo.com/nuxeo/site/marketplace/list?batch=true&client=CLIENT_ID&project=PROJECT_ID&owner=OWNER_ID"
```

{{/panel}}

with:

*   `CLIENT_ID` = Comma-separated client IDs.
*   `PROJECT_ID` = Comma-separated project IDs and/or names. The parameter can also include comma-separated client IDs prefixed with "`client:"`.
*   `OWNER_ID` = A unique client ID.

* * *

&nbsp;

<div class="row" data-equalizer data-equalize-on="medium"><div class="column medium-6">{{#> panel heading='More documentation about the Marketplace'}}

*   [Creating Nuxeo Packages]({{page space='nxdoc' page='creating-nuxeo-packages'}})

{{/panel}}</div><div class="column medium-6">

&nbsp;

&nbsp;

</div></div>