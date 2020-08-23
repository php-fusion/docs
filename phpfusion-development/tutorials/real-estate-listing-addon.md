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

## **Lets get started.**

First, we will need a name for our project. I'll have the liberty of naming this project for you, but feel free to customize it to your own name. For now, let's call this application - "property". So let's prepare the files as following for the most basic setup.

```text
/property/
- /admin/index.php
- /admin/listing.php
- view.php
- infusion.php
- infusion_db.php
- index.php
```

> By placing two **blank** `index.php` files in every folder in PHP-Fusion, you will be disabling anyone from viewing your files directly via browser. This is a very important thing that you must remember to do every time you create a folder. Make it a habit!



