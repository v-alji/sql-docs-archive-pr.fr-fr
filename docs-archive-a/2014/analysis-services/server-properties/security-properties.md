---
title: Propriétés de sécurité | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], properties
- SecurityPackageList property
- BuiltinAdminsAreServerAdmins property
- DisableClientImpersonation property
- ErrorMessageMode property
- RequiredProtectionLevel property
- ServiceAccountIsServerAdmin property
- RequireClientAuthentication property
ms.assetid: 2fc7fe10-0cbb-49ac-aa8c-8ec3f7a7705f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 20133554835803908a340c5369eb66e86b119d72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604753"
---
# <a name="security-properties"></a><span data-ttu-id="08a03-102">Propriétés de sécurité</span><span class="sxs-lookup"><span data-stu-id="08a03-102">Security Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="08a03-103">prend en charge les propriétés de sécurité du serveur répertoriées dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="08a03-103">supports the security server properties listed in the following table.</span></span> <span data-ttu-id="08a03-104">Pour plus d'informations sur les autres propriétés de serveur et la façon de les configurer, consultez [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="08a03-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="08a03-105">**S'applique à :** mode serveur multidimensionnel et tabulaire</span><span class="sxs-lookup"><span data-stu-id="08a03-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="08a03-106">Propriétés</span><span class="sxs-lookup"><span data-stu-id="08a03-106">Properties</span></span>  
 `RequireClientAuthentication`  
 <span data-ttu-id="08a03-107">Propriété booléenne qui indique si le client doit être authentifié.</span><span class="sxs-lookup"><span data-stu-id="08a03-107">A Boolean property that indicates whether client authentication is required.</span></span>  
  
 <span data-ttu-id="08a03-108">La valeur par défaut de cette propriété est True, qui indique que le client doit être authentifié.</span><span class="sxs-lookup"><span data-stu-id="08a03-108">The default value for this property is True, which indicates that client authentication is required.</span></span>  
  
 `SecurityPackageList`  
 <span data-ttu-id="08a03-109">Propriété de type chaîne qui contient une liste (séparée par des virgules) des packages SSPI utilisés par le serveur pour l'authentification des clients.</span><span class="sxs-lookup"><span data-stu-id="08a03-109">A string property that contains a comma-separated list of SSPI packages used by server for client authentication.</span></span>  
  
 `DisableClientImpersonation`  
 <span data-ttu-id="08a03-110">Propriété booléenne qui indique si l'emprunt d'identité du client (par exemple depuis des procédures stockées) est désactivé.</span><span class="sxs-lookup"><span data-stu-id="08a03-110">A Boolean property that indicates whether client impersonation (for example, from stored procedures) is disabled.</span></span>  
  
 <span data-ttu-id="08a03-111">La valeur par défaut de cette propriété est False, qui indique que l'emprunt d'identité du client est activé.</span><span class="sxs-lookup"><span data-stu-id="08a03-111">The default value for this property is False, which indicates that client impersonation is enabled.</span></span>  
  
 `BuiltinAdminsAreServerAdmins`  
 <span data-ttu-id="08a03-112">Propriété booléenne qui indique si les membres du groupe des administrateurs de la machine locale sont des administrateurs [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08a03-112">A Boolean property that indicates whether members of the local machine administrators group are [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrators.</span></span>  
  
 `ServiceAccountIsServerAdmin`  
 <span data-ttu-id="08a03-113">Propriété booléenne qui indique si le compte de service est un administrateur de serveur.</span><span class="sxs-lookup"><span data-stu-id="08a03-113">A Boolean property that indicates whether the service account is a server administrator.</span></span>  
  
 <span data-ttu-id="08a03-114">La valeur par défaut de cette propriété est True, qui indique que le compte de service est un administrateur de serveur.</span><span class="sxs-lookup"><span data-stu-id="08a03-114">The default value for this property is True, which indicates that the service account is a server administrator.</span></span>  
  
 `ErrorMessageMode`  
 <span data-ttu-id="08a03-115">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08a03-115">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="08a03-116">Propriété entière de 32 bits signée qui définit le niveau de protection nécessaire pour toutes les demandes des clients.</span><span class="sxs-lookup"><span data-stu-id="08a03-116">A signed 32-bit integer property that defines the required protection level for all client requests.</span></span> <span data-ttu-id="08a03-117">Cette propriété peut prendre l'une des valeurs répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="08a03-117">This property has one of the values listed in the following table.</span></span>  
  
|<span data-ttu-id="08a03-118">Valeur</span><span class="sxs-lookup"><span data-stu-id="08a03-118">Value</span></span>|<span data-ttu-id="08a03-119">Description</span><span class="sxs-lookup"><span data-stu-id="08a03-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08a03-120">*0*</span><span class="sxs-lookup"><span data-stu-id="08a03-120">*0*</span></span>|<span data-ttu-id="08a03-121">Aucun, texte clair autorisé.</span><span class="sxs-lookup"><span data-stu-id="08a03-121">None, clear text allowed.</span></span>|  
|<span data-ttu-id="08a03-122">*1*</span><span class="sxs-lookup"><span data-stu-id="08a03-122">*1*</span></span>|<span data-ttu-id="08a03-123">(Valeur par défaut) Chiffrement requis, pas de journalisation en texte clair.</span><span class="sxs-lookup"><span data-stu-id="08a03-123">(Default) Encryption required, no clear-text logging.</span></span>|  
|<span data-ttu-id="08a03-124">*2*</span><span class="sxs-lookup"><span data-stu-id="08a03-124">*2*</span></span>|<span data-ttu-id="08a03-125">Demandes en texte clair autorisées, mais seulement avec des signatures (protection plus faible que le chiffrement).</span><span class="sxs-lookup"><span data-stu-id="08a03-125">Clear-text requests allowed but only with signatures (weaker protection than encryption).</span></span>|  
  
 `AdministrativeDataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="08a03-126">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08a03-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a03-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08a03-127">See Also</span></span>  
 <span data-ttu-id="08a03-128">[Configurer les propriétés du serveur dans Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="08a03-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="08a03-129">Déterminer le mode serveur d'une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="08a03-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
