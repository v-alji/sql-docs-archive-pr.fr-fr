---
title: Planifier l’actualisation des données et les sources de données qui ne prennent pas en charge l’authentification Windows (PowerPivot pour SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8d875bc-7823-46b7-a939-867cefd4de12
author: minewiskan
ms.author: owend
ms.openlocfilehash: 63e37dec6f334395c0c1812c6f76d750c16c53ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605769"
---
# <a name="schedule-data-refresh-and-data-sources-that-do-not-support-windows-authentication-powerpivot-for-sharepoint"></a><span data-ttu-id="9ff93-102">Actualisation planifiée des données et sources de données qui ne prennent pas en charge l'authentification Windows (PowerPivot pour SharePoint)</span><span class="sxs-lookup"><span data-stu-id="9ff93-102">Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="9ff93-103">Cette rubrique décrit un flux de travail d’actualisation planifiée des données PowerPivot pour SharePoint qui peut utiliser des sources de données qui **NE PRENNENT PAS EN CHARGE** l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="9ff93-103">This topic describes a workflow of PowerPivot for SharePoint schedule data fresh that can use data sources that do **NOT** support Windows Authentication.</span></span> <span data-ttu-id="9ff93-104">Par exemple, des sources de données Oracle ou IDM DB2.</span><span class="sxs-lookup"><span data-stu-id="9ff93-104">For example Oracle or IDM DB2 data sources.</span></span> <span data-ttu-id="9ff93-105">Les illustrations et les étapes figurant dans cette rubrique font référence à des sources de données Oracle, mais le même flux de travail s'applique aux autres sources de données.</span><span class="sxs-lookup"><span data-stu-id="9ff93-105">The illustrations and steps in this topic reference Oracle data sources but the same workflow applies to other data sources.</span></span>  
  
||  
|-|  
|<span data-ttu-id="9ff93-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010 &#124; SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="9ff93-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010 &#124; SharePoint 2013.</span></span>|  
  
 <span data-ttu-id="9ff93-107">**Présentation :** créer deux applications cibles Banque d'informations sécurisées.</span><span class="sxs-lookup"><span data-stu-id="9ff93-107">**Overview:** Create two Secure Store Target Applications.</span></span> <span data-ttu-id="9ff93-108">Configurez la première application cible (PowerPivotDataRefresh) en vue d'utiliser les informations d'identification Windows.</span><span class="sxs-lookup"><span data-stu-id="9ff93-108">Configure the first target application (PowerPivotDataRefresh) to use Windows credentials.</span></span> <span data-ttu-id="9ff93-109">Configurez la deuxième application cible avec les informations d'identification d'une source de données qui ne prend pas en charge l'authentification Windows, une base de données Oracle par exemple.</span><span class="sxs-lookup"><span data-stu-id="9ff93-109">Configure the second target application with the credentials for a data source that does not support windows authentication, for example, an Oracle database.</span></span> <span data-ttu-id="9ff93-110">La deuxième application cible utilise également la première application cible pour le compte d'actualisation des données sans assistance.</span><span class="sxs-lookup"><span data-stu-id="9ff93-110">The second target application also uses the first target application for the unattended data refresh account.</span></span>  
  
 <span data-ttu-id="9ff93-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span><span class="sxs-lookup"><span data-stu-id="9ff93-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span></span>  
  
-   <span data-ttu-id="9ff93-112">**(1) PowerPivotDatarefresh :** ID d’application cible de la Banque d’informations sécurisées qui est défini avec l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="9ff93-112">**(1) PowerPivotDatarefresh:** A Secure Store Target Application ID that is set with windows authentication.</span></span>  
  
-   <span data-ttu-id="9ff93-113">**(2) OracleAuthentication :** ID d’application cible de la Banque d’informations sécurisées qui est défini avec les informations d’identification Oracle.</span><span class="sxs-lookup"><span data-stu-id="9ff93-113">**(2) OracleAuthentication:** A Secure Store Target Application ID that is set with Oracle credentials.</span></span>  
  
-   <span data-ttu-id="9ff93-114">**(3)** l’application de service PowerPivot est configurée pour utiliser l’application cible « PowerPivotDataRefresh » pour le **compte d’actualisation des données sans assistance**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-114">**(3)** The PowerPivot Service application is configure to use the target application "PowerPivotDataRefresh" for the **Unattended Data Refresh Account**.</span></span>  
  
-   <span data-ttu-id="9ff93-115">**(4)** Le classeur PowerPivot utilise des données Oracle.</span><span class="sxs-lookup"><span data-stu-id="9ff93-115">**(4)** PowerePivot Workbook uses Oracle data.</span></span> <span data-ttu-id="9ff93-116">Les paramètres d’actualisation du classeur spécifient que la connexion de source de données utilise l’application cible **(2)** pour les informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="9ff93-116">The workbook refresh settings specify the data source connection to use the target application **(2)** for credentials.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9ff93-117">Prérequis</span><span class="sxs-lookup"><span data-stu-id="9ff93-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="9ff93-118">Présence d'une application de service PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9ff93-118">A PowerPivot Service Application exists.</span></span>  
  
-   <span data-ttu-id="9ff93-119">Présence d'une application du service Banque d'informations sécurisées.</span><span class="sxs-lookup"><span data-stu-id="9ff93-119">A Secure Store Service Application exists.</span></span>  
  
-   <span data-ttu-id="9ff93-120">Présence d'un classeur Excel avec un modèle de données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9ff93-120">An Excel workbook with a PowerPivot data model exists.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-windows-authentication"></a><span data-ttu-id="9ff93-121">Pour créer un ID d'application cible qui utilise l'authentification Windows</span><span class="sxs-lookup"><span data-stu-id="9ff93-121">To Create a Target Application ID that uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="9ff93-122">Dans l’administration centrale de SharePoint, cliquez sur **gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-122">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="9ff93-123">Cliquez sur le nom de votre application de service Banque d'informations sécurisées.</span><span class="sxs-lookup"><span data-stu-id="9ff93-123">Click the name of your secure store service application.</span></span>  
  
3.  <span data-ttu-id="9ff93-124">Sur la page **Gérer** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-124">On the **Manage** page, click **New**.</span></span> <span data-ttu-id="9ff93-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span><span class="sxs-lookup"><span data-stu-id="9ff93-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span></span>  
  
4.  <span data-ttu-id="9ff93-126">Sur la page **Créer une nouvelle application cible du magasin sécurisé** , configurez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ff93-126">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="9ff93-127">**ID de l'application cible :** PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="9ff93-127">**Target Application ID:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="9ff93-128">**Nom complet :** PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="9ff93-128">**Display Name:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="9ff93-129">**Adresse de messagerie du contact :** ?</span><span class="sxs-lookup"><span data-stu-id="9ff93-129">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="9ff93-130">**Type d'application cible :** Groupe.</span><span class="sxs-lookup"><span data-stu-id="9ff93-130">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="9ff93-131">**URL de la page de l'application cible :** aucune.</span><span class="sxs-lookup"><span data-stu-id="9ff93-131">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="9ff93-132">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="9ff93-133">Sur la page Informations d'identification, ne changez pas les deux noms de champ par défaut, ainsi que les types de champ pour **Nom d'utilisateur Windows** et **Mot de passe Windows**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-133">On the Credentials page, leave the two default field names and field types for **Windows User Name** and **Windows Password**.</span></span>  
  
7.  <span data-ttu-id="9ff93-134">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-134">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="9ff93-135">Sur la page **Paramètres d'appartenance** , ajoutez au moins un **administrateur d'application cible** , puis ajoutez des membres qui ont besoin d'accéder à l'application cible.</span><span class="sxs-lookup"><span data-stu-id="9ff93-135">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="9ff93-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-136">Click **OK**.</span></span>  
  
10. <span data-ttu-id="9ff93-137">Le nouvel ID d'application cible est ajouté à la liste.</span><span class="sxs-lookup"><span data-stu-id="9ff93-137">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="9ff93-138">Sélectionnez l’ID de l’application cible, puis cliquez sur **définir les informations d’identification**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span><span class="sxs-lookup"><span data-stu-id="9ff93-138">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="9ff93-139">Tapez le Nom d'utilisateur Windows et le Mot de passe Windows, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-139">Type the Windows User Name and Windows Password and then click **OK**.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-oracle-credentials"></a><span data-ttu-id="9ff93-140">Pour créer un ID d'application cible qui utilise les informations d'identification Oracle</span><span class="sxs-lookup"><span data-stu-id="9ff93-140">To Create a Target Application ID that uses Oracle credentials</span></span>  
  
1.  <span data-ttu-id="9ff93-141">Dans l’administration centrale de SharePoint, cliquez sur **gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-141">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="9ff93-142">Cliquez sur le nom de votre application de service Banque d'informations sécurisées.</span><span class="sxs-lookup"><span data-stu-id="9ff93-142">Click the name of your Secure Store Service application.</span></span>  
  
3.  <span data-ttu-id="9ff93-143">Dans la page **gérer** , cliquez sur **nouveau**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span><span class="sxs-lookup"><span data-stu-id="9ff93-143">On the **Manage** page, click **New**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span></span>  
  
4.  <span data-ttu-id="9ff93-144">Sur la page **Créer une nouvelle application cible du magasin sécurisé** , configurez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ff93-144">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="9ff93-145">**ID de l'application cible :** OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="9ff93-145">**Target Application ID:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="9ff93-146">**Nom complet :** OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="9ff93-146">**Display Name:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="9ff93-147">**Adresse de messagerie du contact :** ?</span><span class="sxs-lookup"><span data-stu-id="9ff93-147">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="9ff93-148">**Type d'application cible :** Groupe.</span><span class="sxs-lookup"><span data-stu-id="9ff93-148">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="9ff93-149">**URL de la page de l'application cible :** aucune.</span><span class="sxs-lookup"><span data-stu-id="9ff93-149">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="9ff93-150">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-150">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="9ff93-151">Dans la page **informations d’identification** , remplacez le nom du premier champ par `Oracle User ID` , puis remplacez le **type de champ** par `User Name` .</span><span class="sxs-lookup"><span data-stu-id="9ff93-151">On the **Credentials** page, change the first field name to `Oracle User ID` and change the **Field Type** to `User Name`.</span></span>  
  
     <span data-ttu-id="9ff93-152">Remplacez le deuxième nom de champ par `Oracle Password` et le **type de champ** par `Password` .</span><span class="sxs-lookup"><span data-stu-id="9ff93-152">Change the second field name to `Oracle Password` and the **Field Type** to `Password`.</span></span>  
  
7.  <span data-ttu-id="9ff93-153">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-153">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="9ff93-154">Sur la page **Paramètres d'appartenance** , ajoutez au moins un **administrateur d'application cible** , puis ajoutez des membres qui ont besoin d'accéder à l'application cible.</span><span class="sxs-lookup"><span data-stu-id="9ff93-154">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="9ff93-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-155">Click **OK**.</span></span>  
  
10. <span data-ttu-id="9ff93-156">Le nouvel ID d'application cible est ajouté à la liste.</span><span class="sxs-lookup"><span data-stu-id="9ff93-156">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="9ff93-157">Sélectionnez l’ID de l’application cible, puis cliquez sur **définir les informations d’identification**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span><span class="sxs-lookup"><span data-stu-id="9ff93-157">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="9ff93-158">Tapez l'ID d'utilisateur Oracle, ainsi que le mot de passe Oracle, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-158">Type the Oracle User ID and Oracle Password and then click **OK**.</span></span>  
  
 <span data-ttu-id="9ff93-159">Pour plus d’informations, consultez la section « pour créer une application cible pour l’authentification SQL Server » dans utiliser la Banque d’informations [sécurisées avec l’authentification SQL Server (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) ( https://technet.microsoft.com/library/gg298949.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9ff93-159">For more information, see section "To Create a target application for SQL Server Authentication" in [Use Secure Store with SQL Server Authentication (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) (https://technet.microsoft.com/library/gg298949.aspx).</span></span>  
  
## <a name="to-configure-the-powerpivot-service-application"></a><span data-ttu-id="9ff93-160">Pour configurer l'application de service PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9ff93-160">To Configure the PowerPivot Service Application</span></span>  
  
1.  <span data-ttu-id="9ff93-161">Dans l'administration centrale de SharePoint, cliquez sur Gérer les applications de service.</span><span class="sxs-lookup"><span data-stu-id="9ff93-161">In SharePoint central administration, click Manage Service Applications.</span></span>  
  
2.  <span data-ttu-id="9ff93-162">Cliquez sur le nom de votre application de service PowerPivot, par exemple « application de service PowerPivot par défaut ».</span><span class="sxs-lookup"><span data-stu-id="9ff93-162">Click the name of your PowerPivot Service Application, for example "Default PowerPivot Service Application".</span></span>  
  
3.  <span data-ttu-id="9ff93-163">Cliquez sur **Configurer les paramètres d'application de service** dans la section Actions.</span><span class="sxs-lookup"><span data-stu-id="9ff93-163">Click **Configure service application settings** in the Actions section.</span></span>  
  
4.  <span data-ttu-id="9ff93-164">Dans la section **actualisation des données** , définissez le compte d’actualisation des **données PowerPivot sans assistance**sur `PowerPivotDataRefresh` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-164">In the **Data Refresh** section, set the **PowerPivot Unattended Data Refresh Account**to`PowerPivotDataRefresh` and then click **OK**.</span></span>  
  
     <span data-ttu-id="9ff93-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span><span class="sxs-lookup"><span data-stu-id="9ff93-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span></span>  
  
## <a name="to-configure-the-workbook"></a><span data-ttu-id="9ff93-166">Pour configurer le classeur</span><span class="sxs-lookup"><span data-stu-id="9ff93-166">To configure the workbook</span></span>  
  
1.  <span data-ttu-id="9ff93-167">Accédez à votre classeur dans la Galerie PowerPivot, puis cliquez sur **gérer l’actualisation des données**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span><span class="sxs-lookup"><span data-stu-id="9ff93-167">Browse to your workbook in the PowerPivot Gallery and click **Manage Data Refresh**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span></span>  
  
2.  <span data-ttu-id="9ff93-168">Si la page **Historique d'actualisation des données** s'affiche, cliquez sur **Configurer la planification**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-168">If you see the **Data Refresh History** page, click **Configure Schedule**.</span></span>  
  
3.  <span data-ttu-id="9ff93-169">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-169">Click **Enable**.</span></span>  
  
4.  <span data-ttu-id="9ff93-170">Cliquez sur **Aussi actualiser dès que possible**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-170">Click **Also Refresh as soon as possible**.</span></span>  
  
5.  <span data-ttu-id="9ff93-171">Dans la section **Informations d'identification** , cliquez sur **Utilisez le compte d'actualisation des données configuré par l'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-171">In the **Credentials** section, click **Use the Data refresh account configured by the administrator**.</span></span>  
  
6.  <span data-ttu-id="9ff93-172">Désactivez la case **Toutes les sources de données**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-172">Clear **All data sources**.</span></span>  
  
7.  <span data-ttu-id="9ff93-173">Sélectionnez **Actualiser** pour la source de données qui utilise les données Oracle.</span><span class="sxs-lookup"><span data-stu-id="9ff93-173">Select **Refresh** for the data source that uses the Oracle data.</span></span> <span data-ttu-id="9ff93-174">Le nom de la source de données peut être modifié dans Microsoft Excel dans le menu **Données**, **Connexions**, **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="9ff93-174">The name of the data source name can be changed in Microsoft Excel in the **Data**, **Connections**, **Properties** menu.</span></span>  
  
8.  <span data-ttu-id="9ff93-175">Sous votre source de données, sélectionnez **Utiliser la planification par défaut**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-175">Under your data source, Select **Use Default Schedule**.</span></span>  
  
9. <span data-ttu-id="9ff93-176">Sélectionnez **Connectez-vous à l'aide des informations d'identification enregistrées dans le service Banque d'informations sécurisé (SSS) pour la connexion à la source de données. Entrez l’ID utilisé pour consulter les informations d’identification dans la zone Identification SSS**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-176">Select **Connect using the credentials saved in Secure Store Service (SSS) to log on to the data source. Enter the ID used to look up the credentials in the SSS ID box**.</span></span>  
  
10. <span data-ttu-id="9ff93-177">Dans la zone **ID :** , tapez `OracleAuthentication` .</span><span class="sxs-lookup"><span data-stu-id="9ff93-177">In the **ID:** box, type `OracleAuthentication`.</span></span>  
  
11. <span data-ttu-id="9ff93-178">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ff93-178">Click **OK**.</span></span>  
  
     <span data-ttu-id="9ff93-179">Si un message d'erreur semblable au suivant s'affiche : `The provided Secure Store target application is either incorrectly configured or does not exist`.</span><span class="sxs-lookup"><span data-stu-id="9ff93-179">If you see an error message similar to: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span></span>  
  
     <span data-ttu-id="9ff93-180">Les deux solutions courantes sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ff93-180">The two common solutions are:</span></span>  
  
    -   <span data-ttu-id="9ff93-181">Vérifiez que l'ID d'application cible est correct.</span><span class="sxs-lookup"><span data-stu-id="9ff93-181">Verify that the Target Application ID is correct.</span></span>  
  
    -   <span data-ttu-id="9ff93-182">Vérifiez que vous définissez les informations d'identification pour l'application cible.</span><span class="sxs-lookup"><span data-stu-id="9ff93-182">Verify that you set credentials for the Target Application.</span></span>  
  
## <a name="to-verify-data-refresh-with-the-new-authentication"></a><span data-ttu-id="9ff93-183">Pour vérifier l'actualisation des données avec la nouvelle authentification</span><span class="sxs-lookup"><span data-stu-id="9ff93-183">To Verify Data Refresh with the new authentication</span></span>  
 <span data-ttu-id="9ff93-184">Lorsque vous cliquez sur **OK**, la page **Historique d'actualisation** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="9ff93-184">When you click **ok**, you see the **Refresh History** page.</span></span> <span data-ttu-id="9ff93-185">Après quelques minutes, vous devez voir apparaître un nouvel élément dans l'historique d'actualisation du fait que vous avez sélectionné **Aussi actualiser dès que possible**dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="9ff93-185">Within a few minutes, you should see a new item in the refresh history because in the previous steps you selected **Also Refresh as soon as possible**.</span></span> <span data-ttu-id="9ff93-186">La valeur par défaut du travail du minuteur **Travail du minuteur d’actualisation des données PowerPivot** est de 1 minute.</span><span class="sxs-lookup"><span data-stu-id="9ff93-186">The default value for the timer job **PowerPivot Data Refresh Timer Job** is 1 minute.</span></span> <span data-ttu-id="9ff93-187">Si aucun nouvel élément n'apparaît dans l'historique d'actualisation, patientez quelques minutes, puis actualisez votre navigateur.</span><span class="sxs-lookup"><span data-stu-id="9ff93-187">If you do not see a new item in the refresh history, wait a few minutes and refresh your browser.</span></span> <span data-ttu-id="9ff93-188">Si le problème persiste, vérifiez la valeur actuelle du travail du minuteur.</span><span class="sxs-lookup"><span data-stu-id="9ff93-188">If you still do not see the new item, verify the current value of the timer job.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="9ff93-189">Informations complémentaires</span><span class="sxs-lookup"><span data-stu-id="9ff93-189">More Information</span></span>  
  
-   <span data-ttu-id="9ff93-190">[Configurer le service Banque d'informations sécurisé dans SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span><span class="sxs-lookup"><span data-stu-id="9ff93-190">[Configure the Secure Store Service in SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span></span>  
  
-   <span data-ttu-id="9ff93-191">Consultez la section « actualisation planifiée des données » de la rubrique [actualisation des données PowerPivot avec SharePoint 2013 et SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span><span class="sxs-lookup"><span data-stu-id="9ff93-191">See the "Scheduled Data Refresh" section of [PowerPivot Data Refresh with SharePoint 2013 and SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span></span>  
  
  
