Lab 3.3: Deploying an Application for VPN service.
===================================================

1. In Central Manager click on the **Workspace** icon at the top left corner, select **Applications**.

.. image:: images/lab3-app1.png
   :width: 400 px

2. Click **Add Application**.

.. image:: images/lab3-app2.png
   :width: 400 px

3. In the **Add Application** menu, type in the application name as **vpn_app**, and the click **Start Creating** button. Leave **Application Service** as **Standard**.

.. image:: images/lab3-app3.png
   :width: 400 px

4. In the Virtual Servers menu, click on **Start Creating** button to create a virtual server. 

.. image:: images/lab3-app5.png 
   :width: 400 px

5. In the **Virtual Servers** tab, enter the following settings

**Virtual Server Name:** vpn_vs
**Virtual Port:** 443 

.. image:: images/lab3-app4.png
   :width: 400 px

6. Click on the **Edit** button under **Protocols & Profiles**

.. image:: images/lab3-app6.png
   :width: 400 px

7. In the **Protocols & Profiles** menu, tick the slider button next to **Enable HTTPS (Client-Side TLS)** so it’s enabled. 

.. image:: images/lab3-app7.png 
   :width: 400 px

8. Under **Please choose a trust CA certificate**, click the drop-down arrow and select **DDC_CA cert**.

.. image:: images/lab3-app8.png
   :width: 400 px

9. Under **Client Side TLS**, click the **Add** button. 

.. image:: images/lab3-app9.png
   :width: 400 px

10. In the **Add Client Side TLS** menu, set the name to **client_cert**. Under RSA Certificate click on the drop down menu and select **self_demo.f5.com**. Click **Save**.

.. image:: images/lab3-app10.png
   :width: 400 px

11. Under the **Security Policies** column, click on the **Edit** button

.. image:: images/lab3-app11.png
   :width: 400 px

12. In the **Security Policies** menu, slide the slider button next to **Use an Access Policy** to the right to enable it. Under Access Policy, click on the drop-down box and select the **vpn_policy** created in the previous lab. Click **Save**. 

.. image:: images/lab3-app12.png
   :width: 400 px

13. Back in the Application Services Properties, click on **Review and Deploy** button.

.. image:: images/lab3-app13.png

14. In the **Deploy-to** menu, click on **Start Adding** button to add the BIG-IP Next instance the VPN application will be deployed on. Select **big-ip-next 03** from the list, and click **Add to List**.

.. image:: images/lab3-app14.png
   :width: 400 px

15. In the Instance enter the following IP address in the Virtual Address field: **10.1.10.160**. 

.. image:: images/lab3-app15.png
   :width: 400 px

16. Click on **Configure** button, this will open the configuration for the BIG-IP Next instance.

.. image:: images/lab3-app16.png

17. In the instance, click on the **vpn_policy** link under Per Session Policy column

.. image:: images/lab3-app17.png
   :width: 400 px

18. Clicking on the vpn_policy will open up the DHCP pool you previously defined in the policy. This is where you would define the DHCP address scope. Click on **ip_pool**. We want the range to be between 10.1.20.100 and .110 so under **Start Address** enter **10.1.20.100** and under **End Address** enter **10.1.20.110**. Click **Finish**, and then click **Finish** again on the next screen to close of the ip_pool screen.

.. image:: images/lab3-app18.png
   :width: 400 px

19. In the Deploy To screen review the configuration to make sure it matches the screen shot below, and then click **Deploy Changes**.

.. image:: images/lab3-app19.png
   :width: 400 px

20. In the Deploy Application Service window, click **Yes, Deploy**.

.. image:: images/lab3-app20.png
   :width: 400 px

21. As the application is being deployed to the BIG-IP Next instance you will see this pop up window

.. image:: images/lab3-app21.png
   :width: 400 px

22. Once the application is deployed, the Application Dashboard will be displayed. Observe, the application health is Good and Green.

.. image:: images/lab3-app22.png
   :width: 400 px

You are now completed with portion of the lab. Let's test the policy.