#Brands Page Instructions#
Instructions for getting deep linking, and URL changing to work on the Brands page.

**NOTE:**  The URL's used for rewrite rule patterns and the `<base href>` may differ between development and production environments.

##Server-side URL Rewrite Rules##
A server configuration file must exist, and consist of URL rewrite rules in order for deep linking to work.

Some methods include:

* Placing config file in the root of the site
* Configuring rewrite rules through the CMS

###via Web.config###
For IIS environments

```
<configuration>
    <system.webServer>
        <rewrite>
            <rules>
                <rule name="Brands page">
                    <match url="^our-brands/([_0-9A-Za-z-]+)" />
                    <action type="Rewrite" url="/our-brands/index.html?id={R:1}" />
                </rule>
            </rules>
        </rewrite>
    </system.webServer>
</configuration>
```

###via .htaccess###
For Apache environments

```
RewriteEngine on
RewriteRule ^our-brands/([_0-9A-Za-z-]+)$ /our-brands/index.html [L]
```

##&lt;base href&gt; Tag
In order for Angular's `$location` service to direct route paths correctly, A `<base href="/our-brands/">` must be set in the `<head>` of the DOM. It only has to exist on this page

##Data Attributes on &lt;option&gt; Tags
Unless it's the first "All Brands" option in the tabs, a `data-slug` attribute should be set on all `<option>` tags to indicate its path to set in the URL.

```
    <div class="tab-panel-tabs">
        <select ng-change="select(tab)" ng-model="tab">
            <option value="0">All Brands</option>
            <option value="1" data-slug="chocolate">Chocolate</option>
            <option value="2" data-slug="food">Food</option>
        </select>
    </div>
```