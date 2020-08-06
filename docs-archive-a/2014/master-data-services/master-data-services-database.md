---
title: Base de données Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- database [Master Data Services], about the database
- database [Master Data Services]
ms.assetid: 5f590cc1-6ec2-4b8c-a598-03de0f6051a0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7e4bae180dfb7c9051d5445a689c44978ef73bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611128"
---
# <a name="master-data-services-database"></a><span data-ttu-id="0cbeb-102">Base de données Master Data Services</span><span class="sxs-lookup"><span data-stu-id="0cbeb-102">Master Data Services Database</span></span>
  <span data-ttu-id="0cbeb-103">La base de données contient toutes les informations pour le système [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cbeb-103">The database contains all of the information for the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span> <span data-ttu-id="0cbeb-104">Elle est au centre d’un déploiement [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cbeb-104">It is central to a [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] deployment.</span></span> <span data-ttu-id="0cbeb-105">La base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="0cbeb-105">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database:</span></span>  
  
-   <span data-ttu-id="0cbeb-106">stocke les paramètres, objets de base de données et données requis par le système [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-106">Stores the settings, database objects, and data required by the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span>  
  
-   <span data-ttu-id="0cbeb-107">contient des tables intermédiaires utilisées pour traiter les données des systèmes sources ;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-107">Contains staging tables that are used to process data from source systems.</span></span>  
  
-   <span data-ttu-id="0cbeb-108">fournit un schéma et des objets de base de données pour stocker les données de référence de systèmes sources ;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-108">Provides a schema and database objects to store master data from source systems.</span></span>  
  
-   <span data-ttu-id="0cbeb-109">prend en charge les fonctionnalités de contrôle de version, notamment la validation des règles d'entreprise et les notifications par courrier électronique ;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-109">Supports versioning functionality, including business rule validation and e-mail notifications.</span></span>  
  
-   <span data-ttu-id="0cbeb-110">fournit des vues pour les systèmes d'abonnement qui doivent récupérer des données de la base de données.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-110">Provides views for subscribing systems that need to retrieve data from the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0cbeb-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0cbeb-111">In This Section</span></span>  
  
-   [<span data-ttu-id="0cbeb-112">Table de mise en lots des membres feuille &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-112">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](leaf-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="0cbeb-113">Table de mise en lots des membres consolidés &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-113">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="0cbeb-114">Table de mise en lots des relations &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-114">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="0cbeb-115">Erreurs du processus de mise en lots &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-115">Staging Process Errors &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/staging-process-errors-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="0cbeb-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cbeb-116">See Also</span></span>  
 <span data-ttu-id="0cbeb-117">[Créer une base de données Master Data Services](install-windows/create-a-master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="0cbeb-117">[Create a Master Data Services Database](install-windows/create-a-master-data-services-database.md) </span></span>  
 <span data-ttu-id="0cbeb-118">[Master Data Services &#40;de sécurité de l’objet de base de données&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0cbeb-118">[Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span></span>  
 [<span data-ttu-id="0cbeb-119">Connexions, utilisateurs et rôles de base de données &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0cbeb-119">Database Logins, Users, and Roles &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/database-logins-users-and-roles-master-data-services.md)  
  
  
