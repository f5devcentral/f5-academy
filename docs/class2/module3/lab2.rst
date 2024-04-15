Lab 3.2 - Creating an Access Policy
=====================================

1. Click on **Policies** under the **Access** menu

.. image:: /images/lab3-policy1.png
    :width: 400 px

2. Click on **Start Creating** button to create a new policy.

.. image:: /images/lab3-policy2.png
    :width: 400 px

1. In the Create Policy menu, select the radio button next to **Per-Session Policy** under Choose Policy Type, select the radio button next to Start from Scratch under How would you like to create it? Click on the Next button at the top right hand corner.

.. image:: /images/lab3-policy3.png
    :width: 400 px

4. This will bring you to the General Properties menu of the policy. Enter **vpn_policy** as the name for the policy. Click the **Continue** button at the bottom right hand corner.

.. image:: /images/lab3-policy4.png
    :width: 400 px

5. In the **Session** menu you can define the different policy session parameters. For this lab we will keep the default settings. Click the **Continue** button. 

.. image:: /images/lab3-policy5.png
    :width: 400 px

6. In the **Logging** menu you can define what level of logging would you like to gather. For this lab we will keep the default settings. Click the **Continue** button.

.. image:: /images/lab3-policy6.png
    :width: 400 px

7. In the **Single Sign-On** menu you can setup Single Sign-On with SAML or OAuth provider. In this lab we will not be configuring this setting. Click the **Continue** button.

.. image:: /images/lab3-policy7.png
    :width: 400 px

8. In the **Endpoint Security** menu, it should already pre-select the preloaded Endpoint Security package. If not, click the drop down arrow and select version 1.0.0-1566.0. 

.. note:: At the time this lab was created March 2024 this is the latest version available. If you’re running your own lab, you may want to download and install the latest version.

.. image:: /images/lab3-policy8.png
    :width: 400 px

9. In the **Resources** menu, click on the **Start Creating** button. Select **Network Access** from the drop down menu.

.. image:: /images/lab3-policy9.png
    :width: 400 px

10.  In the **Network Access** menu under Resource Properties, you can define a name for the Network Address scope. In this lab to keep it for simplicity, keep the default naming, and click the **Continue** button. 

.. image:: /images/lab3-policy10.png
    :width: 400 px

11. In the **Network Settings** menu, you can define specific network settings such as Preserve Source port, split tunnel vs full tunnel, etc.  Scroll down to Client Options and uncheck the Client for Microsoft Networks. The rest of the settings can stay as default settings. Click the **Continue** button. 

.. image:: /images/lab3-policy11.png
    :width: 400 px

12. In the **IP Pools** menu, define a name for DHCP IP lease pool. We will define the IP address scope under the application. 

**Name:** ip_pool

.. image:: /images/lab3-policy12.png
    :width: 400 px

13. In the **DNS Hosts** menu, you can define DNS servers, suffix search order, and other DNS related settings for network and webtop access. In this lab we will keep the default. Click the **Continue** button. 

.. image:: /images/lab3-policy13.png
    :width: 400 px

14. In the **Drive Mappings** menu, you can configure pre-define drive mappings for your Access policy. In this lab we will not create any drive mappings. Click on **Finish**.

.. image:: /images/lab3-policy14.png
    :width: 400 px

15. This should take you back to the main VPN policy creation menu. You should now see the Network Resource you’ve just created listed. Click on **Create** again. This time you will create a webtop resource.

.. image:: /images/lab3-policy15.png
    :width: 400 px

16. In the Webtop resource menu, you can define name for the webtop resource and configure the different settings for the resource. In this lab we will keep the default. Click **Finish**.

.. image:: /images/lab3-policy16.png
    :width: 400 px

17. This should take you back to the VPN policy creation menu. You should see two resources listed; Network resource and Webtop resource. Click **Continue**.

.. image:: /images/lab3-policy17.png
    :width: 400 px

18. In the **Connectivity** menu, this allows you to configure and customize the Edge client, compression, and other remote access settings. We will keep the default settings. Click **Continue**. 

.. image:: /images/lab3-policy18.png
    :width: 400 px

19. In the **Policy Endings** menu, you can define the different policy endings. In this lab, we will keep the default. Click **Finish**.

.. image:: /images/lab3-policy19.png
    :width: 400 px

20. Next screen is the Access Visual Policy Designer (VPD). In the VPD add an Empty flow by clicking and dragging the **Empty flow**from the Flows menu on left hand side to the plus sign. The plus sign should turn blue like the screen shot below.

.. image:: /images/lab3-policy20.png
    :width: 400 px

This is how the end VPD flow should look like. 

.. image:: /images/lab3-policy20b.png
    :width: 400 px

21.   Inside the Empty flow, mouse over the right hand side, three buttons should appear. Click on the **Collapse** button. This will expand the Empty flow object. 

.. image:: /images/lab3-policy21.png
    :width: 400 px

22.   Confirm the Empty flow object is open, see screen shot below. You can tell because the flow name is at the top left hand side. 

.. image:: /images/lab3-policy22.png
    :width: 400 px

23.   Click on the **Rules** button at the left-hand side of the menu. 

.. image:: /images/lab3-policy23.png
    :width: 400 px

This will bring up all the available Rules to add to the Flow in the VPD. 

24. You can either scroll down or use the Search feature to add the **On-Demand Certificate Authentication** rule to the Empty flow.

.. image:: /images/lab3-policy24.png
    :width: 400 px
 

Remember to add the rule, you will want to drop the rule over to the plus sign and make sure the plus sign turns blue. See screen shot below.

.. image:: /images/lab3-policy24b.png
    :width: 400 px


The Empty flow should look like this with the On-Demand Certificate Authentication Rule added. 

.. image:: /images/lab3-policy24c.png
    :width: 400 px

25.  Inside the On-Demand-Certificate-Authentication rule click on the **Edit** button.

.. image:: /images/lab3-policy25.png
    :width: 400 px

26.  In the Rules properties menu, verify **Authentication Mode** is set to **Require**. Click **Continue**.

.. image:: /images/lab3-policy26.png
    :width: 400 px

27.  In the Branches menu, click on **Create** and create a new Branch name **Success**, and set **Expression Context** as **Client Certificate**, **Condition** as **Validity**, and **Client Certificate** as **Valid**. Click **Save.

.. image:: /images/lab3-policy27.png
    :width: 400 px

28.  Verify the Branch Success has been added. Click Finish. 

.. image:: /images/lab3-policy28.png
    :width: 400 px

29.  In the VPD, you will add the Advanced Resource Assign rule to the policy on plus sign next to the Successful branch. Remember you will need to drag the Rule object over the plus sign until it turn blue, then release. The VPD flow should look like the below. 

.. image:: /images/lab3-policy29.png
    :width: 400 px

30.  Click on the Edit button at the top right corner of the Advanced Resource Assignment Rule object.

.. image:: /images/lab3-policy30.png
    :width: 400 px

31.  In the Advanced Resource Assignment rule properties menu, click on Start Adding under the Resource Assignments section

.. image:: /images/lab3-policy31.png
    :width: 400 px

32.  In the Add Resource Assignment, Expression menu set the following expressions. 

First Expression: 
Set **Context** as **Client Capability**, **Condition** as **Client App ID**, **Client App ID** as **Machine Tunnel Client**. 

Second Expression: 
Set **Context** as **Client Capability**, **Condition** as **Client App ID**, **Client App ID** as **Windows Edge Client**.

Click **Continue**. 

.. image:: /images/lab3-policy32.png
    :width: 400 px


33. In the Add **Resources Assignment** menu, select the Network Access profile you created earlier from the drop down menu. Under Webtops, select the Webtop profile you created earlier from the drop down menu. Click the **Continue** button and then click **Finish**.

.. image:: /images/lab3-policy33.png
    :width: 400 px

34. You should be back on the Advanced Resource Assignment object. Verify you have a resource created and defined. Click **Continue**.

.. image:: /images/lab3-policy34.png
    :width: 400 px

35.  In the Branches menu, we will leave it as default. Click **Finish**. 

.. image:: /images/lab3-policy35.png
    :width: 400 px

36.  You should be back in the VPD on the Empty flow again. Your VPD should look like the screen below. If not, please ask lab assistance for help and/or review the steps above. You can tell which object your in by looking at the name on the top left hand corner.

.. image:: /images/lab3-policy36.png
    :width: 400 px

In the Empty flow object, there are three buttons to the top left-hand side. Click on the **Edit** button. It is the middle button. This will open the Flow Endings property menu. 

.. image:: /images/lab3-policy36b.png
    :width: 400 px

37.  In the **Flow Endings** menu, click on **Create**.

.. image:: /images/lab3-policy37.png
    :width: 400 px

38. This will add a second row to the Flow Endings. Type in Allow as the Name and select the color #199D4D. Click **Save**.

.. image:: /images/lab3-policy38.png
    :width: 400 px

39. In the Empty flow object, click on the **Deny** after the Advanced Resource Assignment rule.

.. image:: /images/lab3-policy39.png
    :width: 400 px

40. You should see a drop-down menu with Deny and Allow. Select **Allow**.

.. image:: /images/lab3-policy40.png
    :width: 400 px

41. Click on the **Collapse** button again to close the Empty flow.

.. image:: /images/lab3-policy41.png
    :width: 400 px

42. Now in the VPD you should be back to the main screen of the flow design. See screen shot below. 

.. image:: /images/lab3-policy42.png
    :width: 400 px

43. Click on the **Deny** box after the Allow branch. Select **Allow**.

.. image:: /images/lab3-policy43.png
    :width: 400 px

44.  The VPD should look like this.

.. image:: /images/lab3-policy44.png
    :width: 400 px

45. Click on the Save button at the top right-hand corner. You should get a message at the bottom right hand corner “Policy Saved successfully”. Click **Exit** to close out of the VPD.

.. image:: /images/lab3-policy45.png
    :width: 400 px

46. You should have an Access policy now in Draft status. 

.. image:: /images/lab3-policy46.png
    :width: 400 px

This concludes the policy building portion of this lab.
