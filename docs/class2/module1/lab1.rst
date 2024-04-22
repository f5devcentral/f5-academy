Lab 1.1: Create DNS Resolver
=============================

Configuring a L3 DNS Resolver
-----------------------------

1. Access **BIG-IP Next Central Manager** if you're not already logged in.

.. image:: images/lab2-cmlogin.png
    :width: 400 px

2. Click on the Workspace icon and select Infrastructure

.. image:: images/lab2-infrastructure.png
    :width: 400 px

3. In the My Instances dashboard, click on *big-ip-next-03.example.com* instance.

.. image:: images/lab2-myinstances.png
    :width: 400 px

4. This will open the Instance Settings screen. On the left side, click on **Networking & Proxy**. Click on **Routes** tab from the menu across the top. 

.. image:: images/lab2-routes.png
    :width: 400 px

5. Click on **Start Adding Routes**

.. image:: images/lab2-addroute.png
    :width: 400 px

6. We will bring up the **DNS Net Resolver** configuration menu where we will define a name and the nameserver for the resolution.

- **Name:** global_f5_internal_net_resolver 
- **Route Type:** DNS Net Resolver
- **DNS Net Resolver:** global_f5_internal_net_resolver
 
.. image:: images/lab2-newroute.png
    :width: 400 px

7. In the same screen, scroll down to **Forward Zone**, and click **Create**. Enter the following parameters.

- **Forward zone:** .  This is a period or single dot
- **Nameserver:** 10.1.1.6:53

.. image:: images/lab2-dnscache.png
    :width: 400 px

8. Scroll down to see the additional settings, and set the following parameters.

**Name:** global_f5_internal_net_resolver
**Select:** Use IPv4, Use TCP, Use UDP

.. image:: images/lab2-new1.png
    :width: 400 px

9. Click **Save**, and then click **Cancel & Exit** to exit out of the Instance Setting screen.

This ends this section of the lab, onto the next. 
