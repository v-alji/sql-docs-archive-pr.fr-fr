---
title: Informations d’emprunt d’identité | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42319d60-ccd0-46b8-af0b-f0968c390d8a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f9226fdbe8656aecf0f9173976c67ee386040d6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696284"
---
# <a name="impersonation-information"></a><span data-ttu-id="18f7e-102">Informations d’emprunt d’identité</span><span class="sxs-lookup"><span data-stu-id="18f7e-102">Impersonation Information</span></span>
  <span data-ttu-id="18f7e-103">Utilisez la page **Informations d’emprunt d’identité** pour spécifier les informations d’identification qu’Analysis Services utilisera pour se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="18f7e-103">Use the **Impersonation Information** page to specify the credentials that Analysis Services will use to connect to the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="18f7e-104">Options</span><span class="sxs-lookup"><span data-stu-id="18f7e-104">Options</span></span>  
 <span data-ttu-id="18f7e-105">**Utiliser un nom d'utilisateur et un mot de  passe Windows spécifiques**</span><span class="sxs-lookup"><span data-stu-id="18f7e-105">**Use a specific Windows user name and password**</span></span>  
 <span data-ttu-id="18f7e-106">Sélectionnez cette option pour que l’objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilise les informations d’identification de sécurité d’un compte d’utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="18f7e-106">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of a specified Windows user account.</span></span> <span data-ttu-id="18f7e-107">Les informations d’identification spécifiées sont utilisées pour le traitement, les requêtes ROLAP, les liaisons hors-ligne, les cubes locaux, les modèles d’exploration, les partitions distantes, les objets liés et la synchronisation entre la cible et la source.</span><span class="sxs-lookup"><span data-stu-id="18f7e-107">The specified credentials will be used for processing, ROLAP queries, out-of-line bindings, local cubes, mining models, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="18f7e-108">Cependant, pour les instructions DMX (Data Mining Extensions) OPENQUERY, cette option est ignorée et les informations d’identification de l’utilisateur actuel sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="18f7e-108">However, for Data Mining Extensions (DMX) OPENQUERY statements, this option is ignored and the credentials of the current user will be used.</span></span>  
  
 <span data-ttu-id="18f7e-109">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="18f7e-109">**User name**</span></span>  
 <span data-ttu-id="18f7e-110">Tapez le domaine et le nom du compte d'utilisateur que doit utiliser l'objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sélectionné.</span><span class="sxs-lookup"><span data-stu-id="18f7e-110">Type the domain and name of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="18f7e-111">Utilisez le format suivant :</span><span class="sxs-lookup"><span data-stu-id="18f7e-111">Use the following format:</span></span>  
  
 <span data-ttu-id="18f7e-112">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="18f7e-112">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="18f7e-113">Cette option est activée si **Utiliser un nom d'utilisateur et un mot de passe spécifiques** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="18f7e-113">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="18f7e-114">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="18f7e-114">**Password**</span></span>  
 <span data-ttu-id="18f7e-115">Tapez le mot de passe du compte d'utilisateur que doit utiliser l'objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sélectionné.</span><span class="sxs-lookup"><span data-stu-id="18f7e-115">Type the password of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="18f7e-116">Cette option est activée si **Utiliser un nom d'utilisateur et un mot de passe spécifiques** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="18f7e-116">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="18f7e-117">**Utiliser le compte de service**</span><span class="sxs-lookup"><span data-stu-id="18f7e-117">**Use the service account**</span></span>  
 <span data-ttu-id="18f7e-118">Sélectionnez cette option pour que l'objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilise les informations d'identification de sécurité associées au service [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] qui gère l'objet.</span><span class="sxs-lookup"><span data-stu-id="18f7e-118">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the object.</span></span> <span data-ttu-id="18f7e-119">Les informations d'identification du compte de service sont utilisées pour le traitement, les requêtes ROLAP, les partitions distantes, les objets liés et la synchronisation entre la cible et la source.</span><span class="sxs-lookup"><span data-stu-id="18f7e-119">The service account credentials will be used for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="18f7e-120">Cependant, pour les instructions DMX (Data Mining Extensions) OPENQUERY, les cubes locaux et les modèles d'exploration de données, les informations d'identification de l'utilisateur actuel sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="18f7e-120">However, for Data Mining Extensions (DMX) OPENQUERY statements, local cubes, and mining models, the credentials of the current user will be used.</span></span> <span data-ttu-id="18f7e-121">Cette option n'est pas prise en charge pour les liaisons hors ligne.</span><span class="sxs-lookup"><span data-stu-id="18f7e-121">This option is not supported for out-of-line bindings.</span></span>  
  
 <span data-ttu-id="18f7e-122">**Utiliser les informations d'identification de l'utilisateur actuel**</span><span class="sxs-lookup"><span data-stu-id="18f7e-122">**Use the credentials of the current user**</span></span>  
 <span data-ttu-id="18f7e-123">Sélectionnez cette option afin que l'objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilise les informations d'identification de sécurité de l'utilisateur actuel pour les liaisons hors ligne, les instructions DMX OPENQUERY, les cubes locaux et les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="18f7e-123">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of the current user for out-of-line bindings, DMX OPENQUERY, local cubes, and mining models.</span></span> <span data-ttu-id="18f7e-124">Cette option n'est pas prise en charge pour le traitement, les requêtes ROLAP, les partitions distantes, les objets liés et la synchronisation entre la cible et la source.</span><span class="sxs-lookup"><span data-stu-id="18f7e-124">This option is not supported for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span>  
  
 <span data-ttu-id="18f7e-125">**Être**</span><span class="sxs-lookup"><span data-stu-id="18f7e-125">**Inherit**</span></span>  
 <span data-ttu-id="18f7e-126">Sélectionnez cette option pour utiliser le comportement d'emprunt d'identité, défini au niveau de la base de données, qui a été défini par l'administrateur du serveur à l'aide de la propriété de base de données `DataSourceImpersonation`.</span><span class="sxs-lookup"><span data-stu-id="18f7e-126">Select this option to use the impersonation behavior, defined at the database level, which has been set by the server administrator using the `DataSourceImpersonation` database property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f7e-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18f7e-127">See Also</span></span>  
 <span data-ttu-id="18f7e-128">[Sources de données dans les modèles multidimensionnels](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="18f7e-128">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="18f7e-129">Sources de données prises en charge &#40;SSAS multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="18f7e-129">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
