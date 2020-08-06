---
title: Appliquer immédiatement des autorisations de membre (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- members [Master Data Services], applying permissions immediately
- permissions [Master Data Services], applying member permissions immediately
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e960ad06213b7c5057a6249b72ce225a6abe35e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611129"
---
# <a name="immediately-apply-member-permissions-master-data-services"></a><span data-ttu-id="0a05f-102">Appliquer immédiatement des autorisations de membre (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0a05f-102">Immediately Apply Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="0a05f-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], au lieu d'attendre que la sécurité des membres s'applique à intervalles réguliers, vous pouvez appliquer immédiatement des autorisations de membre.</span><span class="sxs-lookup"><span data-stu-id="0a05f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], instead of waiting for member security to be applied at regular intervals, you can apply member permissions immediately.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a05f-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="0a05f-104">Prerequisites</span></span>  
 <span data-ttu-id="0a05f-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="0a05f-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0a05f-106">Vous devez avoir l'autorisation d'exécuter la procédure stockée mdm.udpSecurityMemberProcessRebuildModel dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a05f-106">You must have permission to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="0a05f-107">Pour plus d’informations, consultez [Sécurité de l’objet de base de données &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a05f-107">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-immediately-apply-hierarchy-member-permissions"></a><span data-ttu-id="0a05f-108">Pour appliquer immédiatement des autorisations de membres de la hiérarchie</span><span class="sxs-lookup"><span data-stu-id="0a05f-108">To immediately apply hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="0a05f-109">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et connectez-vous à l’instance [!INCLUDE[ssDE](../includes/ssde-md.md)] pour votre base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a05f-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="0a05f-110">Créez une requête.</span><span class="sxs-lookup"><span data-stu-id="0a05f-110">Create a new query.</span></span>  
  
3.  <span data-ttu-id="0a05f-111">Tapez le texte suivant, en remplaçant *database* par le nom de votre base de données et *Model_Name* par le nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="0a05f-111">Type the following text, replacing *database* with the name of your database and *Model_Name* with the name of the model.</span></span>  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  <span data-ttu-id="0a05f-112">Exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="0a05f-112">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a05f-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a05f-113">See Also</span></span>  
 <span data-ttu-id="0a05f-114">[Affecter des autorisations de membre de hiérarchie &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a05f-114">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="0a05f-115">Autorisations des membres de la hiérarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0a05f-115">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
