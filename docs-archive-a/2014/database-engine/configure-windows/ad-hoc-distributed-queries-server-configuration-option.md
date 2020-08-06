---
title: ad hoc distributed queries (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- OPENROWSET function, ad hoc distributed queries option
- Ad Hoc Distributed Queries option
- ad hoc distributed queries
- 7415 (Database Engine Error)
- OPENDATASOURCE function, ad hoc distributed queries option
- ad hoc access
ms.assetid: 5b982015-e196-44c3-83b8-275fb9d769b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d07b3c038597916cdaf026e24e90aab9d6b61616
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600233"
---
# <a name="ad-hoc-distributed-queries-server-configuration-option"></a><span data-ttu-id="783a2-102">ad hoc distributed queries (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="783a2-102">ad hoc distributed queries Server Configuration Option</span></span>
  <span data-ttu-id="783a2-103">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'autorise pas les requêtes distribuées ad hoc avec les fonctions OPENROWSET et OPENDATASOURCE.</span><span class="sxs-lookup"><span data-stu-id="783a2-103">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc distributed queries using OPENROWSET and OPENDATASOURCE.</span></span> <span data-ttu-id="783a2-104">Lorsque cette option est définie sur 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autorise l'accès d'égal à égal.</span><span class="sxs-lookup"><span data-stu-id="783a2-104">When this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows ad hoc access.</span></span> <span data-ttu-id="783a2-105">Lorsque cette option n'est pas définie ou lorsqu'elle est définie sur 0, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne permet pas non plus l'accès d'égal à égal.</span><span class="sxs-lookup"><span data-stu-id="783a2-105">When this option is not set or is set to 0, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc access.</span></span>  
  
 <span data-ttu-id="783a2-106">Les requêtes distribuées ad hoc utilisent les fonctions OPENROWSET et OPENDATASOURCE pour la connexion aux sources de données distantes OLE DB.</span><span class="sxs-lookup"><span data-stu-id="783a2-106">Ad hoc distributed queries use the OPENROWSET and OPENDATASOURCE functions to connect to remote data sources that use OLE DB.</span></span> <span data-ttu-id="783a2-107">OPENROWSET et OPENDATASOURCE doivent être utilisés uniquement pour faire référence à des sources de données OLE DB faisant l'objet d'accès peu fréquents.</span><span class="sxs-lookup"><span data-stu-id="783a2-107">OPENROWSET and OPENDATASOURCE should be used only to reference OLE DB data sources that are accessed infrequently.</span></span> <span data-ttu-id="783a2-108">Pour les sources de données faisant l'objet d'accès plus fréquents, définissez un serveur lié.</span><span class="sxs-lookup"><span data-stu-id="783a2-108">For any data sources that will be accessed more than several times, define a linked server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="783a2-109">L'activation de l'utilisation de noms ad hoc signifie que toute connexion authentifiée à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut accéder au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="783a2-109">Enabling the use of ad hoc names means that any authenticated login to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can access the provider.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="783a2-110">Les administrateurs doivent activer cette fonctionnalité pour les fournisseurs accessibles en toute sécurité via une connexion locale.</span><span class="sxs-lookup"><span data-stu-id="783a2-110">administrators should enable this feature for providers that are safe to be accessed by any local login.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="783a2-111">Notes</span><span class="sxs-lookup"><span data-stu-id="783a2-111">Remarks</span></span>  
 <span data-ttu-id="783a2-112">Toute tentative d’établissement d’une connexion ad hoc alors que l’option **Requêtes distribuées ad hoc** n’est pas activée génère une erreur : Msg 7415, Niveau 16, État 1, Ligne 1</span><span class="sxs-lookup"><span data-stu-id="783a2-112">Attempting to make an ad hoc connection with **Ad Hoc Distributed Queries** not enabled results in error: Msg 7415, Level 16, State 1, Line 1</span></span>  
  
 <span data-ttu-id="783a2-113">L'accès d'égal à égal au fournisseur OLE DB « Microsoft.ACE.OLEDB.12.0 » a été refusé.</span><span class="sxs-lookup"><span data-stu-id="783a2-113">Ad hoc access to OLE DB provider 'Microsoft.ACE.OLEDB.12.0' has been denied.</span></span> <span data-ttu-id="783a2-114">Vous devez accéder à ce fournisseur par le biais d'un serveur lié.</span><span class="sxs-lookup"><span data-stu-id="783a2-114">You must access this provider through a linked server.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="783a2-115">Exemples</span><span class="sxs-lookup"><span data-stu-id="783a2-115">Examples</span></span>  
 <span data-ttu-id="783a2-116">L'exemple suivant active des requêtes distribuées ad hoc puis interroge un serveur nommé `Seattle1` à l'aide de la fonction `OPENROWSET` .</span><span class="sxs-lookup"><span data-stu-id="783a2-116">The following example enables ad hoc distributed queries and then queries a server named `Seattle1` using the `OPENROWSET` function.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
sp_configure 'Ad Hoc Distributed Queries', 1;  
RECONFIGURE;  
GO  
  
SELECT a.*  
FROM OPENROWSET('SQLNCLI', 'Server=Seattle1;Trusted_Connection=yes;',  
     'SELECT GroupName, Name, DepartmentID  
      FROM AdventureWorks2012.HumanResources.Department  
      ORDER BY GroupName, Name') AS a;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="783a2-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="783a2-117">See Also</span></span>  
 <span data-ttu-id="783a2-118">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="783a2-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="783a2-119">[Serveurs liés &#40;moteur de base de données&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="783a2-119">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="783a2-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="783a2-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="783a2-121">[OPENDATASOURCE &#40;Transact-SQL&#41;](/sql/t-sql/functions/opendatasource-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="783a2-121">[OPENDATASOURCE &#40;Transact-SQL&#41;](/sql/t-sql/functions/opendatasource-transact-sql) </span></span>  
 [<span data-ttu-id="783a2-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="783a2-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql)  
  
  
