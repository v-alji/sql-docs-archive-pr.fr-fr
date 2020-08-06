---
title: Opérations de service web par catégorie (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e3f346b5-7e26-481d-9821-1846e2e91289
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0f7dd682f55c16c6dcbff9f0f669593a10486da6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612451"
---
# <a name="categorized-web-service-operations-master-data-services"></a><span data-ttu-id="2a73d-102">Opérations de service Web par catégorie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2a73d-102">Categorized Web Service Operations (Master Data Services)</span></span>
  <span data-ttu-id="2a73d-103">Le service Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] contient un jeu complet d'événements qui vous permettent d'écrire du code pour contrôler toutes les fonctionnalités que [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] traite via son interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a73d-103">The [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service contains a complete set of operations that let you write code to control all of the features that [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] does through its user interface.</span></span> <span data-ttu-id="2a73d-104">Les opérations de service Web sont définies par le biais de l'interface <xref:Microsoft.MasterDataServices.IService> et sont implémentées en tant que méthodes de la classe <xref:Microsoft.MasterDataServices.ServiceClient>.</span><span class="sxs-lookup"><span data-stu-id="2a73d-104">The web service operations are defined by the <xref:Microsoft.MasterDataServices.IService> interface and are implemented as methods in the <xref:Microsoft.MasterDataServices.ServiceClient> class.</span></span> <span data-ttu-id="2a73d-105">Cette rubrique regroupe les opérations de service Web en catégories conceptuelles pour vous aider à comprendre comment utiliser l'API du service Web.</span><span class="sxs-lookup"><span data-stu-id="2a73d-105">This topic groups the web service operations into conceptual categories to help you understand how to use the web service API.</span></span>  
  
## <a name="model-operations"></a><span data-ttu-id="2a73d-106">Opérations de modèle</span><span class="sxs-lookup"><span data-stu-id="2a73d-106">Model Operations</span></span>  
 <span data-ttu-id="2a73d-107">Ces opérations sont utilisées pour créer, mettre à jour et supprimer de modèles, ainsi que pour traiter tout le contenu d'un modèle, comme des entités, des hiérarchies et des versions.</span><span class="sxs-lookup"><span data-stu-id="2a73d-107">These operations are used to create, update, and delete models, as well as to operate on all the contents of a model, such as entities, hierarchies, and versions.</span></span> <span data-ttu-id="2a73d-108">Pour plus d’informations, consultez [Modèles &#40;Master Data Services&#41;](../models-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-108">For more information, see [Models &#40;Master Data Services&#41;](../models-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>|  
  
## <a name="entity-operations"></a><span data-ttu-id="2a73d-109">Opérations d'entité</span><span class="sxs-lookup"><span data-stu-id="2a73d-109">Entity Operations</span></span>  
 <span data-ttu-id="2a73d-110">Ces opérations sont utilisées pour créer, mettre à jour, et supprimer les membres d'une entité unique.</span><span class="sxs-lookup"><span data-stu-id="2a73d-110">These operations are used to create, update, and delete the members of a single entity.</span></span> <span data-ttu-id="2a73d-111">Pour plus d’informations, consultez [Entités &#40;Master Data Services&#41;](../entities-master-data-services.md) et [Membres &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-111">For more information, see [Entities &#40;Master Data Services&#41;](../entities-master-data-services.md) and [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberKeyLookup%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersUpdate%2A>|  
  
## <a name="member-operations"></a><span data-ttu-id="2a73d-112">Opérations de membres</span><span class="sxs-lookup"><span data-stu-id="2a73d-112">Member Operations</span></span>  
 <span data-ttu-id="2a73d-113">Ces opérations sont utilisées pour obtenir, mettre à jour et supprimer des membres.</span><span class="sxs-lookup"><span data-stu-id="2a73d-113">These operations are used to get, update, and delete members.</span></span> <span data-ttu-id="2a73d-114">Le jeu de membres objet de l'opération peut contenir des membres provenant de plusieurs entités.</span><span class="sxs-lookup"><span data-stu-id="2a73d-114">The set of members operated on can contain members from multiple entities.</span></span> <span data-ttu-id="2a73d-115">Pour plus d’informations, consultez [Membres &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-115">For more information, see [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersGet%2A>|  
  
## <a name="attribute-and-hierarchy-operations"></a><span data-ttu-id="2a73d-116">Opérations d'attributs et de hiérarchies</span><span class="sxs-lookup"><span data-stu-id="2a73d-116">Attribute and Hierarchy Operations</span></span>  
 <span data-ttu-id="2a73d-117">Ces opérations sont utilisées pour obtenir les informations relatives aux attributs et aux hiérarchies.</span><span class="sxs-lookup"><span data-stu-id="2a73d-117">These operations are used to get attribute and hierarchy information.</span></span> <span data-ttu-id="2a73d-118">Les attributs et les hiérarchies peuvent également être modifiés à l'aide des opérations de modèle, telles que <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a73d-118">Attributes and hierarchies can also be modified by using the model operations, such as <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span></span> <span data-ttu-id="2a73d-119">Pour plus d’informations, consultez [Attributs &#40;Master Data Services&#41;](../attributes-master-data-services.md) et [Hiérarchies &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-119">For more information, see [Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) and [Hierarchies &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAttributesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.HierarchyMembersGet%2A>|  
  
## <a name="business-rule-operations"></a><span data-ttu-id="2a73d-120">Opérations de règle d'entreprise</span><span class="sxs-lookup"><span data-stu-id="2a73d-120">Business Rule Operations</span></span>  
 <span data-ttu-id="2a73d-121">Ces opérations sont utilisées pour créer, mettre à jour, supprimer, puis publier des règles d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="2a73d-121">These operations are used to create, update, delete, and publish business rules.</span></span> <span data-ttu-id="2a73d-122">Pour plus d’informations, consultez [Règles d’entreprise &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-122">For more information, see [Business Rules &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPaletteGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPublish%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesUpdate%2A>|  
  
## <a name="annotation-operations"></a><span data-ttu-id="2a73d-123">Opérations d'annotation</span><span class="sxs-lookup"><span data-stu-id="2a73d-123">Annotation Operations</span></span>  
 <span data-ttu-id="2a73d-124">Ces opérations sont utilisées pour créer, mettre à jour et supprimer des annotations.</span><span class="sxs-lookup"><span data-stu-id="2a73d-124">These operations are used to create, update, and delete annotations.</span></span> <span data-ttu-id="2a73d-125">Pour plus d’informations, consultez [Annotations &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-125">For more information, see [Annotations &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsGet%2A>|  
  
## <a name="transaction-operations"></a><span data-ttu-id="2a73d-126">Opérations de transaction</span><span class="sxs-lookup"><span data-stu-id="2a73d-126">Transaction Operations</span></span>  
 <span data-ttu-id="2a73d-127">Ces opérations sont utilisées pour obtenir et inverser des transactions.</span><span class="sxs-lookup"><span data-stu-id="2a73d-127">These operations are used to get and reverse transactions.</span></span> <span data-ttu-id="2a73d-128">Pour plus d’informations, consultez [Administrateurs &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-128">For more information, see [Transactions &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsReverse%2A>|  
  
## <a name="version-and-validation-operations"></a><span data-ttu-id="2a73d-129">Opérations de version et de validation</span><span class="sxs-lookup"><span data-stu-id="2a73d-129">Version and Validation Operations</span></span>  
 <span data-ttu-id="2a73d-130">Ces opérations sont utilisées pour copier et valider des versions.</span><span class="sxs-lookup"><span data-stu-id="2a73d-130">These operations are used to copy and validate versions.</span></span> <span data-ttu-id="2a73d-131">Pour plus d’informations, consultez [Versions &#40;Master Data Services&#41;](../versions-master-data-services.md) et [Validation &#40;Master Data Services&#41;](../validation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-131">For more information, see [Versions &#40;Master Data Services&#41;](../versions-master-data-services.md) and [Validation &#40;Master Data Services&#41;](../validation-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.VersionCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationProcess%2A>|  
  
## <a name="data-quality-operations"></a><span data-ttu-id="2a73d-132">Opérations de qualité des données</span><span class="sxs-lookup"><span data-stu-id="2a73d-132">Data Quality Operations</span></span>  
 <span data-ttu-id="2a73d-133">Ces opérations sont utilisées pour effectuer des tâches de qualité des données et vérifier les résultats.</span><span class="sxs-lookup"><span data-stu-id="2a73d-133">These operations are used to perform data quality tasks and to examine their results.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityCleansingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityMatchingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStart%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityInstalledState%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityKnowledgeBasesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationResultsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStatus%2A>|  
  
## <a name="data-import-operations"></a><span data-ttu-id="2a73d-134">Opérations d'importation de données</span><span class="sxs-lookup"><span data-stu-id="2a73d-134">Data Import Operations</span></span>  
 <span data-ttu-id="2a73d-135">Ces opérations sont utilisées pour importer des données dans une base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a73d-135">These operations are used to import data into a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="2a73d-136">Pour plus d’informations, consultez [Importation de données &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-136">For more information, see [Data Import &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingLoad%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingProcess%2A>|  
  
 <span data-ttu-id="2a73d-137">Les opérations suivantes sont utilisées pour importer des données à l'aide du processus de site inclus dans [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a73d-137">The following operations are used to import data by using the staging process included in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="2a73d-138">Elles doivent être utilisées uniquement pour prendre en charge les bases de données existantes.</span><span class="sxs-lookup"><span data-stu-id="2a73d-138">These operations should be used only to support existing databases.</span></span> <span data-ttu-id="2a73d-139">Pour la développement, utilisez les opérations précédemment répertoriées.</span><span class="sxs-lookup"><span data-stu-id="2a73d-139">For new development, use the previously listed operations.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingNameCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingProcess%2A>|  
  
## <a name="data-export-operations"></a><span data-ttu-id="2a73d-140">Opérations d'exportations de données</span><span class="sxs-lookup"><span data-stu-id="2a73d-140">Data Export Operations</span></span>  
 <span data-ttu-id="2a73d-141">Ces opérations sont utilisées pour exporter des données via les vues d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="2a73d-141">These operations are used to export data through the use of subscription views.</span></span> <span data-ttu-id="2a73d-142">Pour plus d’informations, consultez [exportation de données &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-142">For more information, see [Exporting Data &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewUpdate%2A>|  
  
## <a name="security-operations"></a><span data-ttu-id="2a73d-143">Opérations de sécurité</span><span class="sxs-lookup"><span data-stu-id="2a73d-143">Security Operations</span></span>  
 <span data-ttu-id="2a73d-144">Ces opérations sont utilisées pour modifier les paramètres de sécurité qui contrôlent l'accès à la base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a73d-144">These operations are used to modify the security settings that control access to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="2a73d-145">Pour plus d’informations, consultez [Importer des données à partir de tables &#40;Master Data Services&#41;](../security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2a73d-145">For more information, see [Security &#40;Master Data Services&#41;](../security-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesUpdate%2A>|  
  
## <a name="system-operations"></a><span data-ttu-id="2a73d-146">Opérations du système</span><span class="sxs-lookup"><span data-stu-id="2a73d-146">System Operations</span></span>  
 <span data-ttu-id="2a73d-147">Ces opérations sont utilisées pour obtenir et mettre à jour les paramètres système et les préférences de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a73d-147">These operations are used to get and update system settings and user preferences.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceVersionGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemDomainListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemPropertiesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesUpdate%2A>|  
  
  
