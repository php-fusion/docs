---
description: >-
  In this tutorial, we will be making a custom inventory database for real
  estate listing that you can install into PHP-Fusion 9.
---

# Real Estate Listing Addon

**Time to complete tutorial** - Less than 1 hour.

### **In this tutorial, we will be discovering** 

  
****1. The basic of form handling in version 9  
2. The basic of SQL query in version 9  
3. Using PHP-Fusion utility functions such as theme and infusion components to assist you with development of this web application.   
4. Basic concepts of MVCT.   
5. The basics of locale in version 9  
6. The basic SDK to follow to make your work into a custom infusion application package.  
7. Coding it clean with proper coding standard

## **Lets get started.**

First, we will need a name for our project. I'll have the liberty of naming this project for you, but feel free to customize it to your own name. For now, let's call this application - "property". So let's prepare the files as following for the most basic setup.

```text
/property/
- /admin/
----- index.php
----- listing.php
- /locale/
----- index.php
----- English.php
- /templates/
----- index.php
----- public.php
- view.php
- infusion.php
- infusion_db.php
- index.php
```

{% hint style="danger" %}
By placing `index.php` files in every folder, you will be disabling anyone from viewing your files directly via the browser. This is a very important thing that you must remember to do every time you create a folder. Please make it a habit!
{% endhint %}

### Database Structure

Since the property listing will need to be stored somewhere, we will be using the primary MYSQL database as a medium for information data storage. Let's decide our table name and structure as following:

{% tabs %}
{% tab title="Table Structure" %}
**Name**: property

| Table Name | Type / Length | Remarks |
| :--- | :--- | :--- |
| property\_id | BIGINT\(20\) | AUTO INCREMENT |
| property\_name | VARCHAR\(100\) | NOT NULL |
| property\_description | TEXT | NOT NULL |
| property\_image | VARCHAR\(200\) | NOT NULL |
| property\_thumb | VARCHAR\(200\) | NOT NULL |
| property\_datestamp | INT\(10\) | UNSIGNED NOT NULL |
| property\_status | TINYINT\(1\) | UNSIGNED NOT NULL |
| property\_access | SMALLINT\(10\) | NOT NULL |
{% endtab %}

{% tab title="Infusion API" %}

{% endtab %}

{% tab title="SQL " %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
You can click on the tab for the corresponding formats that can be used to build the table. I will not explain the SDK in general. Please read the [Infusion SDK](../infusion-sdk.md) for more information on the API.
{% endhint %}

### Administrative View

**Filename: /admin/listing.php**

```text

```

### Guest and Member View

