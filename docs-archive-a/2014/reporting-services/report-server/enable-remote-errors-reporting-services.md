---
title: Activer les erreurs distantes (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- remote data source [Reporting Services]
- EnableRemoteError server property
ms.assetid: 5f05022b-d557-43e0-b50a-f5e2a1846b83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d2a7e7e0b38b38bf563dfc2a8cff65c897c5293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611531"
---
# <a name="enable-remote-errors-reporting-services"></a><span data-ttu-id="41151-102">Activer les erreurs distantes (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="41151-102">Enable Remote Errors (Reporting Services)</span></span>
  <span data-ttu-id="41151-103">Vous pouvez définir des propriétés de serveur sur un serveur de rapports [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de façon à retourner des informations supplémentaires concernant les conditions d'erreur qui se produisent sur des serveurs distants.</span><span class="sxs-lookup"><span data-stu-id="41151-103">You can set server properties on a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server to return additional information about error conditions that occur on remote servers.</span></span> <span data-ttu-id="41151-104">Si un message d'erreur contient le texte « Pour obtenir plus d'informations sur cette erreur, accédez au serveur de rapports sur le serveur local ou activez les erreurs distantes », vous pouvez définir la propriété `EnableRemoteErrors` de façon à accéder à des informations supplémentaires qui peuvent vous aider à résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="41151-104">If an error message contains the text "For more information about this error, navigate to the report server on the local server machine, or enable remote errors", you can set the `EnableRemoteErrors` property to access additional information that can help you troubleshoot the problem.</span></span> <span data-ttu-id="41151-105">Pour plus d’informations, consultez [Propriétés système de Report Server](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) dans la documentation en ligne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41151-105">For more information, see [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="41151-106">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="41151-106">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="41151-107">Activer les erreurs distantes pour le mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="41151-107">Enable Remote Errors for SharePoint Mode</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="41151-108">Activer les erreurs distantes au moyen de SQL Server Management Studio (mode natif)</span><span class="sxs-lookup"><span data-stu-id="41151-108">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>](#bkmk_mgtStudio)  
  
-   [<span data-ttu-id="41151-109">Activer les erreurs distantes au moyen d'un script (mode natif)</span><span class="sxs-lookup"><span data-stu-id="41151-109">Enable remote errors through script (Native Mode)</span></span>](#bkmk_script)  
  
-   [<span data-ttu-id="41151-110">Modification de la table ConfigurationInfo (mode natif)</span><span class="sxs-lookup"><span data-stu-id="41151-110">Modifying the ConfigurationInfo table (Native Mode)</span></span>](#bkmk_ConfigurationInfo)  
  
##  <a name="enable-remote-errors-for-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="41151-111">Activer les erreurs distantes pour le mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="41151-111">Enable Remote Errors for SharePoint Mode</span></span>  
 <span data-ttu-id="41151-112">Il existe deux procédures différentes pour activer les erreurs distantes pour le mode SharePoint [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41151-112">There are two different procedures for enabling remote errors for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="41151-113">La procédure est différente pour les deux architectures différentes de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="41151-113">The procedure is different for the two different report server architectures.</span></span> <span data-ttu-id="41151-114">La dernière architecture basée sur un service SharePoint qui a été introduite dans la version [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] utilise un paramètre qui peut être configuré pour chaque application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41151-114">The newer SharePoint service based architecture that was introduced in the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, utilizes a setting that can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="41151-115">L'architecture plus ancienne utilise un paramètre de niveau de site unique.</span><span class="sxs-lookup"><span data-stu-id="41151-115">The older architecture utilizes a single site level setting.</span></span>  
  
#### <a name="enable-remote-errors-for-a-reporting-services-service-application"></a><span data-ttu-id="41151-116">Activer les erreurs distantes pour une application de service Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41151-116">Enable Remote errors for a Reporting Services Service Application</span></span>  
  
1.  <span data-ttu-id="41151-117">Pour un serveur de rapports en mode SharePoint installé avec [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ou une version plus récente de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], activez le paramètre d'application de service **Activer les erreurs distantes**.</span><span class="sxs-lookup"><span data-stu-id="41151-117">For a SharePoint mode report server installed with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] or a newer version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], enable the service application setting **Enable remote errors**.</span></span> <span data-ttu-id="41151-118">Le paramètre peut être configuré pour chaque application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41151-118">The setting can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="41151-119">Dans l'Administration Centrale de SharePoint, sous le groupe **Gestion des applications** , cliquez sur **Gérer les applications de service** .</span><span class="sxs-lookup"><span data-stu-id="41151-119">In SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
3.  <span data-ttu-id="41151-120">Trouvez votre application de service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] puis cliquez sur le nom de votre application de service.</span><span class="sxs-lookup"><span data-stu-id="41151-120">Find your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and click the name of your service application.</span></span>  
  
4.  <span data-ttu-id="41151-121">Cliquez sur **Paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="41151-121">Click **System Settings**.</span></span>  
  
5.  <span data-ttu-id="41151-122">Cliquez sur **Activer les erreurs distantes** dans la section **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="41151-122">Click **Enable Remote Errors** in the **Security** section.</span></span>  
  
6.  <span data-ttu-id="41151-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="41151-123">Click **OK**.</span></span>  
  
#### <a name="enable-remote-errors-for-a-sharepoint-site"></a><span data-ttu-id="41151-124">Activer les erreurs distantes pour un site SharePoint</span><span class="sxs-lookup"><span data-stu-id="41151-124">Enable Remote Errors for a SharePoint Site</span></span>  
  
1.  <span data-ttu-id="41151-125">Pour un serveur de rapports en mode SharePoint installé avec une version de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] avant [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], activez le paramètre de site **Activer les erreurs distantes en mode local**.</span><span class="sxs-lookup"><span data-stu-id="41151-125">For a SharePoint mode report server installed with a version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] prior to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], enable the site setting **Enable remote errors in local mode**.</span></span>  
  
2.  <span data-ttu-id="41151-126">Cliquez sur **Paramètres du site** dans **Actions du site** pour le site vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="41151-126">In **Site Actions** click **Site Settings** for the site you want to modify.</span></span>  
  
3.  <span data-ttu-id="41151-127">Dans le groupe **Reporting Services** , cliquez sur **Paramètres du site Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="41151-127">Click **Reporting Services Site Settings** in the **Reporting Services** group.</span></span>  
  
4.  <span data-ttu-id="41151-128">Cliquez sur **Activer les erreurs distantes en mode local**.</span><span class="sxs-lookup"><span data-stu-id="41151-128">Click **Enable remote errors in local mode**.</span></span>  
  
5.  <span data-ttu-id="41151-129">Cliquez sur **OK**</span><span class="sxs-lookup"><span data-stu-id="41151-129">Click **OK**</span></span>  
  
##  <a name="enable-remote-errors-through-sql-server-management-studio-native-mode"></a><a name="bkmk_mgtStudio"></a> <span data-ttu-id="41151-130">Activer les erreurs distantes au moyen de SQL Server Management Studio (mode natif)</span><span class="sxs-lookup"><span data-stu-id="41151-130">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>  
  
1.  <span data-ttu-id="41151-131">Démarrez Management Studio et connectez-vous à une instance du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="41151-131">Start Management Studio and connect to a report server instance.</span></span> <span data-ttu-id="41151-132">Pour plus d’informations, consultez [Se connecter à un serveur de rapports dans Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) dans la documentation en ligne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41151-132">For more information, see [Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="41151-133">Cliquez avec le bouton droit sur le nœud du serveur de rapports, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="41151-133">Right-click the report server node, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="41151-134">Cliquez sur **Avancé** pour ouvrir la page de propriétés.</span><span class="sxs-lookup"><span data-stu-id="41151-134">Click **Advanced** to open the properties page.</span></span> <span data-ttu-id="41151-135">Pour plus d’informations, consultez [Propriétés du serveur &#40;page Avancé&#41; - Reporting Services](../tools/server-properties-advanced-page-reporting-services.md) dans la documentation en ligne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41151-135">For more information, see [Server Properties &#40;Advanced Page&#41; - Reporting Services](../tools/server-properties-advanced-page-reporting-services.md)in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="41151-136">Dans `EnableRemoteErrors` , sélectionnez `True` .</span><span class="sxs-lookup"><span data-stu-id="41151-136">In `EnableRemoteErrors`, select `True`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="enable-remote-errors-through-script-native-mode"></a><a name="bkmk_script"></a> <span data-ttu-id="41151-137">Activer les erreurs distantes au moyen d'un script (mode natif)</span><span class="sxs-lookup"><span data-stu-id="41151-137">Enable remote errors through script (Native Mode)</span></span>  
  
1.  <span data-ttu-id="41151-138">Créez un fichier texte et copiez-y le script suivant.</span><span class="sxs-lookup"><span data-stu-id="41151-138">Create a text file and copy the following script into the file.</span></span>  
  
    ```  
    Public Sub Main()  
      Dim P As New [Property]()  
      P.Name = "EnableRemoteErrors"  
      P.Value = True  
      Dim Properties(0) As [Property]  
      Properties(0) = P  
      Try  
        rs.SetSystemProperties(Properties)  
        Console.WriteLine("Remote errors enabled.")  
      Catch SE As SoapException  
        Console.WriteLine(SE.Detail.OuterXml)  
      End Try  
    End Sub  
    ```  
  
2.  <span data-ttu-id="41151-139">Enregistrez le fichier sous le nom EnableRemoteErrors.rss.</span><span class="sxs-lookup"><span data-stu-id="41151-139">Save the file as EnableRemoteErrors.rss.</span></span>  
  
3.  <span data-ttu-id="41151-140">Cliquez sur **Démarrer**, pointez sur **Exécuter**, tapez **cmd**et cliquez sur **OK** pour ouvrir une fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="41151-140">Click **Start**, point to **Run**, type **cmd**, and click **OK** to open a command prompt window.</span></span>  
  
4.  <span data-ttu-id="41151-141">Accédez au répertoire qui contient le fichier .rss que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="41151-141">Navigate to the directory that contains the .rss file you just created.</span></span>  
  
5.  <span data-ttu-id="41151-142">Tapez la ligne de commande suivante, en remplaçant *servername* par le nom de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="41151-142">Type the following command line, replacing *servername* with the actual name of your server:</span></span>  
  
    ```  
    rs -i EnableRemoteErrors.rss -s http://servername/ReportServer  
    ```  
  
6.  <span data-ttu-id="41151-143">Pour plus d’informations, consultez [Utilitaire RS.exe &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="41151-143">For more information, see [RS.exe Utility &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md)</span></span>  
  
##  <a name="modifying-the-configurationinfo-table-native-mode"></a><a name="bkmk_ConfigurationInfo"></a> <span data-ttu-id="41151-144">Modification de la table ConfigurationInfo (mode natif)</span><span class="sxs-lookup"><span data-stu-id="41151-144">Modifying the ConfigurationInfo table (Native Mode)</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="41151-145">Vous pouvez modifier la table **ConfigurationInfo** dans la base de données du serveur de rapports pour affecter à la valeur `EnableRemoteErrors` `True` , mais si le serveur de rapports est utilisé activement, vous devez utiliser SQL Server Management Studio ou un script pour modifier les paramètres.</span><span class="sxs-lookup"><span data-stu-id="41151-145">You can edit the **ConfigurationInfo** table in the report server database to set `EnableRemoteErrors` to `True`, but if the report server is actively used, you should use SQL Server Management Studio or script to modify the settings.</span></span> <span data-ttu-id="41151-146">Si vous modifiez le paramètre dans la base de données, vous devez redémarrer le service [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] avant que les modifications entrent en vigueur.</span><span class="sxs-lookup"><span data-stu-id="41151-146">If you modify the setting in the database, you need to restart the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service before the changes take effect.</span></span>  
  
  
