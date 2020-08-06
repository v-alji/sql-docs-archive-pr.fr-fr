---
title: Page général | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Business_Intelligence_Designers.Data_Transformation_Designers.General
ms.assetid: d695690a-923b-4036-945e-7621e8651deb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59073ac29f95f1e64bd0a9382366e9539ce1408a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601584"
---
# <a name="general-page"></a><span data-ttu-id="ceed4-102">Page Général</span><span class="sxs-lookup"><span data-stu-id="ceed4-102">General Page</span></span>
  <span data-ttu-id="ceed4-103">Utilisez la page **Général** de la page **Concepteurs de services d'intégration** dans la boîte de dialogue **Options** pour spécifier les options de chargement, d'affichage et de mise à niveau des packages.</span><span class="sxs-lookup"><span data-stu-id="ceed4-103">Use the **General** page of the **Integration Services Designers** page in the **Options** dialog box to specify the options for loading, displaying, and upgrading packages.</span></span>  
  
 <span data-ttu-id="ceed4-104">Pour ouvrir la page **Général** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], dans le menu **Outils** , cliquez sur **Options**, développez **Concepteurs Business Intelligence**et sélectionnez **Concepteurs de services d'intégration**.</span><span class="sxs-lookup"><span data-stu-id="ceed4-104">To open the **General** page, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Tools** menu, click **Options**, expand **Business Intelligence Designers**, and select **Integration Services Designers**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ceed4-105">Options</span><span class="sxs-lookup"><span data-stu-id="ceed4-105">Options</span></span>  
 <span data-ttu-id="ceed4-106">**Vérifier la signature numérique lors du chargement d'un package**</span><span class="sxs-lookup"><span data-stu-id="ceed4-106">**Check digital signature when loading a package**</span></span>  
 <span data-ttu-id="ceed4-107">Sélectionnez cette option pour que [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vérifie la signature numérique durant le chargement d’un package.</span><span class="sxs-lookup"><span data-stu-id="ceed4-107">Select to have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] check the digital signature when loading a package.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="ceed4-108">vérifie uniquement si la signature numérique est présente, si elle est valide et si elle provient d’une source fiable.</span><span class="sxs-lookup"><span data-stu-id="ceed4-108">will only check whether the digital signature is present, is valid, and is from a trusted source.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="ceed4-109">ne vérifie pas si le package a été modifié depuis qu'il a été signé.</span><span class="sxs-lookup"><span data-stu-id="ceed4-109">will not check whether the package has been changed since the package was signed.</span></span>  
  
 <span data-ttu-id="ceed4-110">Si vous définissez la valeur de Registre **BlockedSignatureStates** , cette valeur de Registre remplace l’option **Vérifier la signature numérique lors du chargement d’un package** .</span><span class="sxs-lookup"><span data-stu-id="ceed4-110">If you set the **BlockedSignatureStates** registry value, this registry value overrides the **Check digital signature when loading a package** option.</span></span> <span data-ttu-id="ceed4-111">Pour plus d’informations, consultez [Implémenter une stratégie de signature en définissant une valeur de Registre](implement-a-signing-policy-by-setting-a-registry-value.md).</span><span class="sxs-lookup"><span data-stu-id="ceed4-111">For more information, see [Implement a Signing Policy by Setting a Registry Value](implement-a-signing-policy-by-setting-a-registry-value.md).</span></span>  
  
 <span data-ttu-id="ceed4-112">Pour plus d’informations sur les packages et les certificats numériques, consultez [Identifier la source de packages à l’aide de signatures numériques](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="ceed4-112">For more information about digital certificates and packages, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
 <span data-ttu-id="ceed4-113">**Afficher un avertissement si un package n'est pas signé**</span><span class="sxs-lookup"><span data-stu-id="ceed4-113">**Show warning if package is unsigned**</span></span>  
 <span data-ttu-id="ceed4-114">Sélectionnez cette option pour afficher un avertissement lors du chargement d'un package qui n'est pas signé.</span><span class="sxs-lookup"><span data-stu-id="ceed4-114">Select to display a warning when loading a package that is not signed.</span></span>  
  
 <span data-ttu-id="ceed4-115">**Afficher les étiquettes de contrainte de précédence**</span><span class="sxs-lookup"><span data-stu-id="ceed4-115">**Show precedence constraint labels**</span></span>  
 <span data-ttu-id="ceed4-116">Sélectionnez l’étiquette (Réussite, Échec ou À l’achèvement) à afficher sur les contraintes de précédence pendant la consultation de packages dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ceed4-116">Select which label-Success, Failure, or Completion-to display on precedence constraints when viewing packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ceed4-117">**Langage de script**</span><span class="sxs-lookup"><span data-stu-id="ceed4-117">**Scripting language**</span></span>  
 <span data-ttu-id="ceed4-118">Sélectionnez le langage de script par défaut pour les nouvelles tâches de script et les composants Script.</span><span class="sxs-lookup"><span data-stu-id="ceed4-118">Select the default scripting language for new Script tasks and Script components.</span></span>  
  
 <span data-ttu-id="ceed4-119">**Mettre à jour les chaînes de connexion pour l'utilisation des nouveaux noms de fournisseurs**</span><span class="sxs-lookup"><span data-stu-id="ceed4-119">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="ceed4-120">Durant l’ouverture ou la mise à niveau de packages [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] , mettez à jour les chaînes de connexion afin d’utiliser les noms correspondant aux fournisseurs suivants, pour la version actuelle de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ceed4-120">When opening or upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, update connection strings to use the names for the following providers, for the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="ceed4-121">Fournisseur OLE DB</span><span class="sxs-lookup"><span data-stu-id="ceed4-121">OLE DB provider</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="ceed4-122">Native Client</span><span class="sxs-lookup"><span data-stu-id="ceed4-122">Native Client</span></span>  
  
 <span data-ttu-id="ceed4-123">L'Assistant Mise à niveau de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] met à jour uniquement les chaînes de connexion qui sont stockées dans des gestionnaires de connexions.</span><span class="sxs-lookup"><span data-stu-id="ceed4-123">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="ceed4-124">Il ne met pas à jour les chaînes de connexion qui sont construites dynamiquement à l'aide du langage d'expression [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou en utilisant du code dans une tâche de script.</span><span class="sxs-lookup"><span data-stu-id="ceed4-124">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="ceed4-125">**Créer un ID de package**</span><span class="sxs-lookup"><span data-stu-id="ceed4-125">**Create new package ID**</span></span>  
 <span data-ttu-id="ceed4-126">Durant la mise à niveau de packages [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] , créez des ID de package pour les versions mises à niveau des packages.</span><span class="sxs-lookup"><span data-stu-id="ceed4-126">When upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, create new package IDs for the upgraded versions of the packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceed4-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ceed4-127">See Also</span></span>  
 <span data-ttu-id="ceed4-128">[Vue d’ensemble de la sécurité &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="ceed4-128">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="ceed4-129">Extension de packages avec des scripts</span><span class="sxs-lookup"><span data-stu-id="ceed4-129">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
  
  
