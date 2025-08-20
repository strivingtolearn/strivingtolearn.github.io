---
title: Code Block Highlighting
description: How different languages look with this theme
tags: [markdown, theming]
---

The headings below show what I used for the `<syntax>` in each code block example.
````
```<syntax>
code example...
```
````

### sh
```sh
#!/usr/bin/env bash
# written by j.c@onclusive.com

set -ETeou pipefail
var="Something"
echo "$var"
```

### epp
```epp
<% |
    String[1] $name,
    Optional[Array[Hash[String[1],String[1]]]] $templates = undef,
    Array[Hash[String[1], Optional[String[1]], 1, 4]] $rules,
   | -%>
# THIS FILE IS MANAGED BY PUPPET. DO NOT EDIT BY HAND!
<% if $templates {
      $templates.each |$value| { -%>

<%      if $value['template_name'] =~ String[1] { -%>
$template <%= $value['template_name'] %>, "<%= $value['template_value'] %>"
<%      }
```

### erb
```erb
<% @config_variables.sort.each do |key, value| -%>
  <%- unless value.nil? -%>
<%= key %> = <%= value %>
  <%- end -%>
<% end -%>
<% if @config_cluster == 'classic' -%>
  <%- @cluster_variables.sort.each do |ckey, cvalue| -%>
    <%- unless cvalue.nil? -%>
<%= ckey %> = <%= cvalue %>
    <%- end -%>
```

### html
```html
<!-- `site.alt_lang` can specify a language different from the UI -->
<html lang="en" >
  <head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  <meta name="theme-color" media="(prefers-color-scheme: light)" content="#f7f7f7">
  <meta name="theme-color" media="(prefers-color-scheme: dark)" content="#1b1b1e">
  <meta name="mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <meta
    name="viewport"
    content="width=device-width, user-scalable=no initial-scale=1, shrink-to-fit=no, viewport-fit=cover"
```

### json
```json
{
  "bind_addr": "10.15.3.78",
  "data_dir": "/var/lib/consul",
  "recursors": [
    "8.8.8.8"
  ],
  "retry_join": [
    "10.15.2.3",
    "10.15.2.4",
    "10.15.2.5",
    "10.15.2.6",
    "10.15.2.7"
  ],
  "ui": false
}
```

### diff
```diff
diff --git a/helper-scripts/ipa-functions.sh.asc b/helper-scripts/ipa-functions.sh.asc
index 9b4e457..9e94cd4 100644
--- a/helper-scripts/ipa-functions.sh.asc
+++ b/helper-scripts/ipa-functions.sh.asc
@@ -6 +6 @@ function apply_ipa_master_manifest() {
-  local pp
+  local pp ret
@@ -27 +27,8 @@ function apply_ipa_master_manifest() {
-  puppet apply --verbose --modulepath "$modulepath" "${HOME}/ipa.pp"
+  ret=0
+  puppet apply --verbose --modulepath --detailed-exitcodes \
+    "$modulepath" "${HOME}/ipa.pp" || ret=$?
+  if [ "${ret:?}" == "0" ] || [ "${ret:?}" == "2" ]; then
+    : # 2 is also a successful exit code
+  else
+    elog "Puppet apply failed"
+  fi
@@ -32 +39 @@ function apply_ipa_replica_manifest() {
-  local pp
+  local pp ret
```

### make
```make
NAME = dracut-resizefs
TARBALL_NAME = $(NAME)

# Find all additional non-URL sources
EXTRA = $(shell HOME=$(RPM_DIR) spectool -l $(SPECFILE) | cut -d' ' -f2- | \
            sed -r -e '/^(ftp|http)(s)?:/d' -e '/^$(TARBALL)$$/d')
EXTRA_SOURCES = $(addprefix $(SRC_DIR)/, $(EXTRA))
```

### puppet
```puppet
class role::rsyslog(
  String[1] $remote_url,
  String[1] $def_template,
  Hash $templates,
  # Normally allowing a default in a role param is very bad form, but for this
  # module, the _vast_ majority of roles will never use this.
  Hash[String[1],Array[String[1]]] $rules = {},
) {

  # Name alone is non-unique in AWS so we also need the instance ID
  $elkname_tmp = $facts['tags']['Name']
  if $::biosversion =~ /(?i:amazon)/ or $::biosvendor =~ /(?i:amazon)/ {
    $elkname = "${elkname_tmp}-${facts['ec2_metadata']['instance-id']}"
  } else {
    $elkname = $elkname_tmp
  }
```

### ruby
```ruby
require 'spec_helper'

describe 'role::pxe' do
  # Load dependent modules
  let(:pre_condition) { ['include rsyslog'] }

  on_supported_os.each do |os, os_facts|
    context "on #{os}" do
      let(:facts) { os_facts }
```

### xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<schemalist gettext-domain="gsettings-desktop-schemas">
  <schema id="org.gnome.desktop.thumbnail-cache" path="/org/gnome/desktop/thumbnail-cache/">
    <key name="maximum-age" type="i">
      <default>180</default>
      <description>Maximum age for thumbnails in the cache, in days. Set to -1 to disable cleaning.</description>
    </key>
    <key name="maximum-size" type="i">
      <default>512</default>
      <description>Maximum size of the thumbnail cache, in megabytes. Set to -1 to disable cleaning.</description>
    </key>
  </schema>
</schemalist>

```

### yaml
```yaml
#######################
######### base ########
#######################

role::base_repos::repos:
  centos_base:
    name: base
    url: https://vault.centos.org/centos/6.10/os/x86_64
    key: file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-6
    enabled: 1
  centos_updates:
```
