# Azure

_c.f._

 * [AWS](./aws_device_farm.md)
 * [Serverless](./serverless.md)

Azure in [Plain English](https://www.expeditedssl.com/azure-in-plain-english)

 * Microsoft provided on-line [training](https://azure.microsoft.com/en-us/learn/skills/)
 * [Interactive Azure Platform Big Picture](http://azureplatform.azurewebsites.net/en-us/)
 * https://blogs.msdn.microsoft.com/azurecat/
 * https://docs.microsoft.com/en-us/azure/guidance/#checklists
 * https://docs.microsoft.com/en-us/azure/guidance/#best-practices-articles
 * MS Azure [Storage Explorer](http://storageexplorer.com/)
 * [Secrets & WebSite Hidden Gems](https://www.hanselman.com/blog/AzureAppServiceSecretsAndWebSiteHiddenGems.aspx)

# Overview

My notes on Azure, with particular reference to ARM and networking.
Based on conversation with Russell Seymore (ASOS, now Chef) & Satheesh ThrikovilChandrasekharan (Microsoft).

 * [Azure Subscription and Service Limits, Quotas, and Constraints](https://azure.microsoft.com/en-gb/documentation/articles/azure-subscription-service-limits/)
 * Comparison between the v1 and v2 resources in Azure [Azure Compute, Network & Storage Providers under the Azure Resource Manager](https://azure.microsoft.com/en-gb/documentation/articles/virtual-machines-azurerm-versus-azuresm/)

# Azure Resource Manager / ARM

 * [Azure Resource Manager Overview](https://azure.microsoft.com/en-gb/documentation/articles/resource-group-overview/)
 * [Using Azure PowerShell with Azure Resource Manager](https://azure.microsoft.com/en-gb/documentation/articles/powershell-azure-resource-manager/)
 * [How to automate with Azure Resource Manager](https://azure.microsoft.com/en-gb/documentation/articles/virtual-machines-how-to-automate-azure-resource-manager/)
 * The functions that can be used inside an ARM template.
   * [Azure Resource Manager Template Functions](https://azure.microsoft.com/en-us/documentation/articles/resource-group-template-functions/)
 * Very useful set of starter templates
    * [Azure ARM quickstart templates](https://github.com/Azure/azure-quickstart-templates)

# Using C#

 * Azure [Management Library](https://azure.microsoft.com/en-us/blog/manage-app-service-sql-database-application-gateway-and-more-using-simpler-azure-management-libraries-for-net/)

# Azure CLI meets Linux

 * [Install and run the Azure CLI on the Windows Subsystem for Linux (WSFL)](https://blogs.technet.microsoft.com/uktechnet/2017/01/16/install-and-run-the-azure-cli-on-the-windows-subsystem-for-linux-wsfl/?WT.mc_id=AID533151_EML_4830736_111145)

# Azure Networking
 
 * MS Azure BiteSize Networking presentation [AzureBiteSizeNetworkingPublic.pptx]({{ site.url }}/assets/AzureBiteSizeNetworkingPublic.pptx)

 * [Virtual Network Overview](https://msdn.microsoft.com/en-us/library/azure/jj156007.aspx)
 * [Virtual Network FAQ](https://msdn.microsoft.com/en-us/library/azure/dn133803.aspx) Has some key info on subnets.
 * [What is a Network Security Group (NSG)](https://azure.microsoft.com/en-gb/documentation/articles/virtual-networks-nsg/)?
 * [Network Resource Provider](https://azure.microsoft.com/en-us/documentation/articles/resource-groups-networking/)
 * [Load Balancer Overview](https://azure.microsoft.com/en-gb/documentation/articles/load-balancer-overview/)
 * [Load Balancing for Azure Infrastructure Services](https://azure.microsoft.com/en-gb/documentation/articles/virtual-machines-load-balance/)
   * [Internet Facing load balancer between multiple Virtual Machines or services]()https://azure.microsoft.com/en-gb/documentation/articles/load-balancer-internet-overview/
   * [Internal Load balancer Overview](https://azure.microsoft.com/en-gb/documentation/articles/load-balancer-internal-overview/)

# 3rd Party
 * Citrix Netscaler on Azure
    * [Deploying Citrix NetScaler VPX on Microsoft Azure](http://support.citrix.com/proddocs/topic/netscaler-vpx-10-5/nsvpx-azure.html)

# Training Courses

## Microsoft Acadamy

 * [Establish Microsoft Azure IaaS Technical Fundamentals](https://www.microsoftvirtualacademy.com/en-US/training-courses/establish-microsoft-azure-iaas-technical-fundamentals-8471)
    * [pptx](https://db3b-powerpoint.officeapps.live.com/p/PowerPointFrame.aspx?PowerPointView=SlideShowView&ui=en%2DUS&rs=en%2DUS&WOPISrc=http%3A%2F%2Fdb3b%2D15%2Dview%2Dwopi%2Ewopi%2Elive%2Enet%3A808%2Foh%2Fwopi%2Ffiles%2F%40%2FwFileId%3FwFileId%3Dhttps%253A%252F%252Fcp%252Dmlxprod%252Dstatic%252Emicrosoft%252Ecom%253A443%252F05567%252D1000%252Fen%252Dus%252Fcontent%252Fcontent%255Feo9b2nxz%255F1504984382%252F04282015093634%252Epptx&access_token_ttl=0&wdModeSwitchTime=1436818209795)

# eBooks

 * [Microsoft Azure Essentials: Azure Automation](http://www.microsoftvirtualacademy.com/ebooks)