---
title: Boîte de dialogue informations d’emprunt d’identité (Assistant importation de table) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.impersonationinfo.f1
ms.assetid: bee7eee5-0650-41f1-a372-5076ae97a58c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5300f8b6106a7f29f51018b4e039c2a8c28aa729
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696287"
---
# <a name="impersonation-information-dialog-box-table-import-wizard"></a><span data-ttu-id="84b6f-102">Boîte de dialogue Informations d'emprunt d'identité (Assistant Importation de table)</span><span class="sxs-lookup"><span data-stu-id="84b6f-102">Impersonation Information Dialog Box (Table Import Wizard)</span></span>
  <span data-ttu-id="84b6f-103">Utilisez la page **Informations d'emprunt d'identité** pour spécifier les informations d'identification que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilisera pour se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="84b6f-103">Use the **Impersonation Information** page to specify the credentials that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] will use to connect to the data source.</span></span> <span data-ttu-id="84b6f-104">Pour plus d’informations sur l’emprunt d’identité d’informations d’identification, consultez [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="84b6f-104">For more information about credentials impersonation, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="84b6f-105">Options</span><span class="sxs-lookup"><span data-stu-id="84b6f-105">Options</span></span>  
 <span data-ttu-id="84b6f-106">**Nom d’utilisateur et mot de passe Windows spécifiques**</span><span class="sxs-lookup"><span data-stu-id="84b6f-106">**Specific Windows user name and password**</span></span>  
 <span data-ttu-id="84b6f-107">Sélectionnez cette option pour que le modèle tabulaire utilise les informations d'identification de sécurité d'un compte d'utilisateur Windows spécifié.</span><span class="sxs-lookup"><span data-stu-id="84b6f-107">Select this option to have the tabular model use the security credentials of a specified Windows user account.</span></span>  
  
 <span data-ttu-id="84b6f-108">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="84b6f-108">**User name**</span></span>  
 <span data-ttu-id="84b6f-109">Entrez le domaine et le nom du compte d'utilisateur à utiliser.</span><span class="sxs-lookup"><span data-stu-id="84b6f-109">Type the domain and name of the user account to be used.</span></span> <span data-ttu-id="84b6f-110">Utilisez le format suivant :</span><span class="sxs-lookup"><span data-stu-id="84b6f-110">Use the following format:</span></span>  
  
 <span data-ttu-id="84b6f-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="84b6f-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="84b6f-112">Cette option est activée si **Utiliser un nom d'utilisateur et un mot de passe spécifiques** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="84b6f-112">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="84b6f-113">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="84b6f-113">**Password**</span></span>  
 <span data-ttu-id="84b6f-114">Tapez le mot de passe du compte d'utilisateur que doit utiliser le modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="84b6f-114">Type the password of the user account to be used by the Tabular model.</span></span>  
  
 <span data-ttu-id="84b6f-115">Cette option est activée si **Utiliser un nom d'utilisateur et un mot de passe spécifiques** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="84b6f-115">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="84b6f-116">**Compte de service**</span><span class="sxs-lookup"><span data-stu-id="84b6f-116">**Service account**</span></span>  
 <span data-ttu-id="84b6f-117">Sélectionnez cette option pour utiliser les informations d’identification de sécurité associées au service [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui gère le modèle.</span><span class="sxs-lookup"><span data-stu-id="84b6f-117">Select this option to use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b6f-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84b6f-118">See Also</span></span>  
 [<span data-ttu-id="84b6f-119">Emprunt d’identité &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="84b6f-119">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)  
  
  
