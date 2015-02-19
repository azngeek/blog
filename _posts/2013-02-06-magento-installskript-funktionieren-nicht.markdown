---
layout: post
status: publish
published: true
title: Magento Installer Script does not run
author:
  display_name: donbosco
  login: donbosco
  email: donbosco.rulz@gmail.com
  url: ''
author_login: donbosco
author_email: donbosco.rulz@gmail.com
wordpress_id: 543
wordpress_url: http://www.azngeek.de/?p=543
date: !binary |-
  MjAxMy0wMi0wNiAxNDo1MzoyMyArMDEwMA==
date_gmt: !binary |-
  MjAxMy0wMi0wNiAxMzo1MzoyMyArMDEwMA==
categories:
- Allgemein
tags:
- magento
- snippets
comments: []
---
<p>I recently run into a problem with the "Magento Extension Installer Script". I did follow the <a href="http:&#47;&#47;alanstorm.com&#47;magento_setup_resources">tutorial<&#47;a> by Alan Storm, nut run into a huge problem.<&#47;p></p>
<h2>The fail!<&#47;h2></p>
<p>I was not able to run the install script! The site seems to be normal, when reloading it. The config.xml contained everything, which i needed. And i double-checked it, so this could not be the reason.<&#47;p></p>
<p>[code]<br />
	<modules><br />
        <Don_Recipes><br />
            <version>0.1.0<&#47;version><br />
        <&#47;Don_Recipes><br />
    <&#47;modules><br />
[&#47;code]</p>
<p>The directory and class names were okay as well.<&#47;p></p>
<p>[code lang="shell"] app:&#47;&#47;Don&#47;Recipes&#47;sql&#47;don_recipes_setup&#47;mysql4-install-0.1.0.php # This really should do it [&#47;code]<&#47;p></p>
<p>As well the code content<&#47;p></p>
<p>[code lang="php"] die('hard'); # yeah, as always [&#47;code]<&#47;p></p>
<h2>The solution<&#47;h2></p>
<p>The reason was:<&#47;p></p>
<ul>
<li>The table magento_core_resource hat an entry with the same version<&#47;li>
<li>I deleted the resource don_recipes<&#47;li>
<li>Reload the page<&#47;li><br />
<&#47;ul></p>
<h2>How to debug it?<&#47;h2><br />
Please do yourself a favor and debug the applications. You can easily set a breakpoint within the class <i>Mage_Core_Model_Resource_Setup<&#47;i>.</p>
<p>[code]<br />
    &#47;**<br />
     * Apply data updates to the system after upgrading.<br />
     *<br />
     * @param string $fromVersion<br />
     * @return Mage_Core_Model_Resource_Setup<br />
     *&#47;<br />
    public function applyDataUpdates()<br />
    {<br />
        $dataVer= $this->_getResource()->getDataVersion($this->_resourceName);<br />
        $configVer = (string)$this->_moduleConfig->version;<br />
        if ($dataVer !== false) {<br />
             $status = version_compare($configVer, $dataVer);<br />
             if ($status == self::VERSION_COMPARE_GREATER) {<br />
                 $this->_upgradeData($dataVer, $configVer);<br />
             }<br />
        } elseif ($configVer) {<br />
            $this->_installData($configVer);<br />
        }<br />
        return $this;<br />
    }<br />
[&#47;code]</p>
