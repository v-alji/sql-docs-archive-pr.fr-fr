---
title: Publier et republier des parties de rapports (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92dce484-f39b-403c-9caf-d8772bc3aca3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95fd5e3f7519c6a0d4a6f08cb9bcbf2507d32aaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603832"
---
# <a name="publish-and-republish-report-parts-report-builder-and-ssrs"></a><span data-ttu-id="2b526-102">Publier et republier des parties de rapports (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="2b526-102">Publish and Republish Report Parts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2b526-103">Vous pouvez publier une partie de rapport avec des paramètres par défaut à un emplacement par défaut, ou vous pouvez modifier des métadonnées de partie de rapport, telles que le nom et la description, puis les enregistrer ailleurs sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2b526-103">You can publish a report part with default settings in a default location, or you can edit report part metadata such as name and description, and save it somewhere else on a report server.</span></span> <span data-ttu-id="2b526-104">Vous pouvez également les enregistrer sur un site SharePoint intégré avec un serveur de rapports si vous avez les autorisations appropriées.</span><span class="sxs-lookup"><span data-stu-id="2b526-104">You can also save it to a SharePoint site that is integrated with a report server if you have the correct permissions.</span></span>  
  
 <span data-ttu-id="2b526-105">Vous pouvez publier uniquement la partie de rapport, avec le dataset duquel elle dépend incorporé, ou vous pouvez publier le dataset séparément.</span><span class="sxs-lookup"><span data-stu-id="2b526-105">You can publish just the report part, with the dataset that it depends on embedded in it, or you can publish the dataset separately.</span></span> <span data-ttu-id="2b526-106">Si vous publiez le dataset séparément, il devient un dataset partagé et la partie de rapport est liée à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="2b526-106">If you publish the dataset separately, it becomes a shared dataset, and the report part links to it.</span></span> <span data-ttu-id="2b526-107">Pour plus d’informations, consultez [Parties de rapports et datasets dans le Générateur de rapports](../report-data/report-parts-and-datasets-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="2b526-107">For more information, see [Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="2b526-108">Vous pouvez republier une partie de rapport existante.</span><span class="sxs-lookup"><span data-stu-id="2b526-108">You can republish an existing report part.</span></span> <span data-ttu-id="2b526-109">Si vous avez les autorisations, vous pouvez enregistrer sur l'instance d'origine de la partie de rapport sur le serveur, même si vous ne l'avez pas créée.</span><span class="sxs-lookup"><span data-stu-id="2b526-109">If you have permissions, you can save over the original instance of the report part on the server, even if you didn't create it.</span></span> <span data-ttu-id="2b526-110">Vous pouvez également la publier comme une nouvelle partie de rapport et l'enregistrer au même emplacement ou à un endroit différent.</span><span class="sxs-lookup"><span data-stu-id="2b526-110">You can also publish it as a new report part and save it either in the same or a different location.</span></span>  
  
### <a name="to-publish-a-report-part"></a><span data-ttu-id="2b526-111">Pour publier une partie de rapport</span><span class="sxs-lookup"><span data-stu-id="2b526-111">To publish a report part</span></span>  
  
1.  <span data-ttu-id="2b526-112">Dans le menu du Générateur de rapports, cliquez sur **Publier les parties de rapport**.</span><span class="sxs-lookup"><span data-stu-id="2b526-112">On the Report Builder menu, click **Publish Report Parts**.</span></span>  
  
     <span data-ttu-id="2b526-113">Si vous n'êtes pas connecté à un serveur de rapports, vous serez invité à le faire.</span><span class="sxs-lookup"><span data-stu-id="2b526-113">If you are not connected to a report server, you will be prompted to connect.</span></span> <span data-ttu-id="2b526-114">Si vous ne pouvez pas vous connecter à un serveur de rapports, vous ne pouvez pas publier des parties de rapport.</span><span class="sxs-lookup"><span data-stu-id="2b526-114">If you cannot connect to a report server, you cannot publish report parts.</span></span>  
  
2.  <span data-ttu-id="2b526-115">Pour enregistrer vos parties de rapport avec les paramètres par défaut à l’emplacement par défaut, cliquez sur **Publier toutes les parties de rapport avec les paramètres par défaut**.</span><span class="sxs-lookup"><span data-stu-id="2b526-115">To save your report parts with default settings to the default location, click **Publish all report parts with default settings**.</span></span>  
  
     <span data-ttu-id="2b526-116">Sinon, cliquez sur **Vérifier et modifier les parties de rapport avant de procéder à la publication**.</span><span class="sxs-lookup"><span data-stu-id="2b526-116">Otherwise, click **Review and modify report parts before publishing**.</span></span>  
  
3.  <span data-ttu-id="2b526-117">Modifiez le nom et la description de la partie de rapport : double-cliquez sur le nom pour le modifier et cliquez dans le champ **Description** pour ajouter une description.</span><span class="sxs-lookup"><span data-stu-id="2b526-117">Edit the report part name and description: Double-click the name to edit it and click in the **Description** field to add a description.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2b526-118">Il est judicieux de donner un nom et une description à la partie de rapport pour aider les personnes à l'identifier lors de la recherche.</span><span class="sxs-lookup"><span data-stu-id="2b526-118">It is a good idea to give the report part name and description, to help people identify it when searching.</span></span> <span data-ttu-id="2b526-119">La longueur maximale du nom d'une partie de rapport est de 260 caractères pour le chemin d'accès entier, y compris les noms des dossiers sur le serveur, suivi par le nom réel de la partie de rapport.</span><span class="sxs-lookup"><span data-stu-id="2b526-119">The maximum length for the name of a report part is 260 characters for the entire path, including the names of the folders on the server, followed by the actual name of the report part.</span></span>  
  
4.  <span data-ttu-id="2b526-120">Pour enregistrer votre partie de rapport dans un dossier autre que celui par défaut, cliquez sur le bouton **Parcourir** .</span><span class="sxs-lookup"><span data-stu-id="2b526-120">To save your report part to a folder other than the default, click the **Browse** button.</span></span>  
  
5.  <span data-ttu-id="2b526-121">Quand vous avez défini les options pour toutes les parties de rapports du rapport, cliquez sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="2b526-121">When you have set the options for all the report parts in the report, click **Publish**.</span></span>  
  
     <span data-ttu-id="2b526-122">Une fois que vous avez publié les parties de rapports, la boîte de dialogue affiche ceux qui ont été correctement publiés et ceux qui ne l'ont pas été.</span><span class="sxs-lookup"><span data-stu-id="2b526-122">After you publish the report parts, the dialog box shows which were successfully published and which were not.</span></span> <span data-ttu-id="2b526-123">Vous pouvez consulter les détails dans la boîte de dialogue **Publier les parties de rapports** pour les parties de rapports dont la publication a échoué.</span><span class="sxs-lookup"><span data-stu-id="2b526-123">You can view details in the **Publish Report Parts** dialog box for the report parts that failed to publish.</span></span>  
  
6.  <span data-ttu-id="2b526-124">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="2b526-124">Click **Close**.</span></span>  
  
### <a name="to-republish-a-report-part"></a><span data-ttu-id="2b526-125">Pour republier une partie de rapport</span><span class="sxs-lookup"><span data-stu-id="2b526-125">To republish a report part</span></span>  
  
1.  <span data-ttu-id="2b526-126">Suivez la procédure précédente pour la publication d'une partie de rapport.</span><span class="sxs-lookup"><span data-stu-id="2b526-126">Follow the previous procedure for publishing a report part.</span></span>  
  
2.  <span data-ttu-id="2b526-127">Dans la boîte de dialogue **Publier les parties de rapport** , si vous cliquez sur **Publier en tant que nouvelle copie de la partie de rapport**, le Générateur de rapports n’enregistre pas sur la partie de rapport existante sur le serveur, mais crée à la place une autre partie de rapport.</span><span class="sxs-lookup"><span data-stu-id="2b526-127">In the **Publish Report Parts** dialog box, if you click **Publish as a New Copy of the Report Part**, Report Builder will not save over the existing report part on the server, but will create another report part instead.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b526-128">Si vous la publiez en tant que nouvelle partie de rapport, elle aura un nouvel ID unique.</span><span class="sxs-lookup"><span data-stu-id="2b526-128">If you publish it as a new report part, it will have a new unique ID.</span></span> <span data-ttu-id="2b526-129">Elle ne recevra plus les mises à jour si la partie de rapport d'origine est modifiée.</span><span class="sxs-lookup"><span data-stu-id="2b526-129">It will no longer receive updates if the original report part changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b526-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b526-130">See Also</span></span>  
 <span data-ttu-id="2b526-131">[Parties de rapport &#40;Générateur de rapports et SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2b526-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2b526-132">[Parties de rapports et datasets dans Générateur de rapports](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="2b526-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="2b526-133">[Résoudre les problèmes liés aux parties de rapports &#40;Générateur de rapports et SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2b526-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2b526-134">[Rechercher les mises à jour ou désactiver les mises à jour &#40;Générateur de rapports et SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2b526-134">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2b526-135">Rechercher des parties de rapports et définir un dossier par défaut &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2b526-135">Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;</span></span>](browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md)  
  
  
