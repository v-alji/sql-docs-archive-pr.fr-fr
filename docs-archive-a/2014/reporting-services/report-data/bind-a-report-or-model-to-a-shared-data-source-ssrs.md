---
title: Lier un rapport ou un modèle à une source de données partagée (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
ms.assetid: 23cc15f2-2883-48e2-bc6c-fa0ab61a2e21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 596caba042d476173b3c49d1ad18e79d0827fe89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697560"
---
# <a name="bind-a-report-or-model-to-a-shared-data-source-ssrs"></a><span data-ttu-id="cfde6-102">Lier un rapport ou un modèle à une source de données partagée (SSRS)</span><span class="sxs-lookup"><span data-stu-id="cfde6-102">Bind a Report or Model to a Shared Data Source (SSRS)</span></span>
  <span data-ttu-id="cfde6-103">Dans certaines situations, par exemple si vous déplacez un rapport ou un modèle d'un serveur test vers un serveur de production, vous pouvez envisager d'enregistrer le fichier sur votre ordinateur local puis de le télécharger sur un autre serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cfde6-103">In some situations, such as when you move a report or model from a test server to a production server, you might want to save the file to your local computer and then upload it to a different report server.</span></span> <span data-ttu-id="cfde6-104">Si vous téléchargez le rapport ou le modèle sur le nouveau serveur, vous devez le lier de nouveau à une source de données partagée stockée sur le nouveau serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cfde6-104">When you upload the report or model to the new server, you need to rebind it to a shared data source that is stored on the new report server.</span></span> <span data-ttu-id="cfde6-105">Si vous ne liez pas de nouveau le rapport ou le modèle, celui-ci ne fonctionnera pas correctement en cas d'accès à partir du nouveau serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cfde6-105">If you don't rebind the report or model, it will not work correctly when accessed from the new report server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cfde6-106">Avant de procéder à cette opération, la source de données doit déjà exister sur le serveur de rapports ou la bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfde6-106">Before rebinding a report or model to a shared data source, the data source must already exist on the report server or SharePoint library.</span></span> <span data-ttu-id="cfde6-107">Pour plus d’informations sur les sources de données, consultez [Créer, modifier, puis supprimer des sources de données partagées &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cfde6-107">For more information about data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-native-mode"></a><span data-ttu-id="cfde6-108">Pour lier un rapport ou un modèle à une source de données partagée sur un serveur de rapports s'exécutant en mode natif</span><span class="sxs-lookup"><span data-stu-id="cfde6-108">To bind a report or model to a shared data source on a report server running in native mode</span></span>  
  
1.  <span data-ttu-id="cfde6-109">Dans le **Gestionnaire de rapports**, cliquez sur le nom du rapport ou du modèle que vous avez téléchargé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="cfde6-109">In **Report Manager**, click the name of the report or model that you uploaded to the server.</span></span>  
  
     <span data-ttu-id="cfde6-110">L'onglet Propriétés s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="cfde6-110">The Properties tab opens.</span></span>  
  
2.  <span data-ttu-id="cfde6-111">Cliquez sur **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="cfde6-111">Click **Data Sources**.</span></span>  
  
3.  <span data-ttu-id="cfde6-112">Cliquez sur **Parcourir**, puis accédez à la source de données à laquelle vous souhaitez lier le modèle ou le rapport.</span><span class="sxs-lookup"><span data-stu-id="cfde6-112">Click **Browse**, and then navigate to the data source to which you want to bind the report or model.</span></span>  
  
4.  <span data-ttu-id="cfde6-113">Sélectionnez la source de données, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfde6-113">Select the data source and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="cfde6-114">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="cfde6-114">Click **Apply**.</span></span>  
  
     <span data-ttu-id="cfde6-115">Le rapport ou le modèle est désormais lié à une source de données que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cfde6-115">The report or model is now bound to the data source that you selected.</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-sharepoint-integrated-mode"></a><span data-ttu-id="cfde6-116">Pour lier un rapport ou un modèle à une source de données partagée sur un serveur de rapports s'exécutant en mode intégré SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfde6-116">To bind a report or model to a shared data source on a report server running in SharePoint integrated mode</span></span>  
  
1.  <span data-ttu-id="cfde6-117">Si la bibliothèque n'est pas déjà ouverte, cliquez sur son nom dans la barre de lancement rapide.</span><span class="sxs-lookup"><span data-stu-id="cfde6-117">If the library is not already open, click its name on the Quick Launch bar.</span></span> <span data-ttu-id="cfde6-118">Si le nom de la bibliothèque n'est pas visible, cliquez sur **Afficher tout le contenu du site**, puis sur le nom de la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="cfde6-118">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="cfde6-119">Pointez sur le rapport ou le modèle et cliquez sur la flèche orientée vers le bas.</span><span class="sxs-lookup"><span data-stu-id="cfde6-119">Point to the report or model and click the down arrow.</span></span>  
  
3.  <span data-ttu-id="cfde6-120">Cliquez sur **Gérer les sources de données**.</span><span class="sxs-lookup"><span data-stu-id="cfde6-120">Click **Manage Data Sources**.</span></span>  
  
4.  <span data-ttu-id="cfde6-121">Cliquez sur **dataSource1**.</span><span class="sxs-lookup"><span data-stu-id="cfde6-121">Click **dataSource1**.</span></span>  
  
5.  <span data-ttu-id="cfde6-122">Dans la zone **Type de connexion** , vérifiez que **Source de données partagée** est activée.</span><span class="sxs-lookup"><span data-stu-id="cfde6-122">In the **Connection Type** area, verify that **Shared data source** is selected.</span></span>  
  
6.  <span data-ttu-id="cfde6-123">Dans la zone lien de la **source de données** , cliquez sur le bouton de sélection (...).</span><span class="sxs-lookup"><span data-stu-id="cfde6-123">In the **Data Source Link** area, click the ellipsis (...) button.</span></span>  
  
7.  <span data-ttu-id="cfde6-124">Localisez la source de données que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="cfde6-124">Locate the data source you want to use.</span></span>  
  
8.  <span data-ttu-id="cfde6-125">Sélectionnez la source de données et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfde6-125">Select the data source and **click OK**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="cfde6-126">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="cfde6-126">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfde6-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfde6-127">See Also</span></span>  
 <span data-ttu-id="cfde6-128">[Télécharger un fichier ou un rapport &#40;Gestionnaire de rapports&#41;](../reports/upload-a-file-or-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="cfde6-128">[Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md) </span></span>  
 <span data-ttu-id="cfde6-129">[Télécharger des documents vers une bibliothèque SharePoint &#40;Reporting Services en mode SharePoint&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="cfde6-129">[Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="cfde6-130">[Créer et gérer des sources de données partagées &#40;Reporting Services en mode intégré SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span><span class="sxs-lookup"><span data-stu-id="cfde6-130">[Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span></span>  
 <span data-ttu-id="cfde6-131">[Créer, supprimer ou modifier une source de données partagée &#40;Gestionnaire de rapports&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="cfde6-131">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="cfde6-132">[Connexions de données, sources de données et chaînes de connexion dans Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="cfde6-132">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="cfde6-133">Sources de données prises en charge par Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cfde6-133">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](../create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
