---
title: Modifier le compte d’administrateur système (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], changing
ms.assetid: cf30312e-4338-49a7-90f0-6e4f7b431ff8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d13cdc19c70c9e16c92dfd290393739d7e4f5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703055"
---
# <a name="change-the-system-administrator-account-master-data-services"></a><span data-ttu-id="663ec-102">Modifier le compte de l'administrateur système (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="663ec-102">Change the System Administrator Account (Master Data Services)</span></span>
  <span data-ttu-id="663ec-103">Vous pouvez modifier le compte d’utilisateur désigné comme [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] administrateur système.</span><span class="sxs-lookup"><span data-stu-id="663ec-103">You can change the user account that is designated as the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="663ec-104">Une fois cette procédure terminée, le compte d'administrateur système précédent est supprimé.</span><span class="sxs-lookup"><span data-stu-id="663ec-104">When you complete this procedure, the former system administrator user account is deleted.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="663ec-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="663ec-105">Prerequisites</span></span>  
 <span data-ttu-id="663ec-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="663ec-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="663ec-107">Vous devez ajouter le nom d'utilisateur du nouvel administrateur à la liste d'utilisateurs de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="663ec-107">You must add the new administrator's user name to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Users list.</span></span> <span data-ttu-id="663ec-108">Pour plus d’informations, consultez [Ajouter un utilisateur &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="663ec-108">For more information, see [Add a User &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="663ec-109">Vous devez avoir l'autorisation d'afficher mdm.tblUse et d'exécuter la procédure stockée mdm.udpSecurityMemberProcessRebuildModel dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="663ec-109">You must have permission to view mdm.tblUser and to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="663ec-110">Pour plus d’informations, consultez [Sécurité de l’objet de base de données &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="663ec-110">For more information, see [Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-change-the-administrator-account"></a><span data-ttu-id="663ec-111">Pour modifier le compte d'administrateur</span><span class="sxs-lookup"><span data-stu-id="663ec-111">To change the administrator account</span></span>  
  
1.  <span data-ttu-id="663ec-112">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et connectez-vous à l’instance [!INCLUDE[ssDE](../includes/ssde-md.md)] pour votre base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="663ec-112">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="663ec-113">Dans MDM. tblUser, recherchez l’utilisateur qui sera le nouvel administrateur et copiez la valeur dans la `SID` colonne.</span><span class="sxs-lookup"><span data-stu-id="663ec-113">In mdm.tblUser, find the user that will be the new administrator and copy the value in the `SID` column.</span></span>  
  
3.  <span data-ttu-id="663ec-114">Créez une requête.</span><span class="sxs-lookup"><span data-stu-id="663ec-114">Create a new query.</span></span>  
  
4.  <span data-ttu-id="663ec-115">Tapez le texte suivant, en remplaçant *Domain \ user_name* par le nom d’utilisateur et le *sid* du nouvel administrateur par la valeur que vous avez copiée à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="663ec-115">Type the following text, replacing *DOMAIN\user_name* with the new administrator's user name and *SID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpSecuritySetAdministrator] @UserName='DOMAIN\user_name', @SID = 'SID', @PromoteNonAdmin = 1  
    ```  
  
5.  <span data-ttu-id="663ec-116">Exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="663ec-116">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="663ec-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="663ec-117">See Also</span></span>  
 [<span data-ttu-id="663ec-118">Administrateurs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="663ec-118">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
  
