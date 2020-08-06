---
title: Analyser un modèle tabulaire dans Excel (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.chooseperspect.f1
ms.assetid: 47fa45fc-60ab-41a1-bde3-5781c8462889
author: minewiskan
ms.author: owend
ms.openlocfilehash: fae542ffb5b470d23d9cf27fcc11367f571e7cec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612482"
---
# <a name="analyze-a-tabular-model-in-excel-ssas-tabular"></a><span data-ttu-id="1021e-102">Analyser un modèle tabulaire dans Excel (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="1021e-102">Analyze a Tabular Model in Excel (SSAS Tabular)</span></span>
  <span data-ttu-id="1021e-103">La fonctionnalité Analyser dans Excel de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ouvre l’application Microsoft Excel, crée une connexion de source de données à la base de données model de l’espace de travail, puis ajoute un tableau croisé dynamique à la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="1021e-103">The Analyze in Excel feature in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] opens Microsoft Excel, creates a data source connection to the model workspace database, and adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="1021e-104">Les objets de modèle (tables, colonnes, mesures, hiérarchies et KPI) sont inclus en tant que champs dans la liste de champs du tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="1021e-104">Model objects (tables, columns, measures, hierarchies, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1021e-105">Pour utiliser la fonctionnalité Analyser dans Excel, vous devez disposer de Microsoft Office 2003 ou d’une version ultérieure installée sur le même ordinateur que [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1021e-105">To use the Analyze in Excel feature, you must have Microsoft Office 2003 or later installed on the same computer as [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="1021e-106">Si Office n'est pas installé sur le même ordinateur, vous pouvez utiliser Excel sur un autre ordinateur et vous connecter à la base de données model de l'espace de travail comme source de données.</span><span class="sxs-lookup"><span data-stu-id="1021e-106">If Office is not installed on the same computer, you can use Excel on another computer and connect to the model workspace database as a data source.</span></span> <span data-ttu-id="1021e-107">Vous pouvez ensuite ajouter manuellement un tableau croisé dynamique à la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="1021e-107">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="1021e-108">Les objets de modèle (tables, colonnes, mesures et KPI) sont inclus en tant que champs dans la liste de champs du tableau croisé dynamique.</span><span class="sxs-lookup"><span data-stu-id="1021e-108">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="1021e-109">Tâches</span><span class="sxs-lookup"><span data-stu-id="1021e-109">Tasks</span></span>  
  
#### <a name="to-analyze-a-tabular-model-project-by-using-the-analyze-in-excel-feature"></a><span data-ttu-id="1021e-110">Pour analyser un projet de modèle tabulaire à l'aide de la fonctionnalité Analyser dans Excel</span><span class="sxs-lookup"><span data-stu-id="1021e-110">To analyze a tabular model project by using the Analyze in Excel feature</span></span>  
  
1.  <span data-ttu-id="1021e-111">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Analyser dans Excel**.</span><span class="sxs-lookup"><span data-stu-id="1021e-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Analyze in Excel**.</span></span>  
  
2.  <span data-ttu-id="1021e-112">Dans la boîte de dialogue **Choisir les informations d’identification et la perspective** , sélectionnez l’une des options relatives aux informations d’identification suivantes pour vous connecter à la source de données de l’espace de travail du modèle :</span><span class="sxs-lookup"><span data-stu-id="1021e-112">In the **Choose Credential and Perspective** dialog box, select one of the following credential options to connect to the model workspace data source:</span></span>  
  
    -   <span data-ttu-id="1021e-113">Pour utiliser le compte d’utilisateur actuel, sélectionnez **Utilisateur Windows actuel**.</span><span class="sxs-lookup"><span data-stu-id="1021e-113">To use the current user account, select **Current Windows User**.</span></span>  
  
    -   <span data-ttu-id="1021e-114">Pour utiliser un compte d’utilisateur différent, sélectionnez **Autre utilisateur Windows**.</span><span class="sxs-lookup"><span data-stu-id="1021e-114">To use a different user account, select **Other Windows User**.</span></span>  
  
         <span data-ttu-id="1021e-115">En général, ce compte d'utilisateur est membre d'un rôle.</span><span class="sxs-lookup"><span data-stu-id="1021e-115">Typically, this user account will be a member of a role.</span></span> <span data-ttu-id="1021e-116">Aucun mot de passe n'est requis.</span><span class="sxs-lookup"><span data-stu-id="1021e-116">No password is required.</span></span> <span data-ttu-id="1021e-117">Le compte ne peut être utilisé que dans le contexte d'une connexion Excel à la base de données d'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="1021e-117">The account can only be used in the context of an Excel connection to the workspace database.</span></span>  
  
    -   <span data-ttu-id="1021e-118">Pour utiliser un rôle de sécurité, sélectionnez **Rôle**puis, dans la zone de liste, sélectionnez un ou plusieurs rôles.</span><span class="sxs-lookup"><span data-stu-id="1021e-118">To use a security role, select **Role**, and then in the listbox, select one or more roles.</span></span>  
  
         <span data-ttu-id="1021e-119">Les rôles de sécurité doivent être définis à l'aide du gestionnaire de rôles.</span><span class="sxs-lookup"><span data-stu-id="1021e-119">Security roles must be defined using the Role Manager.</span></span> <span data-ttu-id="1021e-120">Pour plus d’informations, consultez [Créer et gérer des rôles &#40;SSAS Tabulaire&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="1021e-120">For more information, see [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
3.  <span data-ttu-id="1021e-121">Pour utiliser une perspective, dans la zone de liste **Perspective** , sélectionnez une perspective.</span><span class="sxs-lookup"><span data-stu-id="1021e-121">To use a perspective, in the **Perspective** listbox, select a perspective.</span></span>  
  
     <span data-ttu-id="1021e-122">Les perspectives (autres que celles par défaut) doivent être définies à l'aide de la boîte de dialogue Perspectives.</span><span class="sxs-lookup"><span data-stu-id="1021e-122">Perspectives (other than default) must be defined using the Perspectives dialog box.</span></span> <span data-ttu-id="1021e-123">Pour plus d’informations, consultez [créer et gérer des Perspectives &#40;&#41;tabulaires SSAS ](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="1021e-123">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1021e-124">La liste de champs du tableau croisé dynamique dans Excel n'est pas actualisée automatiquement lorsque vous apportez des modifications au projet de modèle dans le générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="1021e-124">The PivotTable Field List in Excel does not refresh automatically as you make changes to the model project in the model designer.</span></span> <span data-ttu-id="1021e-125">Pour actualiser la liste de champs du tableau croisé dynamique, dans Excel, dans le ruban **Options** , cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="1021e-125">To refresh the PivotTable Field List, in Excel, on the **Options** ribbon, click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1021e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1021e-126">See Also</span></span>  
 [<span data-ttu-id="1021e-127">Analyser dans Excel &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="1021e-127">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](analyze-in-excel-ssas-tabular.md)  
  
  
