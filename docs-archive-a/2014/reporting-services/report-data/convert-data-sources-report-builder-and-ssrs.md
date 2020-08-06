---
title: Convertir une source de données incorporée en source partagée (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
- data sources [Reporting Services], shared
ms.assetid: 0e099c7e-8c03-43eb-9ea3-76e52d9ebbe3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5827bab564b58e7a2b7922f01a33f550a6f523f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601909"
---
# <a name="convert-a-data-source-from-embedded-to-shared-report-builder-and-ssrs"></a><span data-ttu-id="805bd-102">Convertir une source de données incorporée en source partagée (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="805bd-102">Convert a Data Source from Embedded to Shared (Report Builder and SSRS)</span></span>
  <span data-ttu-id="805bd-103">Chaque source de données dans le volet des données de rapport est incorporée et est spécifique au rapport ou est partagée.</span><span class="sxs-lookup"><span data-stu-id="805bd-103">Each data source in the Report Data pane is embedded and specific to the report or is shared.</span></span> <span data-ttu-id="805bd-104">Dans le Générateur de rapports, une source de données partagée pointe vers une source de données partagée publiée sur un serveur de rapports ou un site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="805bd-104">In Report Builder, a shared data source points to a published shared data source on a report server or SharePoint site.</span></span> <span data-ttu-id="805bd-105">Dans le Concepteur de rapports, une source de données partagée pointe vers une source de données partagée dans l’Explorateur de solutions sous le dossier **Sources de données partagées** .</span><span class="sxs-lookup"><span data-stu-id="805bd-105">In Report Designer, a shared data source points to a shared data source in the **Shared Data Sources** folder in Solution Explorer.</span></span>  
  
 <span data-ttu-id="805bd-106">Pour plus d’informations sur les différences entre les sources de données incorporées et partagées, consultez [Connexions de données ou sources de données incorporées et partagées &#40;Générateur de rapports et SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="805bd-106">For more information about the differences between embedded and shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="805bd-107">Pour plus d’informations sur la création d’une source de données partagée, consultez [Créer une source de données incorporée ou partagée &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="805bd-107">For more information on how to create a shared data source, see [Create an Embedded or Shared Data Source &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="report-designer"></a><span data-ttu-id="805bd-108">Concepteur de rapports</span><span class="sxs-lookup"><span data-stu-id="805bd-108">Report Designer</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="805bd-109">Pour convertir une source de données incorporée en source partagée</span><span class="sxs-lookup"><span data-stu-id="805bd-109">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="805bd-110">Dans le volet des données de rapport, cliquez avec le bouton droit sur la source de données, puis cliquez sur **Convertir en source de données partagée**.</span><span class="sxs-lookup"><span data-stu-id="805bd-110">In the Report Data pane, right-click the data source, and then click **Convert to Shared Data Source**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="805bd-111">Si le volet des données de rapport n’est pas visible, cliquez sur **Données du rapport** dans le menu **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="805bd-111">If the Report Data pane is not visible, on the **View** menu, click **Report Data**.</span></span> <span data-ttu-id="805bd-112">Si le volet s'ouvre comme une fenêtre flottante, vous pouvez l'ancrer.</span><span class="sxs-lookup"><span data-stu-id="805bd-112">If the pane opens as a floating window, you can dock it.</span></span> <span data-ttu-id="805bd-113">Pour plus d’informations, consultez [Ancrer le volet des données de rapport dans le Concepteur de rapports &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="805bd-113">For more information, see [Dock the Report Data Pane in Report Designer &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span></span>  
  
     <span data-ttu-id="805bd-114">Dans le volet des données de rapport, l'icône de source de données se transforme en icône de source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="805bd-114">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span> <span data-ttu-id="805bd-115">Dans l’Explorateur de solutions, une source de données partagée avec le même nom s’affiche sous le dossier **Sources de données partagées** .</span><span class="sxs-lookup"><span data-stu-id="805bd-115">In Solution Explorer, a shared data source with the same name appears under the **Shared Data Source** folder.</span></span>  
  
### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="805bd-116">Pour convertir une source de données partagée en source incorporée</span><span class="sxs-lookup"><span data-stu-id="805bd-116">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="805bd-117">Dans le volet des données de rapport, cliquez avec le bouton droit sur la source de données, ouvrez la boîte de dialogue **Propriétés de la source de données** , puis cliquez sur **Connexion incorporée**.</span><span class="sxs-lookup"><span data-stu-id="805bd-117">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="805bd-118">Entrez les informations requises.</span><span class="sxs-lookup"><span data-stu-id="805bd-118">Enter the required information.</span></span>  
  
     <span data-ttu-id="805bd-119">Dans le volet des données de rapport, l'icône de source de données se transforme en icône de source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="805bd-119">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="report-builder"></a><span data-ttu-id="805bd-120">Générateur de rapports</span><span class="sxs-lookup"><span data-stu-id="805bd-120">Report Builder</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="805bd-121">Pour convertir une source de données incorporée en source partagée</span><span class="sxs-lookup"><span data-stu-id="805bd-121">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="805bd-122">Dans le volet des données de rapport, cliquez avec le bouton droit sur la source de données pour ouvrir la boîte de dialogue **Propriétés de la source de données** , puis cliquez sur **Connexion incorporée**.</span><span class="sxs-lookup"><span data-stu-id="805bd-122">In the Report Data pane, right-click the data source to open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="805bd-123">Entrez les informations requises.</span><span class="sxs-lookup"><span data-stu-id="805bd-123">Enter the required information.</span></span>  
  
     <span data-ttu-id="805bd-124">Dans le volet des données de rapport, l'icône de source de données se transforme en icône de source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="805bd-124">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
#### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="805bd-125">Pour convertir une source de données partagée en source incorporée</span><span class="sxs-lookup"><span data-stu-id="805bd-125">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="805bd-126">Dans le volet des données de rapport, cliquez avec le bouton droit sur la source de données, ouvrez la boîte de dialogue **Propriétés de la source de données** , puis cliquez sur **Connexion incorporée**.</span><span class="sxs-lookup"><span data-stu-id="805bd-126">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="805bd-127">Entrez les informations requises.</span><span class="sxs-lookup"><span data-stu-id="805bd-127">Enter the required information.</span></span>  
  
     <span data-ttu-id="805bd-128">Dans le volet des données de rapport, l'icône de source de données se transforme en icône de source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="805bd-128">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805bd-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="805bd-129">See Also</span></span>  
 <span data-ttu-id="805bd-130">[Gérer des sources de données de rapports](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="805bd-130">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="805bd-131">Connexions de données, sources de données et chaînes de connexion dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="805bd-131">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
