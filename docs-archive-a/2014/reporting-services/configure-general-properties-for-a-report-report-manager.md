---
title: Configurer les propriétés générales d’un rapport (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], properties
- properties [Reporting Services], general
ms.assetid: 10b941b2-28e6-4408-9ee4-acebc63c8496
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f30900158591afcd5997053dbb61cc22b495ed10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707279"
---
# <a name="configure-general-properties-for-a-report-report-manager"></a><span data-ttu-id="8fb86-102">Configurer les propriétés générales d'un rapport (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="8fb86-102">Configure General Properties for a Report (Report Manager)</span></span>
  
### <a name="to-configure-general-report-properties"></a><span data-ttu-id="8fb86-103">Pour configurer les propriétés générales d'un rapport</span><span class="sxs-lookup"><span data-stu-id="8fb86-103">To configure general report properties</span></span>

1.  <span data-ttu-id="8fb86-104">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="8fb86-104">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>

2.  <span data-ttu-id="8fb86-105">Dans Gestionnaire de rapports, accédez à la page **contenu** .</span><span class="sxs-lookup"><span data-stu-id="8fb86-105">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="8fb86-106">Localisez le rapport pour lequel vous voulez configurer les propriétés générales et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="8fb86-106">Navigate to the report that you want to configure general properties for and open it.</span></span>

3.  <span data-ttu-id="8fb86-107">Cliquez sur l’onglet **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8fb86-107">Click the **Properties** tab.</span></span>

     <span data-ttu-id="8fb86-108">Ou, si la page **contenu** est en mode Détails, cliquez sur l’icône de la page de propriétés :</span><span class="sxs-lookup"><span data-stu-id="8fb86-108">Or, if the **Contents** page is in Details view, click the property page icon:</span></span>

     <span data-ttu-id="8fb86-109">![Icône de la page de propriétés](media/prop.gif "Icône de la page de propriétés")</span><span class="sxs-lookup"><span data-stu-id="8fb86-109">![Property page icon](media/prop.gif "Property page icon")</span></span>

4.  <span data-ttu-id="8fb86-110">La page Propriétés **générales** s’affiche et vous pouvez configurer les propriétés comme suit :</span><span class="sxs-lookup"><span data-stu-id="8fb86-110">The **General** properties page is displayed, and you can configure properties as follows:</span></span>

    -   <span data-ttu-id="8fb86-111">Dans la section **Propriétés** , vous pouvez modifier le nom et la description du rapport.</span><span class="sxs-lookup"><span data-stu-id="8fb86-111">In the **Properties** section, you can modify the report name and description.</span></span>

    -   <span data-ttu-id="8fb86-112">Vous pouvez activer la case à cocher **Masquer en mode liste** pour masquer l’élément lorsque la page est ouverte dans la mise en page par défaut (mode liste) qui réorganise les éléments sur la page.</span><span class="sxs-lookup"><span data-stu-id="8fb86-112">You can select the **Hide in list view** checkbox to hide the item when the page is opened in the default page layout (list view) which arranges items across and down the page.</span></span>

    -   <span data-ttu-id="8fb86-113">Dans la section **définition de rapport** , cliquez sur **modifier** pour extraire une copie de la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="8fb86-113">In the **Report Definition** section, click **Edit** to extract a copy of the report definition.</span></span> <span data-ttu-id="8fb86-114">Les modifications que vous apportez localement à la définition de rapport ne sont pas enregistrées sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="8fb86-114">Modifications that you make locally to the report definition are not saved on the report server.</span></span>

         <span data-ttu-id="8fb86-115">Ou, pour mettre à jour la définition de rapport à partir d’un fichier. rdl, cliquez sur **mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="8fb86-115">Or, to update the report definition from an .rdl file, click **Update**.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="8fb86-116">Si vous procédez à la mise à jour d'une définition de rapport, redéfinissez les paramètres de la source de données une fois cette opération terminée.</span><span class="sxs-lookup"><span data-stu-id="8fb86-116">If you update a report definition, you must reset the data source settings after the update is completed.</span></span>

    -   <span data-ttu-id="8fb86-117">Utilisez les boutons **supprimer** ou **déplacer** pour supprimer ou déplacer le rapport.</span><span class="sxs-lookup"><span data-stu-id="8fb86-117">Use the **Delete** or **Move** buttons to delete or move the report.</span></span>

    -   <span data-ttu-id="8fb86-118">Vous pouvez également créer un rapport lié.</span><span class="sxs-lookup"><span data-stu-id="8fb86-118">You can also create a linked report.</span></span>

5.  <span data-ttu-id="8fb86-119">Lorsque vous avez terminé de configurer les propriétés générales du rapport, cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="8fb86-119">When you have finished configuring general properties for the report, click **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8fb86-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8fb86-120">See Also</span></span>
 <span data-ttu-id="8fb86-121">[Déplacer ou supprimer un élément &#40;gestionnaire de rapports](report-server/move-or-delete-an-item-report-manager.md) [page&#41;contenu &#40;gestionnaire de rapports](../../2014/reporting-services/contents-page-report-manager.md)&#41;la [recherche, l’affichage et la gestion des rapports &#40;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [page Propriétés générales](../../2014/reporting-services/general-properties-page-reports-report-manager.md) générateur de rapports et SSRS &#41;, rapports &#40;gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="8fb86-121">[Move or Delete an Item &#40;Report Manager&#41;](report-server/move-or-delete-an-item-report-manager.md) [Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) [Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md)</span></span>


